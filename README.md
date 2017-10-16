# check-my-pages

**check-my-pages** is a scrapping script to test the Spanish web archive (with more than 10,000 pages). It checks each url in a list and creates report files about what was tested. Each file reports about a specific issue and includes the scanned url together with the result.

Please note that the script was written to check for problems detected when manually inspecting a small sample (about 1%) of the Spanish website. This script was not built to be used as-it-is in other websites, you are supposed to modify it.

This script complements other scripts and command line tools like ack, grep, rpl and others.

## Download and install

To install the script, clone the repository, compile it and move the executable to your working folder.

## File with list of urls

The urls file, by default `urls.csv` must have all the urls you want to check. You can use a text file with 1 url per line or a csv file with the urls on the first column and without headers.

## Checking the urls

To check all urls in `urls.csv` with all the checks use the command:

```
./scrap -urls=urls.csv -http -analytics -canonical
```

This repository includes a few testing urls in the file `urls.csv`. Please replace them by your own.

It will create a couple of files, one per check the script is doing:
* `httpResponses.csv` - Stores the http response codes for the URL. 200 means everything is OK.
* `analytics.csv` - Reports unusual google analytics codes
* `canonicals.csv` - Reports the canonical url for every url

## Remove the report files

To remove the files created by **check-my-pages**:

```
./scrap -clear 
```