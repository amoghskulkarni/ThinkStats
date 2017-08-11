Exploratory data analysis
=========================

- Anecdotal evidences vs statistical approaches while tackling the question "do the first babies arrive late?"

- Statistical approach comprises of 
    - Data collection: NSFG survey 
    - Descriptive statistics: Generate and visualize statistics that summarize the data concisely
    - Exploratory data analysis: Look for patterns, differences, and other features that address the questions we are interested in.
    - Estimation: Estimate characteristics of the general population.
    - Hypothesis testing: Evaluate cause and effect relationship

- NSFG survey
    - Official link: https://www.cdc.gov/nchs/nsfg/index.html
    - Types of studies
        - Cross-sectional study: snapshot of the group at a point in time (like this one)
        - Longitudinal study: observe a group repeatedly over a period of time
    - Jargon
        - Population: e.g. The target population of the NSFG suvey in the question is people in the US aged 15-44 
        - Sample: Subset of the population
        - Respondants: Individuals participating in the survey
        - Representative sample: The sample such that every member of the population had equal chance of participating
    - NSFG is not representative, it is _oversampled_
    - Codebook and user's guide of the survey contains design of the study, the survey questions and the encoding of the responses
        - https://www.cdc.gov/nchs/nsfg/nsfg_cycle6.html
    
- Intro to Panda and basics of Python
    - Data
        - [2002FemPreg.dct](https://github.com/amoghskulkarni/ThinkStats2/blob/master/code/2002FemPreg.dct)
        - The file is in the form of Stata dictionary file. Stata is a statistical software system. The file contains descriptions of 444 columns.
    - How to use utils/functions given in the code provided by the book 
        - [code](https://github.com/amoghskulkarni/ThinkStats2/blob/master/code/thinkstats2.py)
        - Use `ReadFemPreg()` given in [here](https://github.com/amoghskulkarni/ThinkStats2/blob/master/code/nsfg.py#L41)
            - First argument is the name of the `.dct` file and the second one is the name of `.dat.gz` file
            - This function returns a `DataFrame` object
    - `DataFrame` objects
        - Fundamental data structure provided by pandas
        - Row for a record, column for a variable
        - Also contains the variable names and their types, also provides the methods for accessing and modifying the data
        - The attribute `columns` returns a sequence of column names as Unicode strings
            - e.g. `df.columns` => `Index([u'caseid', u'pregordr', u'howpreg_n', u'howpreg_p', ... ])`
            - The result is an `Index`, can be treated as list
            - `df.columns[1]` => `'pregordr'`
        - To access a column, use the column name as the key
            - e.g. `df['pregordr']` => `...`
            - The results is a `Series`, can be treated as a list
            - `df['pregordr'][0]` => `1`
        - Can also access the columns of a DataFrame using dot notation
            - `pregorder = df.pregordr`
            - Only works if the column name is a valid Python identifier
    - Variables
        - Columns and what they represent
        - Some are from raw data and some are derived
    - Transformation
        - Data cleaning
        - [`CleanFemPreg()`](https://github.com/amoghskulkarni/ThinkStats2/blob/master/code/nsfg.py#L56) function cleans the variables
            - `df.agepreg /= 100.0` is dividing all the records in `agepreg` column by 100.0
            - `replace()` method replaces special values
                - `df.birthwgt_lb.replace(na_vals, np.nan, inplace=True)` where `na_vals = [97, 98, 99]`
        - You can add a new column
            - Correct way to add a column is `df['column_name'] = ...` and not `df.column_name = ...`
    - Validation
        