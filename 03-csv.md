---
layout: page
title: Working with Library Data
subtitle: CSV Files
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Explain why we might want to use a library when working with even
>   a fairly simple format like CSV.
> * Use the csv module in the Python Standard Library to read and write
>   CSVs


[CSV](http://en.wikipedia.org/wiki/Comma-separated_values) is a
least-common-denominator file format for tabular data that can be
imported and/or exported by many systems. The basic dea is simple:
rows of fields seperated by commas; but there is no official standard
specifying exactly it should be implemented, and there are many
possibly variants and gotchas.

Handily, Python includes a nice module for reading and writing from
CSV files. Unsurprisingly, it's called
[csv](https://docs.python.org/2/library/csv.html).





~~~ {.python}
~~~

> ## Challenge Title {.challenge}
>
> Description of a single challenge.
> There may be several challenges
> that make reference to [Challenge Title](01-one.html#challenge-title).
