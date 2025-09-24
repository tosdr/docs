# Useful SQL Queries

This Page is more or less targeted at ToS;DR Staff with access to Production or Staging Databases.

Though they may be useful for anyone self hosting Phoenix as well.

* [Top 10 Services with most approved points](useful-sql-queries.md#UsefulSQLQueries-Top10Serviceswithmostapprovedpoints)
* [Get amount of services a rating has](useful-sql-queries.md#UsefulSQLQueries-Getamountofservicesaratinghas)
  * [Excluding N/A Ratings](useful-sql-queries.md#UsefulSQLQueries-ExcludingN/ARatings)
* [Top 10 Services on ToS;DR with the “highest” possible rating.](useful-sql-queries.md#UsefulSQLQueries-Top10ServicesonToS;DRwiththe“highest”possiblerating.)
* [Top 10 Services on ToS;DR with the “worst” possible rating.](useful-sql-queries.md#UsefulSQLQueries-Top10ServicesonToS;DRwiththe“worst”possiblerating.)

### Top 10 Services with most approved points <a href="#usefulsqlqueries-top10serviceswithmostapprovedpoints" id="usefulsqlqueries-top10serviceswithmostapprovedpoints"></a>

```
SELECT COUNT(POINTS.ID) AS POINTSUM,
	SERVICES.NAME As SERVICENAME,
	SERVICES.RATING
FROM POINTS
INNER JOIN SERVICES ON POINTS.SERVICE_ID = SERVICES.ID
WHERE POINTS.STATUS = 'approved'
GROUP BY SERVICES.ID
ORDER BY POINTSUM DESC
LIMIT 10
```

### Get amount of services a rating has <a href="#usefulsqlqueries-getamountofservicesaratinghas" id="usefulsqlqueries-getamountofservicesaratinghas"></a>

```
SELECT COUNT(RATING) AS AMOUNT,
	RATING,
	CONCAT((COUNT(RATING) * 100 /
										(SELECT COUNT(RATING)
											FROM SERVICES
											WHERE RATING IS NOT NULL )), '%') AS PERCENTAGE
FROM SERVICES
WHERE RATING IS NOT NULL
GROUP BY RATING
ORDER BY RATING ASC;
```

#### Excluding N/A Ratings <a href="#usefulsqlqueries-excludingn-aratings" id="usefulsqlqueries-excludingn-aratings"></a>

```
SELECT COUNT(RATING) AS AMOUNT,
	RATING,
	CONCAT((COUNT(RATING) * 100 /
										(SELECT COUNT(RATING)
											FROM SERVICES
											WHERE RATING IS NOT NULL
												AND RATING != 'N/A')), '%') AS PERCENTAGE
FROM SERVICES
WHERE RATING IS NOT NULL
	AND RATING != 'N/A'
GROUP BY RATING
ORDER BY RATING ASC;
```

### Top 10 Services on ToS;DR with the “highest” possible rating. <a href="#usefulsqlqueries-top10servicesontos-drwiththe-highest-possiblerating" id="usefulsqlqueries-top10servicesontos-drwiththe-highest-possiblerating"></a>

Counts all Services with an “A” rating and the most “good” cases.

```
SELECT SERVICES.NAME,
	SERVICES.RATING,
	COUNT(CASES.CLASSIFICATION) AS AMOUNTGOODCASES
FROM SERVICES
INNER JOIN POINTS ON POINTS.SERVICE_ID = SERVICES.ID
INNER JOIN CASES ON CASES.ID = POINTS.CASE_ID
WHERE SERVICES.RATING = 'A'
    AND POINTS.STATUS = 'approved'
	AND SERVICES.IS_COMPREHENSIVELY_REVIEWED = TRUE
	AND CASES.CLASSIFICATION = 'good'
	AND SERVICES.ID != 969 /* Exluding ToS;DR Phoenix */
	AND SERVICES.ID != 596 /* Excluding ToS;DR */
GROUP BY SERVICES.ID,
	CASES.CLASSIFICATION
ORDER BY AMOUNTGOODCASES DESC
LIMIT 10;
```

### Top 10 Services on ToS;DR with the “worst” possible rating. <a href="#usefulsqlqueries-top10servicesontos-drwiththe-worst-possiblerating" id="usefulsqlqueries-top10servicesontos-drwiththe-worst-possiblerating"></a>

Counts all Services with an “E” rating and the most “bad” and “blocker” cases

```
SELECT SERVICES.NAME,
	SERVICES.RATING,
	COUNT(CASES.CLASSIFICATION) AS AMOUNTBADCASES
FROM SERVICES
INNER JOIN POINTS ON POINTS.SERVICE_ID = SERVICES.ID
INNER JOIN CASES ON CASES.ID = POINTS.CASE_ID
WHERE SERVICES.RATING = 'E'
    AND POINTS.STATUS = 'approved'
	AND SERVICES.IS_COMPREHENSIVELY_REVIEWED = TRUE
	AND (CASES.CLASSIFICATION = 'bad'
						OR CASES.CLASSIFICATION = 'blocker')
GROUP BY SERVICES.ID,
	CASES.CLASSIFICATION
ORDER BY AMOUNTBADCASES DESC
LIMIT 10;
```
