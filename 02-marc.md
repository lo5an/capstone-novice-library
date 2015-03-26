---
layout: page
title: Working With Library Data
subtitle: MARC Records
minutes: 10
---
> ## Learning Objectives {.objectives}
>
> * Find and evaluate specialized Python libraries
> * Read and display MARC records
> * Modify and save MARC records

## The quest for a MARC tool

Lots of library metadata lives in MARC records, which is a pretty
complicated data format to parse, so a good starting point for working
with MARC is looking for a Python library that can do the heavy
lifting for us.

A quick look through the <a
href="https://docs.python.org/2/library/index.html">Python Standard
Library</a> doesn't turn up anything, but a search for "python marc"
leads us to <a href="https://github.com/edsu/pymarc">pymarc</a> by Ed
Summers.

Looking around the GitHub repository, we can see that pymarc:
* has been updated recently
* seems to be in regular use by many people
* has pretty good documentation
* installs simply, and without difficut dependencies

The recommended installtion method uses pip, which is now the default
package manager for python.

~~~{.bash}
pip install pymarc
~~~

## Displaying book info

Now that we've got a tool for handling MARC, let's test it by
displaying some book information. We'll begin by printing out the
title field for all of the records in a MARC file.


~~~{.python}
# Print a list of titles from a MARC record
from pymarc import MARCReader
with open('./data/marc.dat', 'rb') as marcfile:
    reader = MARCReader(marcfile)
    for record in reader:
        print(record['245']['a'])
~~~


## Updating  records

Reading information from MARC is nice, but we also need to be able to
update and save records, so let's try that next.

~~~{.python}
from pymarc import MARCReader
with open('./data/marc.dat','rb') as marcin, open('./data/newmarc.dat', 'wb') as marcout:
    reader = MARCReader(marcin)
	for record in reader:
        record.add_field(Field()) #TODO: need to actually add content
	    out.write(record.as_marc())
~~~


> ## MARC Summary {.challenge}

> Write a function that takes a file name as an argument and prints
> out a numbered list of title, author, and publication date for each
> record.


