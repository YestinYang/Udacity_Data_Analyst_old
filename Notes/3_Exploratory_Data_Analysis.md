# Udacity Data Analyst Nano Degree

## Part 3: Exploratory Data Analysis

> Keep curious and skeptical about data, test and develop intuitions of data

### Basic Commands

- `c()` — vector object, containing arguments

  - ```R
    numbers <- c(1:10)
    numbers <- c(numbers, 11:20)
    ```

- `nchar()` — count the number of each characters

  - ```R
    udacious = c("Chris Saden", "Lauren Castellano", "Sarah Spikes")
    mystery = nchar(udacious)
    ```

- Subsetting

  - ```R
    udacious[mystery == 11]
    ```

- `data()` — load data

- `str()` — display the structure of R object, like `info()` in Python

- `dim()` — size of R object

- `names()` — output all variable names in dataset

- `row.names()` — get and rename variable names

  - ```R
    row.names(mtcars)
    row.names(mtcars) <- c(1:32)  # rename
    ```

- `head()` — first 5 rows

- `tail()` — last 5 rows

- `$` — display particular variable

  - ```R
    mtcars$cyl
    ```

- `mean()` — average

- `?[any command]` — help doc of command



----

### Reference:

1. [Interactive Conditional Probability](http://setosa.io/conditional/)
2. 