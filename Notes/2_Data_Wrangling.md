# Udacity Data Analyst Nano Degree

## Part 2: Data Wrangling

### Intro

- Gather

  - Coding to download: scalability and reproducibility (scientific method)

  - Use `with ... as ...` when handling files, to avoid out of memory due to not closing each file used     [Context Manager](https://jeffknupp.com/blog/2016/03/07/python-with-context-managers/)

    - ```python
      with zipfile.ZipFile('armenian-online-job-postings.zip', 'r') as myzip:
          myzip.extractall()
      ```

- Assess (what to clean next)

  - Quality --> dirty (missing / invalid / wrong / inconsistent)
  - Tidiness --> messy (structural issue)
    - One variable per column
    - One observation per row
    - Each type of observational unit forms a table
  - Tools
    - Visual: spreadsheet for small dataset
    - Programmatic: pandas for large dataset
      - `df.head` / `df.tail` / `df.info` / `df.column.value_counts` 
  - Record the assessment result for next step
    - problem only, not action

- Clean

  - Define

    - transform assessment result to pseudo code (cleaning plan)

  - Code

    - start from a copy of original data frame

  - Test

    - ```python
      # Use assert to verify the result programmatically
      for phrase in asap_list:
          assert phrase not in df_clean.StartDate.values
      ```

- Re-assess and Iteration

- Other Ideas

  - Wrangling and EDA (Exploratory data analysis / Feature Engineering)
    - Wrangling will not improve your analysis or modeling, but just make it possible
    - EDA does improve
  - ETL (Extract-Transform-Load Process)
    - For IT user / well-structured data / BI use case, while wrangling is for analysts user / any data / exploratory new data 
    - [Data Wrangling Versus ETL: What’s the Difference?](https://tdwi.org/articles/2017/02/10/data-wrangling-and-etl-differences.aspx)

### Data Gather

