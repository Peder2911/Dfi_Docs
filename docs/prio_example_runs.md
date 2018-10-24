# PRIO example runs

This document contains suggestions for using Dfi to find ceasefires in Factiva Pdf documents.

## Workflow

Transfer the Pdf documents you want to process to a memory stick or online location, so you can put them onto the computer running Dfi. If you don't want to bother too much with learning about paths, put the folder containing the documents on the desktop and use this path:

```
/home/coder/Desktop/name_of_your_folder
```

Remember to keep the desktop clutter free! Delete the folder after using the script.

## Regex suggestions

Learning Regex can be a bit daunting, since it looks sort of like Snoopy swearing. These examples both illustrate the power of regex, and might be useful in themselves:

To find all entries (sentences or articles) containing either of the words _Ceasefire, ceasefire, cease-fire, Truce, truce, Armistice or armistice_:

```
([Cc]ease-?fire|[Tt]ruce|[Aa]rmistice)
```

To find all entries containing the words _signed, signing, signs_ and other conjugations:

```
\bsign[a-z]{1,3}\b
```

To find all entries containing the words _peace deal,  peace declaration, peace agreement_:

```
[Pp]eace\s(deal|declaration|agreement)
```

The concepts used in the expressions above are groups, word-classes, and quantifiers. For more information about these, see [this tutorial](https://www.oreilly.com/ideas/an-introduction-to-regular-expressions). To see what these patterns will find, copy and paste them on [regex101](https://regex101.com/), which is an excellent resource for working with Regex. 

## Multiple searches

For each run, the program applies a single Regex pattern. This means that filtering entries containing the word Truce, _and then_ finding the entries among these containing the word Deal requires two consequtive runs.

First, [run Dfi and use Pdfs as source](./prio_starters_guide.md). The output file tmp.csv will then be used as input for the program. To do this, run Dfi again and select _Simple_Csv_ as your sourcing option. When configuring, you will be prompted to enter a csv-file to use. The path to tmp.csv on your desktop is:

```
/home/coder/Desktop/tmp.csv
```

Next, configure Dfi as you otherwise would. This will perform a Regex search on the entries in the results from the first search. This looping search can be performed any number of times, consequtively narrowing the scope of your data.

:warning: __Remember, Dfi overwrites the tmp.csv file every time it is run__

This means that if you want to keep the results of a search, the file must be renamed. For example, if i do a Pdf-search on entries containing the word armistice, and i want to find both entries that also contain the word initiated _and_ entries that contain the word ended, in separate datasets, i would have to:

1. Do a Pdf-search, producing tmp.csv.
2. Rename the initial file to ceasefire.csv
3. Do a Simple_Csv run targeting `/home/coder/Desktop/ceasefire.csv` using the regex string `initiated`, and renaming the result initiated.csv
4. Do a Simple_Csv run targeting `/home/coder/Desktop/ceasefire.csv` using the regex string `ended`, and renaming the result ended.csv

Now i have three files, containing all of my results; a file containing all entries mentioning ceasefire, a file containing entries containing both ceasefire _and_ initiated, and a file containing entries containing both ceasefire _and_ initiated.

## Keep and Discard

:scissors: The Entrap_Met_Star module allows for negative (_discard_) and positive (_keep_) searches. Combining successive negative and positive searches might be a very useful strategy; for example first extracting all articles not mentioning something (discard), then searching within those articles for mentions of something else (keep).

  