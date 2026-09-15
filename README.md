# dsa-bible

This is a study project for exploratory data analysis of biblical data with R. It uses the Almeida Revista e Corrigida (ARC) translation in a SQLite database to explore the structure and distribution of books, chapters, verses, and characters.

The project was created as a practical exercise after the Alura course **R for Data Science: Conhecendo a linguagem**. It is a learning repository: the report, code, and analysis can evolve as new R and data-analysis concepts are studied.

## Purpose

Serve as a personal reference for practicing:

- Loading data from a SQLite database with R
- Transforming and joining data with `dplyr`
- Calculating counts, maximums, minimums, means, and medians
- Producing a reproducible exploratory analysis with Quarto

## Stack

- R 4.3.3 was used to develop the project
- Quarto for the executable report
- SQLite for the biblical data
- R packages: `RSQLite`, `glue`, and `dplyr`

## Structure

```text
.
├── data/ARC.sqlite          # Almeida Revista e Corrigida database
├── images/                  # images used by the report
├── main.qmd                 # Quarto report and analysis code
├── DSA com a Bíblia.pdf     # exported project report
├── README.md
└── LICENSE
```

## Analysis

The report loads the Bible database and builds views by verse, chapter, and book. It explores topics such as:

- The largest and smallest verses, chapters, and books by different measures
- Counts of chapters, verses, and characters
- Means and medians for characters, verses, and chapters
- The distribution of books between the Old and New Testaments

The analysis is documented in Portuguese in [`main.qmd`](main.qmd).

## Running locally

### Prerequisites

- R installed locally
- [Quarto](https://quarto.org/) to render the report
- The `data/ARC.sqlite` database included in this repository

### Install R packages

Run this in an R session:

```r
install.packages(c("RSQLite", "glue", "dplyr"))
```

### Configure the database path

Open `main.qmd` and update the `path` variable near the beginning of the file so it points to your local copy of `data/ARC.sqlite`.

```r
path <- "C:/path/to/dsa-bible/data/ARC.sqlite"
```

### Render the report

From the repository root, run:

```bash
quarto render main.qmd
```

You can also open `main.qmd` in RStudio with Quarto support and render it from the editor.

## Data source

The project uses the ARC translation distributed by [damarals/biblias](https://github.com/damarals/biblias). That repository provides biblical texts in multiple formats, including SQLite.

## License

This project is licensed under the [MIT License](LICENSE).