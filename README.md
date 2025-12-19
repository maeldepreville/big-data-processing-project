# Big Data Processing Project

IMDB data analysis and real-time Wikipedia stream processing.

## Overview

### 1. IMDB Data Analysis

Analysis of IMDB datasets (movies, actors, crew, ratings) using PySpark.

**Datasets used:**
- `name.basics.tsv.gz` - People information
- `title.basics.tsv.gz` - Basic title information
- `title.ratings.tsv.gz` - Ratings and votes
- `title.crew.tsv.gz` - Production crew
- `title.akas.tsv.gz` - Alternative titles
- `title.episode.tsv.gz` - TV series episodes

**Key findings:**
- 11.4M people in dataset
- 95.58% missing birth dates
- Film durations: shortest movie 1 min, longest short 97 min
- 28 distinct genres identified
- Highest rated comedy: Itlu Me Yedava (9.7/10)

### 2. Wikipedia Stream Processing

Real-time monitoring of Wikipedia edits for 5 IMDB entities.

**Tracked entities:**
- Christopher Nolan (director)
- The Shawshank Redemption (movie)
- Leonardo DiCaprio (actor)
- Star Wars (franchise)
- Science fiction (genre)

**Metrics collected:**
- Edit count per entity
- Unique editors count
- Last edit timestamp

**Alert system:**
- Triggers alert every 5 edits
- Saved to `alerts.json`

**Output files:**
- `stream_metrics.json` - Overall metrics
- `alerts.json` - High-frequency edit alerts

## Tech Stack

- **PySpark** - Distributed data processing
- **pywikibot** - Wikimedia EventStreams API integration
- **Java 17** - Spark runtime
- **Python 3.13** - Execution environment

## Usage

1. Install dependencies:
```bash
pip install pyspark pywikibot requests-sse
```

2. Configure JAVA_HOME (Java 17 required):
```bash
export JAVA_HOME=/path/to/java17
```

3. Run the notebook:
```bash
jupyter notebook notebook.ipynb
```

## Results

Analysis results are available in the notebook. Stream processing generates two JSON files with real-time metrics and alerts.
