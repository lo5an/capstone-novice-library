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

~~~{.bash}
pip install pymarc
~~~


## Displaying some book data

~~~{.python}
# Print a list of titles from a MARC record
from pymarc import MARCReader
with open('./data/marc.dat', 'rb') as marcfile:
    reader = MARCReader(marcfile)
    for record in reader:
        print(record['245']['a'])
~~~


## Updating our records

~~~{.python}
from pymarc import MARCReader
with open('./data/marc.dat','rb') as marcin, open('./data/newmarc.dat', 'wb') as marcout:
    reader = MARCReader(marcin)
	for record in reader:
        record.add_field(Field()) #TODO: need to actually add content
	    out.write(record.as_marc())
~~~



