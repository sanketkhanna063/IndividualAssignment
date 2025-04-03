# Data 1202: Data Analytics Tools

## Project Title
Lab 6 - Data Merging and Analysis with Pandas

## Short Description
This project involves analyzing and merging datasets using the pandas library in Python. The code demonstrates various join operations such as left joins, inner joins, and outer joins to enrich datasets, detect missing values, and identify differences between datasets.

## Getting Started

### Prerequisites
- Python 3.x
- pandas library
- CSV files: `movies.csv`, `financials.csv`, `taglines.csv`, `movie_to_genres.csv`, `iron1.csv`, `iron2.csv`

### Installing
1. Clone the repository:
   ```sh
   git clone <repository_link>
   ```
2. Navigate to the project directory:
   ```sh
   cd <project_directory>
   ```
3. Install the required dependencies:
   ```sh
   pip install pandas
   ```

## Running the Code
Run the Python script to process and analyze the datasets:
```sh
python lab6.py
```

## Breakdown of Code

### 1. Merging Movies and Financial Data
- Loads movie data (`movies.csv`) and financial data (`financials.csv`).
- Performs a left join to merge financial information with movie details.
- Identifies missing financial data.

```python
import pandas as pd
movies = pd.read_csv('movies.csv')
movies.head()
financials = pd.read_csv('financials.csv')
financials.head()
movies_financials = movies.merge(financials, on='id', how='left')
number_of_missing_fin = movies_financials['budget'].isnull().sum()
print(f"Number of movies missing rows: {number_of_missing_fin}")
```

### 2. Enriching Movies with Taglines
- Performs a left join to merge movie titles with taglines.
- Compares the results with an inner join to observe missing data.

```python
movies = pd.read_csv("movies.csv")
taglines = pd.read_csv("taglines.csv")
movies_left = movies.merge(taglines, on='id', how='left')
movies_inner = movies.merge(taglines, on='id', how='inner')
missing_taglines = movies_left['tagline'].isnull().sum()
print(f"Number of movies missing a tagline: {missing_taglines}")
```

### 3. Filtering Science Fiction Movies
- Extracts movies of the "Science Fiction" genre.
- Merges genre data with the movies dataset to get complete information.

```python
genres = pd.read_csv("movie_to_genres.csv")
sci_fi_only = genres[(genres["genre"] == "Science Fiction")].merge(movies, left_on="movie_id", right_on="id", how="left")
print(sci_fi_only.head())
```

### 4. Identifying Unique Actors between Two Movies
- Loads actor data for Iron Man 1 and Iron Man 2.
- Performs an outer join to find actors who appeared in only one of the two movies.

```python
iron_1_actor = pd.read_csv("iron1.csv")
iron_2_actor = pd.read_csv("iron2.csv")
iron_1_and_2 = iron_1_actor.merge(iron_2_actor, on='id', how='outer', suffixes=('_1','_2'))
m = ((iron_1_and_2['name_1'].isnull()) | (iron_1_and_2['name_2'].isnull()))      
print(iron_1_and_2[m])
```

## Deployment
This project is intended for educational purposes and can be executed in a local Python environment.

## Author
Your Name

## License
This project is licensed under the MIT License.

## Acknowledgments
- Data sourced from open movie datasets.
- Pandas documentation for merge operations.

