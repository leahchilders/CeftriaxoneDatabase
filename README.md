# Ceftriaxone + *Neisseria gonorrhoeae* Database

- The main **SQLite** file was last modified: *not uploaded yet*
- The **CSV** files were last modified: *not uploaded yet, but `publication_citations/publications.py` is up to date*

-----

### Note: This repository is a work in progress. Importantly, all publication citations and provenance has been added. The rest of the data and methods will be added incrementally as I work on it.

-----

## 1 Introduction and Basic Information

This repository contains (some of) the downloadable content powering my database UI on my portfolion website: https://leahchilders-portfolio.vercel.app/ceftriaxone-database. This website has authentication set up for other pages, but you do not need to be logged in to access the database.

The database centralizes reported pharmacodynamic values (the minimum inhibitory dose (MIC) as well as dose response curve parameters) from a systematic literature search of the antibiotic Ceftriaxone used to treat both susceptible and resistant strains of *Neisseria gonorrhoeae*. 

There are three main categories of data contained in this database, and they are labeled as such:

1. MIC values reported by a publication (typically from broth dilution or Etest susceptibility testing)
2. PD curve parameters reported by a publication (typically from fitting Hill functions to time-kill data)
    - These reported parameters may contain a fitted `zMIC` value, which is not always equal to the observed MIC. One publication may report (i) a broth dilution MIC, (ii), an Etest MIC, and (iii) a fitted zMIC value, and these may al three be different.
3. PD curve parameters fit by me, using time-kill data or figures reported by a publication

The tables and their columns are available in `database_schema.txt`. While most of the information is presented via the UI, some is supplementary and not mentioned there (and since this is a work in progress, some of the information isn't available anywhere yet, but it will be).

**Not available yet but will be:** The main database file is `ceftriaxone.sqlite`, but for convenience I have also included CSV files for each table. To avoid unintended behavior, I would recommend not opening these CSV's in Excel (interesting read: [Despite geneticists being warned about spreadsheet problems, 30% of published papers contain mangled gene names in supplementary data.](https://www.nature.com/articles/d41586-021-02211-4)). I do not believe any of the fields will autocorrect, but I cannot guarantee the accuracy. I will also not be able to update the CSV files as frequently as I update the SQLite file.

## 2 Methods

### 2.1 Populating the Database

This database was created using SQLite3. I query the database using both the command line as well as through a small Python API I wrote specifically to help me record the data.

### 2.2 Serving the Database

The UI is presented on my portfolio website, a Next.js site hosted on Vercel. The SQLite file is shipped and queried by the client. The plots are generated using Plotly.

### 2.3 Systematic Literature Review


### 2.4 Pharmacodynamic Curve Fitting


## 3 Lisence, Use, and Citation

### 3.1 For the Referenced Publications

This repository includes data extracted from peer-reviewed publications. The underlying publications (and any figures/tables/media originating from them) remain covered by their original copyright and license terms. Each publication's data can currently be found in `publication_citations/publications.py`.

For each publication referenced in the database, I record the DOI/URL, licensing or copyright notes, and provenance (e.g., whether a value came from a table, figure, supplement, or raw dataset). 

For any third-party "publication assets" (e.g., figures or tables saved under `supplementary_resources/publication_assets`), those files are not covered by the database license in Section 3.2 and may only be reused according to the terms of the original publication. I will only put assets from open access papers in this folder, and it will not be exhaustive.

### 3.2 For the Database

The database contents and my original contributions are licensed under the **Creative Commons Attribution 4.0 International License (CC BY 4.0).** This includes:

- The SQLite database file (`ceftriaxone.sqlite`)
- The table-level CSV exports
- My original schema design and curation work (including annotations/metadata I created)
- Parameter datasets fit by me (when derived from time-kill data or digitized figure data), as represented in this repository

**What This License Does Not Cover:** CC BY 4.0 in this repository does not grant rights to:

- Third-party figures/tables/media from publications (even if stored in this repo), which remain under their original terms
- Content that is not owned by me or is not licensable by me

### 3.3 How to Cite

If you use or redistribute the database, please cite it. For scientific claims, cite the original publication(s) associated with the specific measurements/parameters.

```bibtex
@dataset{childers_cefdb_2026,
  author={Childers, Leah},
  title={CefDB: A Curated Database of Ceftriaxone Pharmacodynamics and Susceptibility Measurements against Neisseria gonorrhoeae},
  year={2026},
  url={https://leahchilders-portfolio.vercel.app/ceftriaxone-database}
}
