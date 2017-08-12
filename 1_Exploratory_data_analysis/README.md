Exploratory data analysis
=========================

- Anecdotal evidences vs statistical approaches while tackling the question "do the first babies arrive late?"

- Statistical approach comprises of 
    - Data collection: NSFG survey 
    - Descriptive statistics: Generate and visualize statistics that summarize the data concisely
    - Exploratory data analysis: Look for patterns, dierences, and other features that address the questions we are interested in.
    - Estimation: Estimate characteristics of the general population.
    - Hypothesis testing: Evaluate cause and effect relationship

- NSFG survey
    - Official link: https://www.cdc.gov/nchs/nsfg/index.htm
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
        - https://www.cdc.gov/nchs/nsfg/nsfg_cycle6.htm
    
- Intro to Panda and basics of Python
    - Where is data and how to import data
        - [2002FemPreg.dct](https://github.com/amoghskulkarni/ThinkStats2/blob/master/code/2002FemPreg.dct)
        - The file is in the form of Stata dictionary file. Stata is a statistical software system. The file contains descriptions of 444 columns.
        - 
    - How to use utils/functions given in the code provided by the book [thinkstats2.py](https://github.com/amoghskulkarni/ThinkStats2/blob/master/code/thinkstats2.py)
    