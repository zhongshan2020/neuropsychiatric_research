Fine-mapping eQTL functional enrichment analysis
 
<h1> 1, RBP binding sites data statistics </h1>

RBP binding sites on exons:

7231675 sites for 171 RBPs in  POSTAR

3463192 sites for 36 RBPs in STARBASE2

10189051 sites for 183 RBPs in FIMO

15705977 sites for 118 RBPs in eCLIP

We have checked and find that eCLIP is included in POSTAR database, but not all of them included (about 20%)

Overlap between different datasets, including between FIMO and POSTAR is just about 3-5%

As positive control, we check RBP binding sites overlap between two replicates of eCLIP data, and found 20%-40% overlap


<h1> 2, eQTL split into 4 bins accoring to PIP scores: </h1>

eQ1: top 25%

eQ2: 25-50%

eQ3: 50-75%

eQ4: low 25%

Comparison of functional scores among the different groups was shown in Figure
https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.score.eqtlbins.nocontrol.pdf
  
Comparison of functional scores among the different groups along with control (SNPsnap) was shown in Figure
https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.score.eqtlbins.pdf

we can see in general eQ1 show high functional score than others and also control, and significant in some cases (ANnova p value shown)


<h1> 3, Enrichment of the eQTL among functional genomic regions compared to control SNPs (SNPsnap simlations) </h1> 
 
 the number of regions show significant eQTL enrichment (p<0.01) and total regions tested is listed as bellow: 

eQTL_bins	 #Enriched_regions	 #Total_regions_tested	 Ratio

 Q1	  50	  2845	  0.0175

 Q2	  35	  2845	  0.0123

 Q3	  38	  2845	  0.0133

 Q4	  33	  2846	  0.0115

we can see Q1 (top25%) eQTLs tend to enriched in more regions than others eQTLs

 <h1> 4, Prediction of 3'UTR eQTL against common SNPs using machine learning methods </h1>

<h2> (1), SNP data: </h2>

3,149 eQTL finemapped using DAPG for human brain

66,737 common SNPs matched using SNPsnap (default settings)

<h2> (2), features: </h2>

9 evolution/selection or other funcional features of prediction scores from many diffent software tools: DeepSea, Phylop, CADD, RNAsnp, Eigen,GWAVA for example.  

2,869 functional genome region annotations including: RBP binding sites and miRNA binding sites for specific RBP or miRNAs, and 3'UTR cis-regulatory elements.

<h2> (3), prediction using machinelearning method xgboost, 2 ways to estimate AUC : </h2>

(a), Cross validation

5-fold cross validation on the whole dataset performed to evaluate CV AUC:
 
xgb.cv(data = data[,-ind_label], label = data[,ind_label],nthread = 10, nfold = 5, nrounds=20,verbose=2,metrics={'auc'},objective = "binary:logistic")


(b),train-test

25% data randomly selected as test, and rest 75% as train, to evaluate prediction efficiency and AUC:  

xgboost(data = train[,-ind_label], label = train[,ind_label], nthread = 10, verbose=2, nrounds=20,objective = "binary:logistic")
 

<h2> (4), Analysis 1: Prediction of eQTL using common features: Phylop_score, CADD, Eigen, and GWAVA_region_score only: </h2>

AUC of 0.543 obtained 

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.anno.matr.selfeatures.xgboost.auc.pdf


<h2> (5), Analysis 2: Prediction of eQTL using all features: </h2>

AUC of 0.776 obtained

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.matr.xgboost.auc.pdf

<h2> (6), Analysis 3: Prediction of eQTL with top 25% PIP score using all features: </h2>

AUC of 0.894 obtained

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.anno.matr.q1.xgboost.auc.pdf

 
