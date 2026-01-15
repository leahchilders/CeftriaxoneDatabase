# Ceftriaxone + *Neisseria gonorrhoeae* Database

- The main **SQLite** file was last modified:
- The **CSV** files were last modified:

-----

### Note: This repository is currently empty and the `/ceftriaxone` link below does not currently exist. This will all be posted by the end of January 2026.

-----

### 1 Introduction and Basic Information

This repository contains the downloadable content powering my database UI on my portfolion website: https://leahchilders-portfolio.vercel.app/ceftriaxone-database. This website has authentication set up for other pages, but you do not need to be logged in to access the database.

The database centralizes reported pharmacodynamic values (the minimum inhibitory dose (MIC) as well as dose response curve parameters) from a systematic literature search of the antibiotic Ceftriaxone used to treat both susceptible and resistant strains of *Neisseria gonorrhoeae*. 

There are three main categories of data contained in this database, and they are labeled as such:

1. MIC values reported by a publication (typically from broth dilution or Etest susceptibility testing)
2. PD curve parameters reported by a publication (typically from fitting Hill functions to time-kill data)
3. PD curve parameters fit by me, using time-kill data or figures reported by a publication

The database schema is shown in `database_schema.md` so you can see what tables and columns exist. While most of the information is presented via the UI, some is supplementary and not mentioned there.

The main database file is `ceftriaxone.sqlite`, but for convenience I have also included CSV files for each table. To avoid unintended behavior, I would recommend not opening these CSV's in Excel (interesting read: [Despite geneticists being warned about spreadsheet problems, 30% of published papers contain mangled gene names in supplementary data.](https://www.nature.com/articles/d41586-021-02211-4)). I do not believe any of the fields will autocorrect, but I cannot guarantee the accuracy. I will also not be able to update the CSV files as frequently as I update the SQLite file.

### 2 Methods

#### 2.1 Populating the Database

This database was created using SQLite3. I query the database using both the command line as well as through a small Python API I wrote specifically to help me record the data.

#### 2.2 Serving the Database

The UI is presented on my portfolio website, a Next.js site hosted on Vercel. The SQLite file is shipped and queried by the client. The plots are generated using Plotly.

#### 2.3 Systematic Literature Review


#### 2.4 Pharmacodynamic Curve Fitting


### 3 Lisence, Use, and Citation

#### 3.1 For the Referenced Publications

Lisences, copyright information, DOIs, URLs, and bibtex citations are provided for each publication in the database. I also note the figure/table/file provenance. When data comes from an open access paper, I may also provide a copy of the figures and tables referenced (see `supplementary_resources/publication_assets`). 

To cite the database as a whole, see below, but to cite primary claims, cite the publication the report came from. To cite parameters fit by me whose data came from a publication, cite the database and the publication.

#### 3.2 For the Database

The contents of this database are covered by the [lisence]. This database may be used, referenced, and distributed, but it must be cited. I provide the following bibtex citations for the dataset:

```bibtex
@dataset{childers_cefdb_2026,
  author={Childers, Leah},
  title={CefDB: A Curated Database of Ceftriaxone Pharmacodynamics and Susceptibility Measurements},
  year={2026},
  url={https://leahchilders-portfolio.vercel.app/ceftriaxone-database}
}
