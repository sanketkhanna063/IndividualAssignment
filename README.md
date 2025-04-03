# **Data 1202: Data Analytics Tools**  
## **Lab 6 - Data Merging and Analysis with Pandas**  

### **Project Overview**  
This project explores **data manipulation using Pandas**, focusing on **merging datasets, handling missing values, and filtering data**. The dataset includes **movies, financials, taglines, genres, and actor lists from the Iron Man movie series**. The primary objective is to understand different types of joins (**left, right, inner, outer**) and their impact on datasets.  

---

## **Getting Started**  

### **Prerequisites**  
Before running the code, ensure you have the following installed:  

- **Python 3.x**  
- **Pandas library**  

To install Pandas, run:  
```bash
pip install pandas
```

### **Installing**  
1. **Clone the repository:**  
   ```bash
   git clone <repository_link>
   cd <repository_name>
   ```
2. **Ensure the required CSV files are present:**  
   - `movies.csv`  
   - `financials.csv`  
   - `taglines.csv`  
   - `movie_to_genres.csv`  
   - `iron1.csv`  
   - `iron2.csv`  

---

## **Project Details**  

### **1. Merging Movies and Financial Data**  
- **Loads the `movies.csv` and `financials.csv` datasets**  
- **Performs a left join on `id` to merge financials into the movies dataset**  
- **Counts the number of missing values in financial data**  
- **Displays the first few rows of the merged dataset**  

### **2. Comparing Left Join vs. Inner Join with Taglines**  
- **Loads the `taglines.csv` dataset**  
- **Performs both left and inner joins with `movies.csv`**  
- **Counts the number of missing taglines**  

### **3. Filtering Science Fiction Movies**  
- **Loads the `movie_to_genres.csv` dataset**  
- **Filters for movies in the "Science Fiction" genre**  
- **Merges with movies dataset to get additional details**  

### **4. Finding Actors in Only One of the Iron Man Movies**  
- **Loads actor lists for Iron Man 1 (`iron1.csv`) and Iron Man 2 (`iron2.csv`)**  
- **Uses an outer join to find actors who were in one movie but not the other**  

---

## **Running the Code**  
To execute the script, use the following command in the terminal:  

```bash
python script.py
```

---

## **Running the Tests**  

To verify the correctness of the script, you can include test cases such as:  

1. **Checking if datasets load correctly:**  
   ```python
   assert not movies.empty, "Movies dataset failed to load!"
   assert not financials.empty, "Financials dataset failed to load!"
   ```

2. **Verifying merge operations:**  
   ```python
   assert 'budget' in movies_financials.columns, "Financials merge unsuccessful!"
   assert 'tagline' in movies_left.columns, "Tagline merge unsuccessful!"
   ```

3. **Ensuring missing values are correctly counted:**  
   ```python
   assert missing_values >= 0, "Error in missing data count!"
   ```

---

## **Deployment**  
This project is for **educational purposes** and is not intended for production use.  

---

## **Author**  
**[Your Name]**  
- GitHub: [Your GitHub Profile]  
- Email: [Your Email]  

---

## **License**  
This project is licensed under the **MIT License**.  

---

## **Acknowledgments**  
- **Pandas Documentation:** [pandas.pydata.org](https://pandas.pydata.org/)  
- **Dataset Sources:** Educational datasets on movies and actors  

