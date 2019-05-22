Fine-mapping eQTL functional enrichment analysis
 
1, RBP binding sites data statistics
RBP binding sites on exons:
7231675 sites for 171 RBPs in  POSTAR
3463192 sites for 36 RBPs in STARBASE2
10189051 sites for 183 RBPs in FIMO
15705977 sites for 118 RBPs in eCLIP

We have checked and find that eCLIP is included in POSTAR database, but not all of them included (about 20%)

Overlap between different datasets, including between FIMO and POSTAR is just about 3-5%

As positive control, we check RBP binding sites overlap between two replicates of eCLIP data, and found 20%-40% overlap


2, eQTL split into 4 bins accoring to PIP scores:
eQ1: top 25%
eQ2: 25-50%
eQ3: 50-75%
eQ4: low 25%

Comparison of functional scores among the different groups was shown in Figure
https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.score.eqtlbins.nocontrol.pdf
  
Comparison of functional scores among the different groups along with control (SNPsnap) was shown in Figure
https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/finemap_eQTL_commonSNPs.anno.score.eqtlbins.pdf

we can see in general eQ1 show high functional score than others and also control, and significant in some cases (ANnova p value shown)


3, Enrichment of the eQTL among functional genomic regions compared to control SNPs (SNPsnap simlations) was calculated, the number of regions show significant eQTL enrichment (p<0.01) and total regions tested is listed as bellow: 

eQTL_bins	#Enriched_regions	#Total_regions_tested	Ratio
Q1	50	2845	0.0175746924428823
Q2	35	2845	0.0123022847100176
Q3	38	2845	0.0133567662565905
Q4	33	2846	0.0115952213633169

we can see Q1 (top25%) eQTLs tend to enriched in more regions than others eQTLs

 
