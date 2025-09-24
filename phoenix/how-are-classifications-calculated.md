# How are classifications calculated?

Feel free to check the most up-to-date version of our algorithm [here](https://github.com/tosdr/edit.tosdr.org/blob/master/app/models/service.rb#L88-L109).

Basically, as of Sept 2025, a blocker counts as 3 bad points, and the algorithm looks at the balance:

number of good points − number of bad points − (3 × number of blockers).

* If there are no points at all, the grade is N/A.
* If the balance is −10 or lower, or if the number of blockers is greater than the number of good points, you get an E.
* Otherwise, if you have at least 3 blockers or if you have more bad points than good points, you get a D.
* Otherwise, if the balance is less than 5, you get a C.
* Otherwise, if you still have any bad points, you get a B.
* Only if you have no blockers and no bad points at all, you get an A.
