Prediction of fine-mapping eQTL using xgboost
The trian dataset used same as above, briefly, 3,149 eQTL as positive, and 66,737 common SNPs (matched by SNPsnap) as negative, in total 2,934 features (mainly including RBP bidning, miRNA binding).

The xgboost was used for outcome prediction based on features, using the objective method: "binary:logistic" and loss function metrics: "Precison recall auc", 5-fold CV to estimate performance.

Two analysis performed with different instance weight to show whether higher PIP score for eQTLs can indicate more reliable eQTLs:

<h2> a, same instance weight: </h2>

AUC curve:

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.matr.xgb_train_AUC.aucpr.pdf


outcome (eQTL/common SNPs) vs predictions (>0.5 as positive):

||Pred:0|Pred:1|
|--|--|--|	
|Obs:0|36163|30574|
|Obs:1|302|2847|

Feature importance (top 200 shown):

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.matr.xgb_train_featureImportance.aucpr.pdf


relationship between PIP score vs Prediction probability:

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.pred.pip.cor.pdf


b, PIP score as instance weight for positive (eQTL), and arbitarily chosen 0.01 for negative (common SNPs):

AUC curve:

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.snps.anno.matr.instancewt.xgb_train_AUC.aucpr.pdf


outcome (eQTL/common SNPs) vs predictions (>0.5 as positive):

||Pred:0|Pred:1|
|--|--|--|	
|Obs:0|66732|5|
|Obs:1|3136|13|


Feature importance (top 200 shown):

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.snps.anno.matr.instancewt.xgb_train_featureImportance.aucpr.pdf
  
