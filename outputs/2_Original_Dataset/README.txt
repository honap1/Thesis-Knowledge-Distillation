========================================================
ORIGINAL DATASET — Adult Income (Census Income)
========================================================

Source       : UCI Machine Learning Repository / OpenML
OpenML ID    : 1590
URL          : https://www.openml.org/d/1590
Original UCI : https://archive.ics.uci.edu/ml/datasets/adult
Donor        : Ronny Kohavi and Barry Becker (1996)

File         : adult_income_original.csv
Rows         : 48,842
Columns      : 15 (14 features + 1 target)
Missing vals : 6,465 cells (stored as NaN; original UCI used '?')

--------------------------------------------------------
DATA DICTIONARY
--------------------------------------------------------

Column              Type         Description
------------------  -----------  ------------------------------------------
age                 Numerical    Age of the individual (years)
workclass           Categorical  Employment type
                                 (Private, Self-emp-not-inc, Self-emp-inc,
                                  Federal-gov, Local-gov, State-gov,
                                  Without-pay, Never-worked)
fnlwgt              Numerical    Final weight — census sampling weight
education           Categorical  Highest level of education attained
                                 (Bachelors, Some-college, 11th, HS-grad,
                                  Prof-school, Assoc-acdm, Assoc-voc, 9th,
                                  7th-8th, 12th, Masters, 1st-4th, 10th,
                                  Doctorate, 5th-6th, Preschool)
education-num       Numerical    Education level as an ordinal integer (1-16)
marital-status      Categorical  Marital status
                                 (Married-civ-spouse, Divorced,
                                  Never-married, Separated, Widowed,
                                  Married-spouse-absent, Married-AF-spouse)
occupation          Categorical  Occupation type
                                 (Tech-support, Craft-repair, Other-service,
                                  Sales, Exec-managerial, Prof-specialty,
                                  Handlers-cleaners, Machine-op-inspct,
                                  Adm-clerical, Farming-fishing,
                                  Transport-moving, Priv-house-serv,
                                  Protective-serv, Armed-Forces)
relationship        Categorical  Relationship status within household
                                 (Wife, Own-child, Husband, Not-in-family,
                                  Other-relative, Unmarried)
race                Categorical  Race
                                 (White, Asian-Pac-Islander,
                                  Amer-Indian-Eskimo, Other, Black)
sex                 Categorical  Sex (Male, Female)
capital-gain        Numerical    Capital gains income (USD)
capital-loss        Numerical    Capital losses (USD)
hours-per-week      Numerical    Average hours worked per week
native-country      Categorical  Country of origin (43 categories)
income              Target       Annual income bracket
                                 (<=50K or >50K)

--------------------------------------------------------
MISSING VALUES
--------------------------------------------------------
Columns with missing values (NaN):
  workclass       : ~1,836 missing
  occupation      : ~1,843 missing
  native-country  :   ~583 missing

--------------------------------------------------------
CLASS DISTRIBUTION
--------------------------------------------------------
  <=50K  :  37,155 samples (76.1%)
  >50K   :  11,687 samples (23.9%)

--------------------------------------------------------
CITATION
--------------------------------------------------------
Kohavi, R. (1996). Scaling up the accuracy of naive-bayes
classifiers: A decision-tree hybrid. KDD.
Available via UCI ML Repository and OpenML (ID 1590).
========================================================
