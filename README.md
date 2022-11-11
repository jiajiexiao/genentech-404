# genentech-404

https://www.kaggle.com/competitions/genentech-404-challenge/

Dataset Description
Data Access
All participants are required to sign and adhere to the Data Usage Agreement for the Alzheimer's Disease Neuroimaging Initiative (ADNI) dataset on the LONI website https://ida.loni.usc.edu/collaboration/access/appApply.jsp?project=ADNI. Participants must request access to the database, be aware that approval may take between 3-5 business days. Participants who already have approval to access ADNI through the LONI website, do not need to apply again. PARTICIPANTS SHOULD NOT DOWNLOAD THE COMPETITION DATA UNTIL THE ADNI DATA ACCESS REQUEST HAS BEEN APPROVED BY THE LONI WEBSITE ADMINISTRATORS.

In the Proposed Analysis section, Participants are encouraged to use the following statement:

I am requesting access to the ADNI database in order to participate in Genentech's 404 Challenge on missing data imputation. The goal of the 404 Challenge to develop flexible algorithms to deal with different patterns of missing data in tabular clinical datasets that include demographics, cognitive scores, and MR-derived volumetric measurements.

Files
The training set (dev_set.csv) is a complete dataset with no missing values. Three copies of dev_set.csv are created, dev_1.csv, dev_2.csv, dev_3.csv each with different simulated missingness mechanisms.

The task is to predict the missing values in the test_A.csv and test_B.csv. The solution file should be formatted similarly to the sample_submission.csv. The Id column should include a string with RID_hash , VISCODE , col_name , test_set separated by underscores, for example 7cdf3031d8e8b148faf18742c72e6f21ffd63e9a344f729b9f33c7bd95e69355_90_CDRSB_test_B. The Predicted column should include the predicted value.

Files
```
dev_set.csv - complete training set

dev_1.csv - training set with missing values, missingness mechanism #1

dev_2.csv - training set with missing values, missingness mechanism #2

dev_3.csv - training set with missing values, missingness mechanism #3

test_A.csv - test set with missing values, missingness mechanism A

test_B.csv - test set with missing values, missingness mechanism B

sample_submission.csv - a sample submission file in the correct format, predicting all missing values as the column means
```

Hint: Participants will not be given information about missingness mechanisms A, B but are encouraged to develop algorithms that can characterize the missingness pattern and adapt the imputation approach accordingly.


Columns
Each row in the csv corresponds to a single subject visit. The data is longitudinal and all datasets (training set, public leaderboard set, and private leaderboard set) were split by subject. Ordinal or categorical variables will be treated as continuous during evaluation. Performance will be measured using range normalized mean absolute error (MAE).

Variables that are always observed:
```
RID_hash - unique subject ID
VISCODE - visit code, referring to the number of months
Variables that may have missingness:

AGE - age at that particular visit
PTGENDER_num - sex {0: 'Male', 1: 'Female'}
PTEDUCAT - education level
DX_num - diagnosis {0: 'Cognitively Normal', 1: 'Mild Cognitive Impairment', 2: 'Dementia'}
APOE4 - number of APOE e4 alleles
CDRSB - cognitive score, Clinical Dementia Rating Sum of Boxes
MMSE - cognitive score, Mini‐Mental State Examination
ADAS13 - cognitive score, Alzheimer's Disease Assessment Scale-Cognitive Subscale
Ventricles - ventricle volume
Hippocampus - hippocampus volume
WholeBrain - whole brain volume
Entorhinal - entorhinal volume
Fusiform - fusiform volume
MidTemp - midtemp volume
```
