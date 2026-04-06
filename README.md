# 🎬 IMDb Movie Data Analysis & Visualization

## 📌 Project Overview
This project involves a comprehensive data analysis of over 5,000 movies using the IMDb dataset. The objective was to clean, transform, and visualize the data to extract meaningful insights regarding cinematic trends, box office profitability, director performance, and global market reach. The final output is a highly interactive, cinematic-themed Power BI dashboard that allows users to explore movie statistics dynamically.

## 🛠️ Tools & Technologies Used
* **Data Cleaning & Preprocessing:** Microsoft Excel
* **Data Modeling & Visualization:** Microsoft Power BI
* **Languages:** DAX (Data Analysis Expressions)

## 🧹 Data Cleaning (Excel)
Before importing the data into Power BI, the raw `movie_metadata-DATASET.csv` was rigorously cleaned in Excel to ensure accuracy:
* **Handling Missing Values:** * Replaced blank or null 'Title Year' fields with a `1900` placeholder to maintain data integrity without breaking timeline visuals.
  * Replaced empty text fields (e.g., Director Name, Language) with "Unknown".
  * Filled missing duration and aspect ratio metrics using median/mode values where appropriate.
* **Formatting:** Standardized text formatting, removed trailing spaces, and ensured financial columns (Gross, Budget) were formatted as currency/numeric.

## 🧮 Data Modeling & DAX Measures
In Power BI, custom DAX measures were created for dynamic calculations:
* `Total Movies = COUNT(movie_metadata[Movie Title])`
* `Total Gross = SUM(movie_metadata[Gross])`
* `Total Budget = SUM(movie_metadata[Budget])`
* `Total Profit = [Total Gross] - [Total Budget]`
* `Total Countries = DISTINCTCOUNT(movie_metadata[Country])`

## 📊 Dashboard Visualizations
The dashboard features a premium, dark "IMDb-style" theme across two interactive pages:

### **Page 1: Global Box Office Overview**
* **KPI Cards:** High-level metrics displaying Total Profit, Total Movies, Total Countries, and Total Budget.
* **Map Visual:** *Box Office Gross by Country* – Shows global revenue distribution.
* **Treemap:** *Top 30 Blockbusters by Genre* – Highlights highest-grossing genres.
* **Clustered Bar Chart:** *Top 10 Directors by Box Office Gross* – Identifies the most commercially successful directors.
* **Line Chart:** *Total Box Office Gross by Year* – Tracks historical revenue trends.
* **Donut Chart:** *Movies by Content Rating* – Shows distribution across R, PG-13, PG, etc.
* **Matrix:** *Financial Performance by Language* – Displays Gross, Budget, and Movie Count by language using Data Bars.

### **Page 2: Director Drill-Through Profile**
* A dedicated drill-through page allowing users to right-click on a director to view their portfolio, dynamic KPIs, and detailed movie lineup.

## 💡 Key Insights
1. **USA Dominates the Market:** The United States accounts for the vast majority of global box office gross.
2. **Top Directors:** Directors like Steven Spielberg and Peter Jackson consistently yield the highest box office returns.
3. **Genre Profitability:** Action, Adventure, and Sci-Fi are the leading genres in the Top 30 Blockbusters treemap.
4. **Content Rating Trends:** R and PG-13 are the most produced content ratings in this dataset.

## 🚀 How to Use This Repository
1. Clone the repository to your local machine.
2. Open `movie_metadata -CLEANED.xlsx` to view the processed dataset.
3. Open `Movie Metadata-DASHBOARD.pbix` in **Power BI Desktop**.
4. Interact with the dashboard by using the slicers or clicking on specific visual elements to cross-filter the data.

## 📁 Files Included
* `movie_metadata-DATASET.csv` - The original raw dataset.
* `movie_metadata -CLEANED.xlsx` - The cleaned dataset used for modeling.
* `Movie Metadata-DASHBOARD.pbix` - The Power BI project file.
* `DASHBOARD PG1.png` & `DASHBOARDS PG2.jpg` - Images of the final dashboard.
