# 🎬 IMDb Movie Data Analysis & Visualization

## 📌 Project Overview
This project involves a comprehensive data analysis of over 5,000 movies using the IMDb dataset. The objective was to clean, transform, and visualize the data to extract meaningful insights regarding cinematic trends, box office profitability, director performance, and global market reach. The final output is a highly interactive, cinematic-themed Power BI dashboard that allows users to explore movie statistics dynamically.

## 🛠️ Tools & Technologies Used
* **Data Cleaning & Preprocessing:** Microsoft Excel
* **Data Modeling & Visualization:** Microsoft Power BI
* **Languages:** DAX (Data Analysis Expressions)

## 🧹 Data Cleaning (Excel)
Before importing the data into Power BI, the raw `movie_metadata.csv` was rigorously cleaned in Excel to ensure accuracy:
* **Handling Missing Values:** * Replaced blank or null 'Title Year' fields with a `1900` placeholder to maintain data integrity without breaking timeline visuals.
  * Replaced empty text fields (e.g., Director Name, Language) with "Unknown".
  * Filled missing Duration and aspect ratio metrics using median/mode values where appropriate.
* **Formatting:** Standardized text formatting, removed trailing spaces, and ensured financial columns (Gross, Budget) were formatted as currency/numeric.
* **Data Validation:** Removed duplicate movie entries and inconsistent records to ensure accurate aggregations.

## 🧮 Data Modeling & DAX Measures
In Power BI, a star-schema-like approach was taken (if multiple tables) and custom DAX measures were created for dynamic calculations:
* `Total Movies = COUNT(movie_metadata[Movie Title])`
* `Total Gross = SUM(movie_metadata[Gross])`
* `Total Budget = SUM(movie_metadata[Budget])`
* `Total Profit = [Total Gross] - [Total Budget]`
* `Total Countries = DISTINCTCOUNT(movie_metadata[Country])`

## 📊 Dashboard Visualizations
The dashboard was designed with a premium, dark "IMDb-style" theme. It includes two main interactive pages:

### **Page 1: Global Box Office Overview**
* **KPI Cards:** High-level metrics displaying Total Profit ($21bn), Total Movies (4,811), Total Countries (66), and Total Budget.
* **Map Visual:** *Box Office Gross by Country* – Shows revenue distribution globally, with bubble sizes indicating gross revenue.
* **Treemap:** *Top 30 Blockbusters by Genre* – Highlights the highest-grossing genres and movies.
* **Clustered Bar Chart:** *Top 10 Directors by Box Office Gross* – Identifies the most commercially successful directors (e.g., Steven Spielberg, Peter Jackson).
* **Line Chart:** *Total Box Office Gross by Year* – Tracks the historical trend of movie revenue over the decades.
* **Donut Chart:** *Movies by Content Rating* – Shows the volume distribution across R, PG-13, PG, etc.
* **Matrix:** *Financial Performance by Language* – Displays Gross, Budget, and Movie Count by language, enhanced with conditional formatting (Data Bars).

### **Page 2: Director Drill-Through Profile**
* A dedicated drill-through page allowing users to right-click on any director (e.g., Steven Spielberg) and view their specific portfolio.
* Includes dynamic KPIs for the selected director and a detailed table of their movie lineup, highlighting individual movie gross and IMDB scores.

## 💡 Key Insights
1. **USA Dominates the Market:** The geographic map highlights that the United States accounts for the vast majority of global box office gross.
2. **Top Directors:** Directors like Steven Spielberg and Peter Jackson consistently yield the highest box office returns.
3. **Genre Profitability:** Action, Adventure, and Sci-Fi are the leading genres in the Top 30 Blockbusters treemap, indicating high audience demand for visually spectacular films.
4. **Content Rating Trends:** R and PG-13 are the most produced content ratings in this dataset.

## 🚀 How to Use This Repository
1. Clone the repository to your local machine.
2. Open `movie_metadata cleaned -Akash M.xlsx` to view the processed dataset.
3. Open `Movie Metadata-Akash M.pbix` in **Power BI Desktop**.
4. Interact with the dashboard by using the "Select Year" and "Select Genre" slicers on the left panel, or click on specific visual elements to cross-filter the data.

## 📁 Files Included
* `movie_metadata-DATASET.csv` - The original raw dataset.
* `movie_metadata cleaned -Akash M.xlsx` - The cleaned dataset used for modeling.
* `Movie Metadata-Akash M.pbix` - The Power BI project file.
* `Screenshots/` - Images of the final dashboard pages.
