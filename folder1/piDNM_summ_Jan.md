                                                piDNM analysis summary
                                                      (by ZSL)


Aim: overenrichment of DNMs within post-transcriptional regulatory sites (mainly RBP binding and RNA structure changes)

Overall Desigin: 

Breifly, we compare the counts of DNMs within each coding region against that of synonymous regions for DNM overenrichment estimates. We split the coding genes into several different gene sets according to functional annotations as for relation with human diseases and split the coding regions/sites into disjoint categories. DNM overenrichment estimates were performed for different genesets and different sites and compared. We have tried different ways of gene set and sites spliting, and different enrichment testing methods (supplied if requested), however the results are quite similar as bellow.

Methods:
1, To estimate DNM overenrichment on possible post-transcriptional functional sites (including RBPbiding and Ribsnitch sites) and for different mutation effect sites specifically, we split the coding regions into the following 7 main different regions: 

LOF (stop-gain/loss, and consensus splicing sites), 

damaging missense (nonsynonymous predicted to be deleterious by Polyphen), 

potential splicing sites (predicted by spidex), 

RBP binding sites (from CLIPdb and Starbase2 databases),

RIbosnitch (RNAsnp-M3, fdr<0.05), 

normal nonsynonymous regions (excluding damaging ones) 

and synonymous regions. 

The hierachy for overlapping annotations is : LOF, damaging missense, potential splicing sites, RBP binding, Ribosnitch, normal nonsynonymous and synonymous 
 
2, For each WES dataset, DNM overenrichent in each regions were compared against synonymous mutation regions, and the expected mutation rate were calculated from background mutation rate, then Binomial test were used for enrichment significnace and ratio calculation, 95% confidence interval for enrichment ratio also estimated; 

3, for WGS dataset, we compare DNM rate in each genomic region in Case vs Control samples, and to DNM rate in synonymous mutation regions in Case vs Control were used as background, similarly binomial test were used for enrichment significnace and ratio calculation, 95% confidence interval for enrichment ratio also estimated;


Data:
1, 25,035 SNV DNMs from about 50 neuropsychiatric WES and WGS studies (including ASD, EE, SCZ et al);

2, 9,657,613 and 8,453,935 RBPbinding sites collected from CLIPdb and Starbase2 databases; 

3, 8,005,040 predicted mutations on refGenes exon regions by RNAsnp software tool (Mode3, p value <=0.05); 

4, predicted possible splicing change mutations on transcriptome by sipdex software tool and other mutation effects (like Polyphen, CADD etc.) were annotated using the annovar software tool;

5, genome-wide DNM mutation rate data were obtained from the published work by Jedidiah Carlson, which cover about 73% of whole human genome (hg19);

6, neuron-psychiatric genes were obtain from TADA predictions(FDR<0.3), AutismKB FMRP targets, CHD8 target G2Cdb etc collected in Donna M. Werling's published work. 

7, Nonmental genes downloaded from Arjun Krishnan's work was defined as those not related to neuropsychaitric diseases based on OMIM record and used as nagative control;

8, gene expression in embryonic human brain were obtained from the branspan databases, and mean expression level across genomci regions/developmental stages in the lower 10% were taken as not expressed in brain. 

Main results:
DNM enrichment analysis using WES datasets (only several WES datasets with > 500 disease families presented) 

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.WES.dnm.enrich.pdf

DNM enrichment analysis using WGS datasets (only several WGS datasets with > 500 disease families and with proban and sibling presented) 

https://github.com/lalzs1982/neuropsychiatric_research/blob/master/folder1/tt.WGS.dnm.enrich.pdf

Figure legends:
a, barplot to show enrichment of DNMs within each genetic region of specific gene sets for each study: x-axis for different regions, and y-axis for overenrichment ratio using synonymous sites as background, the calculation is as bellow:

ratio between #DNM in studied regions/#DNM in synonymous sites and #mr sum in studied regions/#mr sum in synonymous sites for WES dataset; 

ratio between #DNM in studied regions/#DNM in synonymous sites in cases and #DNM in studied regions/#DNM in synonymous sites in siblings for WGS dataset; 
 
b, 95% confidence interval for overenrichment ratio was marked as vertical line on each bar, and stars to indicate statistics test significance (*: <0.05, **:<0.01 and *** < 0.001), and the numbers on each bar to represent number of DNMs within each region;

c, different bar colors for different genesets, and each figure panel for each study.

Conclusions:

1, As postive control (neuro-function related genesets: TADAFDR0.3 and FMRP_targets_Darnell2011 genesets on the figure), we observed DNM overenrichment especially for LOF, damaging missense mutations in the case samples but much less normal samples, which prove validaty of the data and method used in the analysis. 

2, we observed DNM overenrichment for RBP binding sites (CLIPdb and STAR2 on the figure) on the neuro-function related genesets, at least higher than normal nonsynonymous sites, which indicate some enrichment, but not significant.

3, In negatve control (NonMental genesets on the figure), we cannot in general found many DNM overenrichment acorss all the studies, which is expected.

4, In the genome wide level analysis (All on the figure), we can still observed DNM overenrichment on LOF and damaging mutation sites as expected, unfortunately, not for RBP binding sites (CLIPdb and STAR2 on the figure), which indicate no or minor enrichment on the genome-wide scale.

5, In addition, we observed higher DNM overenrichment for potantial splicing sites (predicted by spidex), but not for RNA structure changing sites (RNAsnpM3 and RNAfold).


Details about Methods and Data could be supplied on request. 


