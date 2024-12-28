In this work, we propose the ‘FairGenerate,’ a pre-processing method that addresses imbalanced data and biased labels from the training dataset. 
We implemented FairGenerate and all baselines using Python 3.10.11. 

We utilized nine publicly available datasets. All datasets are available in the **Dataset** folder, except below, which were excluded due to size limitations.

They can be obtained from the below URLs.

**MEPS15** - https://gitlab.liris.cnrs.fr/otouat/MEPS-HC/-/blob/main/h181.csv <br />
**MEPS16** - https://gitlab.liris.cnrs.fr/otouat/MEPS-HC/-/blob/main/h192.csv

********************************************************************************************************

1. Adult Income dataset - http://archive.ics.uci.edu/ml/datasets/Adult
2. COMPAS - https://github.com/propublica/compas-analysis
3. German Credit - https://archive.ics.uci.edu/ml/datasets/Statlog+%28German+Credit+Data%29
4. Bank Marketing - https://archive.ics.uci.edu/ml/datasets/bank+marketing
5. Default Credit - https://archive.ics.uci.edu/ml/datasets/default+of+credit+card+clients
6. Heart - https://archive.ics.uci.edu/ml/datasets/Heart+Disease
7. MEPS15 - https://meps.ahrq.gov/mepsweb/
8. MEPS16 - https://meps.ahrq.gov/mepsweb/
9. Student - https://archive.ics.uci.edu/ml/datasets/Student+Performance

********************************************************************************************************

**The replicate folder contains the codes to replicate our results.**
**Replicate Package** -  [[https://drive.google.com/drive/folders/1AUKoHZ2sPWzTogNX4YV9D9hJPymHWIQV?usp=sharing]]
**Results** - https://drive.google.com/drive/folders/1X3RdUNN07Vcum1Sh7HpUKCMfTrQ_HHC6 

The codes in the folder are named for the applicable scenarios. The Adult and COMPAS data sets include two protected attributes, so we divide them into two scenarios: Adult_sex and Adult_race, similarly COMPAS_sex and COMPAS_race.

<h1> Code description</h1>

In the above replicate package -
* <b>generated_data</b> folder contains the final synthetic data samples produced by the proposed approach, which were used to report the results.
* <b>FairGenerate.py </b> contains the code of the proposed approach to generate synthetic data samples.
* For each scenario, a Jupyter notebook is provided, allowing for the replication of results. Directly running them will result in the replication of results
* <b>Stats.py</b> file contains the code of Scott-Knott results.

********************************************************************************************************

Baselines
-----------------------------------------------------
**Fair-Smote: Proposed in the paper: Bias in Machine Learning Software: Why? How? What to Do?**
Fair-Smote is a pre-processing method that uses the modified SMOTE method to make the distribution of sensitive features in the data set consistent, and then deletes biased data through situation testing.
We use the code they provided in the code repository: https://github.com/joymallyac/Fair-SMOTE

**FairMask: Proposed in the paper: FairMask: Better Fairness via Model-Based Rebalancing of Protected Attributes**
Fairway is a hybrid algorithm that combines pre-processing and post-processing methods. 
We use the code they provided in the code repository: https://github.com/anonymous12138/biasmitigation 

**LTDD: Linear Regression Based Training Data Debugging**
LTDD is preprocessing algorithm that finds and removes the biased portion present in the features of the training data.
We use the code they provided in the code repository: https://github.com/fairnesstest/LTDD

**MirrorFair**
MirrorFair is a preprocessing method that employs an ensemble approach to address fairness issues, grounded in the principles of
counterfactual inference. It creates a counterfactual dataset from the original dataset and trains two
separate models, one on the original dataset and the other on the counterfactual dataset. Finally, it
adaptively combines the predictions from both models to produce fairer final decisions.
We use the code they provided in the code repository: https://github.com/XY-Showing/FSE2024-MirrorFair
 
**Reweighing: Data preprocessing techniques for classification without discrimination**
Reweighing is a pre-processing method that calculates a weight value for each data point based on the expected probability and the observed probability, to help the unprivileged class have a greater chance of obtaining favorable prediction results. 
We use the following python's AIF360 module to achieve it:

<code>from aif360.algorithms.preprocessing import Reweighing</code>
-----------------------------------------------------

The following folder contains an Excel sheet that contains the Scott-Knott Test analysis for Logistic Regression, Decision Tree, Support Vector Machine, and Deep Learning Models Used in this study. 

https://drive.google.com/drive/folders/1X3RdUNN07Vcum1Sh7HpUKCMfTrQ_HHC6
