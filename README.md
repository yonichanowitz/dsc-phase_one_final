# Microsoft Film Production company Proposal

## Goal: Prove what factors contribute to a profitable film

This repository is a mock proposal of decisions for how Microsoft should go about creating 
a film production company.

The project uses real data about film from popular film rating databases. 
It includes data and a Jupyter notebook demonstrating how i would go 
about processing said data and come to conclusions on what Microsoft should do

## Contents of this repository 

- `README.md`: README document that sumerizes this repo. what you are reading now

- `index.ipynb`: A Jupyter notebook demonstrating the methods i used to get to the conclusions i did, with the available data

This notebook loads appropriate libraries, creates pandas dataframes from the data, cleans
the data, organizes it, calculates profit, calculates averages, creates graphs to demonstrate findings

- `MicrosoftFilms.pdf`: A slideshow as a PDF with a graphical summery of my findings.
This slideshow is a synopsis of the findings, intended to be used with a live presentation

- `unzipped-data` folder: Folder with data used in the Jupyter notebook above

## Jupyter notebook explanation

### data sources

the data used in this project is from [The Numbers](https://www.the-numbers.com/) , [Box Office Mojo](https://www.boxofficemojo.com/)
and [IMDB](https://developer.imdb.com/)

*The Numbers* and *BoxOfficeMojo* were used to get financial data on 5700+ films
*IMDB* was used to gather genre and names of people in the films from the above data bases

### data that was ignored

the *IMDB* database, while having the most films, did not have any financial data, and therefore, was not usable as the base database.
any columns which did not help relate to that data was droppped. films that were on both *The Numbers* and *IMDB*, after data cleaning were about 3800. the 3800 rows were then joined with a table of personelle in each film, generating a new database of about 140,000 rows, one each for Writers, Directors and Actors respectively, per movie.

### criteria for a profitable film

i defined a profitable film as a film where the `domestic gross` sales at the box office, subtracting the `film production cost` was more than $1. i also ran the same calculations on international films, but the resulting data set was much smaller, with more outliers 

### filtering method

the database was then split into three tables, one each for Directors, Writers, and Actors. each table was then sorted by profitability then grouped by `nconst` which is a identifier *IMDB* gives to each person on a film, and added a column with an aggregation of the average of the profit of all films each person was in. Afterwards i filtered each database by people who's average film profit was greater than $3m to get the "best of the best"

this method was applied again for genre

## conclusion

films who had a combination of the best of the best, generally made more money