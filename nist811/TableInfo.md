The following tables in CSV format are an abbreviated version of the NIST 
["Special Publication 811: NIST Guide to the SI" Appendix B.9](https://www.nist.gov/pml/special-publication-811/nist-guide-si-appendix-b-conversion-factors/nist-guide-si-appendix-b9). 
They are converted to a more easily machine readable format and are used for 
verifying conversion accuracy of units in the db.json file.

They have the following basic format:

| Convert From | Convert To | Multipy By | Supported       |
| ------------ | ---------- | ---------- | --------------- |
| ft / s       | m / s      | 3.048e-01  | true            |

Which means that (1 ft / s) approximately equals (3.048e-01 m / s). The last 
row indicates if the conversion is supported by the units located in the
`unitdata/db.json` database file. Non obvious or confusing units may have a 
full name included in parenthesis to avoid confusion. For example:

| Convert From  | Convert To | Multipy By | Supported       |
| ------------- | ---------- | ---------- | --------------- |
| Gal (Galileo) | \[c\]m / s^2 | 1.0      | false           |

It is assumed that most people would easily confuse this unit with the more
common "Gallon". So special notation is helpful.

