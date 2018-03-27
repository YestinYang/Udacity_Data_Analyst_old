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

- Types of Data Source

  - Flat File (like CSV / TSV, structured text file)

    - human readable / easily edit / good for small dataset
    - `pd.read_csv(<path>, [sep='<RegEx>', ...])` 

  - HTML from Web Scrapping

    - Elements

      - ```html
        <p>This is a paragraph.</p>
        <h1>This is a heading.</h1>
        <span>This is a span</span>
        <img src="image.jpg" alt="a picture">
        ```

    - Trees

      - ```html
        <!-- Parent div with child h1 and p -->
        <div>
            <h1>This is a heading.</h1>
            <p>This is a paragraph.</p>
        </div>
        ```

    - `BeautifulSoup` handle html file     [Sample code](../2_Wrangling_Code/gathering_html.ipynb)

  - HTTP via `requests` 

  - TXT File

    - Encoding and Decoding    [The difference between UTF-8 and Unicode?](http://www.polylab.dk/utf8-vs-unicode.html)
      - **ASCII / ANSI:** 8-bits per byte stores one character, which from code 32 to 127, while the content of code 128-255 is defined by different standards
      - **Unicode:** a list of characters with unique numbers (code points)
        - "Hello" has code points as "U+0048 U+0065 U+006C U+006C U+006F"
      - **UTF-8 / UTF-16:** encoding algorithm translating info to binary to store on disk
      - Therefore, when reading a text file, app **decoding** the binary data to number, and translate into character by mapping Unicode
      - In Python, `str` is Unicode itself, `bytes` and `bytearray` needs to be decoding     [What is the difference between a string and a byte string?](https://stackoverflow.com/questions/6224052/what-is-the-difference-between-a-string-and-a-byte-string)

- Ways of Constructing DataFrame

  - From list of dictionary

    - ```python
      df_list.append({'title': title,
                      'score': int(score),
                      'number_of_ratings': int(num_ratings)})
      df = pd.DataFrame(df_list, columns = ['title', 'score', 'number_of_ratings'])
      ```

    -   


