# Privacy Shields API

Use this interface to retrieve a privacy shield (SVG badge) for a service.

![](https://shields.tosdr.org/en_596.svg)

## Endpoint

```
https://shields.tosdr.org/<locale>_<service_id>.svg
```

## Parameters

| Parameter  | Type            | Description            |
| ---------- | --------------- | ---------------------- |
| service_id | String\|Integer | ID of the service.     |
| locale     | String          | Locale code for the badge (for example `en`). |
