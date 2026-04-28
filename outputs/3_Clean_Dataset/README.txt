========================================================
CLEAN DATASET — Adult Income (after preprocessing)
========================================================

Source file  : adult_income_cleaned.csv
Rows         : 48,842
Columns      : 15 (14 features + 1 target)
Missing vals : 0 (all imputed)

This file contains the fully preprocessed version of the
Adult Income dataset used as input to all experiments in
the thesis. Preprocessing was applied in a leak-free
manner (imputers and encoders fit on training data only).

--------------------------------------------------------
PREPROCESSING STEPS APPLIED
--------------------------------------------------------

1. MISSING VALUE IMPUTATION (Numerical)
   - Strategy : Median imputation (sklearn SimpleImputer)
   - Applied to: age, fnlwgt, education-num, capital-gain,
                 capital-loss, hours-per-week
   - Fit on   : training split only; applied to val/test

2. MISSING VALUE IMPUTATION (Categorical)
   - Strategy : Mode (most frequent) replacement for '?'
   - Applied to: workclass, occupation, native-country

3. CATEGORICAL ENCODING
   - Method   : Label Encoding (sklearn LabelEncoder)
   - Each category mapped to a unique integer index
   - Used as integer indices for embedding lookup layers
     (NOT one-hot encoded)
   - Fit on   : training split only

4. TARGET ENCODING
   - <=50K  ->  0
   - >50K   ->  1

5. DATA SPLITTING (stratified, fixed seed=42)
   - Train : 34,188 samples (70%)
   - Val   :  4,885 samples (10%)
   - Test  :  9,769 samples (20%)

Note: Numerical features are NOT scaled in this file.
Each model wrapper applies its own StandardScaler
(fit on the training fold only) to prevent data leakage.

--------------------------------------------------------
COLUMN DESCRIPTIONS (after encoding)
--------------------------------------------------------

Column              Type       Values / Encoding
------------------  ---------  ----------------------------------
age                 Numerical  Continuous (imputed)
workclass           Integer    0-7  (label encoded, 8 categories)
fnlwgt              Numerical  Continuous (imputed)
education           Integer    0-15 (label encoded, 16 categories)
education-num       Numerical  Continuous (imputed)
marital-status      Integer    0-6  (label encoded, 7 categories)
occupation          Integer    0-13 (label encoded, 14 categories)
relationship        Integer    0-5  (label encoded, 6 categories)
race                Integer    0-4  (label encoded, 5 categories)
sex                 Integer    0-1  (label encoded, 2 categories)
capital-gain        Numerical  Continuous (imputed)
capital-loss        Numerical  Continuous (imputed)
hours-per-week      Numerical  Continuous (imputed)
native-country      Integer    0-40 (label encoded, 41 categories)
income              Integer    0 = <=50K, 1 = >50K (target)

--------------------------------------------------------
CLASS DISTRIBUTION
--------------------------------------------------------
  0 (<=50K) : 37,155 samples (76.1%)
  1 (>50K)  : 11,687 samples (23.9%)

========================================================
