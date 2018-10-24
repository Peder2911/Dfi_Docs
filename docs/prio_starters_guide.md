# PRIO Starters guide to Dfi

## What is Dfi?

Dfi (Diverse_Folio_Isle, a working title) is a framework for reading, processing and reasoning about large quantities of text. As such, Dfi has several potential uses, like searching through text using regex, classifying text using ML-models, and potentially extracting information from text.

Dfi was developed for my [thesis](https://github.com/peder2911/thesis2018-2019) as a framework for scientifically testing the processing and reasoning steps for event coding.

## Steps

Follow these steps perform a simple filtering of Factiva-Pdf documents, either of sentences or full article text. This guide assumes that the technical setup of Dfi has been completed.

1. :pencil: Sourcing

   First, you need to import text into Dfi. Gather the Pdf documents in a folder, and transfer the folder to the computer running Dfi.

2. :cake: Run Dfi

   Double-click the script named Dfi on the desktop. This starts Dfi, and opens a terminal with a text prompt.

3. :eye: Choosing scripts

   Next you must specify which procedures to run. Dfi supports multiple procedures, many of which might be useful. For this walkthrough, choose _Unlit_Ferment_Typified_, which is a Factiva-Pdf sourcing script. Scripts are selected by entering a number corresponding to a choice in the list, and pressing enter.

4. :book: Sentences or article body

   Depending on whether you want to filter out individual sentences, or whole articles, select Sentence_Splitter, or bypass the preprocessing stage.

5. :balance_scale: Filtering

   For this walkthrough, select the _Entrap_Met_Star_ classification script. This is a regex-filtering script.

6. :gear: Configuring the scripts

   Next you must configure the chosen scripts. Following this tutorial, you must configure two scripts; the Pdf-sourcing script Uft, and the regex filtering script Ems.

7. :eye: Configuring Uft

   You must enter the path to the folder containing the Pdf documents you wish to process. A path is a location in your computers' file system. If your pdfs are in a folder named "Colombia", located on your desktop, the path is /home/coder/Desktop/Colombia.
   To see the parent folder of a file, right click it and choose properties.

8. :balance_scale: Configuring Ems

   The regex filtering script Ems requires two configuration steps. First, you must choose whether to search in the headline or body of each article. If you chose to use the sentence splitter earlier, “body” means sentence.
   Next you must enter a regex pattern to use for searching. Regex (Regular Expressions) is a very poweful search tool with many applications. A very useful site when working with Regex is [regex101](https://regex101.com/), which lets you test patterns before applying them. For a concise introduction to regex, see [this tutorial from O'reilly](https://www.oreilly.com/ideas/an-introduction-to-regular-expressions).

   You must also choose whether to _keep_ matches, or _discard_ matches. This means that you can do a negative or positive search; either keeping all entries matching your pattern (searching), or discarding all entries matching your pattern (filtering).

9. :clock1: Wait

   The program will take a moment to execute, depending on the scope of your search.

10. :trophy: Results

    The results will appear in your current working directory. If you ran the script from the desktop, the results will appear on the desktop, in the file called tmp.csv. Remember to rename and / or move this file if you are performing multiple searches, as the program overwrites the file tmp.csv each time it is run.

## Using the results:

tmp.csv is a csv-formatted data file containing the sentences or articles that matched your search pattern. The file can be opened in any data analysis environment, including Excel, Stata and R for further processing or visualization. For tips, see this document on example runs.

## Further reading

https://www.oreilly.com/ideas/an-introduction-to-regular-expressions

