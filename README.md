Goal:
 Create a Streamlit web application that performs an OLAP analysis of U.S. Non-Farm Payrolls data stored in a PostgreSQL database.
 The app must answer these business questions with interactive visualizations and the ability to show or explain the SQL logic behind the scenes.
Functional Requirements
Database & Data Handling


Connect to PostgreSQL using psycopg2.


Read the nonfarm_payrolls table into a pandas DataFrame.


Cache the data with @st.cache_data to avoid repeated queries.


Convert the date column to datetime.


Custom UI/UX


Use Streamlit with a sidebar navigation to select one of four OLAP operations: Slicing, Dicing, Roll-up, and Drill-Down.


Inject a small CSS block to give a light background, centered header, subtle shadows for charts/tables, and a clean, modern look.


Display helpful success/error messages if the database connection succeeds or fails.


Analyses & Visuals (use Plotly Express)


Slicing


Question 1: Average total payroll employment for each calendar year (2010–2025).


Question 2: Monthly employment levels from March–December 2020 compared with the same months in 2019.


Dicing


Question 1: Identify months where employment dropped more than 2 % month-over-month, and calculate how many months it took to return to the prior peak.


Question 2: Within Q4 (Oct–Dec) of each year, find which month consistently shows the highest payroll growth.


Roll-up


Question 1: Aggregate total payroll employment by quarter and by year, showing quarter-over-quarter and year-over-year growth rates.


Question 2: Compare average employment in the 2010s vs. the 2000s.


Drill-Down


Question 1: For the year with the highest annual employment gain, show which months contributed most to that gain.


Question 2: Identify the month with the sharpest drop and explain that a weekly breakdown is not possible because the dataset is monthly.


Implementation Details


Organize the code into clear, reusable functions:


load_data() (database query & caching)


add_custom_css() (styling)


create_slicing_charts(df), create_dicing_charts(df), create_rollup_charts(df), create_drilldown_charts(df)


main() to tie everything together.


Show any key SQL snippets used for the underlying questions as comments or in expandable sections for educational purposes.


Use environment variables (DB_NAME, DB_USER, DB_PASSWORD, DB_HOST) for database credentials, with defaults for local testing.


Output Format


Deliver a single Python file, ready to run with streamlit run dashboard.py.


Include concise comments so another analyst can quickly understand each block.


Deliverable:
 A complete Python script that meets the above requirements and is ready to deploy as a Streamlit app.
