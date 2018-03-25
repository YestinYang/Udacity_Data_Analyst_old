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

- ​