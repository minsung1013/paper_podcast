# Dossier — Improved Therapeutic Antibody Reformatting through Multimodal Machine Learning

## Source / provenance

- Actual PDF `/Users/minsung.choi/bioeu/protein/papers/bighat-multimodal-antibody-reformatting.pdf`,19pages; read maintextpp1–8 and all appendicespp11–19; referencespp9–10 consulted for background identities.
- Jiayi Xin (Penn; work at BigHat), Aniruddh Raghu, Nick Bhattacharya, Adam Carr, Melanie Montgomery, Hunter Elliott (BigHat).
- arXiv2509.19604v1,23September2025; PDFexplicit NeurIPS2025. [arXiv](https://arxiv.org/abs/2509.19604)
- Main direction IgG→scFv. AppendixB erroneously reverses wording scFv→IgG; do not follow that isolated label.
- Main task supervised retrospective prediction of synthesis failure and yield, plusSECsupplement. Not a de novo generationmodel; no therapeutic efficacy/clinical validation; no new target-binding demonstration.

## Paper order / script

Abstract/intro → Method2.1 formulation →2.2dataset →2.3evaluation →2.4features →2.5models →3.1setup →3.2baselines →3.3multimodal results →AppendixE supportingresults →4conclusion/discussion →wrapup.

Script56narratorparagraphs,12,699actualHangul syllables in narratorprose. Header and chaptertitles separate. All spokenprose inKorean; pron.jsonincluded. Parent renders/publishes.

## Data and experimental level

-1477unique scFv signatures, tuple(VH,VL,linker,orientation); repeatedtargetsaveraged.
- Maintextpp3/13:56parentalfamilies across7campaigns. AppendixBpp11–12:52families. **Unresolvedinternalinconsistency disclosed in narration**. Uses“약오십여”thenstatesbothcounts.
-8linkertypes,2orientations. ActualmeanVH118.9±4.8aa,VL108.1±2.2; AHoalignment152slots/domain is not literalproteinlength.
-40.9% synthesisfailure,59.1%pass. yieldmean31.33±51.44ng/µL; range3.50–513.58; scriptdoesnotfabricatefailurecutoff or expressionplatform.
- Labels from real reformattingcampaignexperiments, structures fromBoltz2predictions; assay/QCmethoddetailslimited. Evidencelevel: measured molecularproduction/puritylabels + retrospectiveMLvalidation, not prospective model-selectedcampaign.

## Methods

- Three splits: scFvsignature knownfamily/unseenconstruct; targetfamily fewsamplesfromnewfamily; parentalfamily entirelyheldoutfamily/noassaydatafromthatfamily.
- Zero-shot means no trainingassayoutcomes fromnewparentfamily; doesnotmean no trainingdata/externalpretraining/predictedstructures.
-60/10/30 train/val/test byappropriatesplitunit,10randomfolds,mean±SD.
- Sequence: AHoalignedVH/VLonehot + categoricalorientation/linker. FrozenAbLang/ISMperresidueembeddingsmeanpooledcomparators.
- Structures: predictparentalIgGandscFvBoltz2,rigidalign,CαRMSD +perresiduealignedcoordinates+gapflags. ComparatorAbMPNN/DPLM2meanpooledembeddings.
- Bio: NaturalAntibodyCDRpatchhydrophobicity,positive/negativecharge,scFvcharge separation. Missingvaluesimputedwithdatasetmean. Scriptflagsreproducibilityquestion whetherpreprocessingstatisticscomputedtrainingonly; doesNOTclaimprovenleakage.
- LinearlogisticL1/L2classification/regularizedlinearregression; frozenembeddingMLP2hiddenlayers,AdamW/earlystopping. BigPLMsnotendtoendfinetuned; resultcannotgeneralizetoallfoundationmodeluses.
- Figure5combinessequence/structure/biophysics. Appendixablationfeaturesseq/struct/rmsd arenotexactlymain3modalitydefinition.

## Core results exact anchors

### Table1p6 singlefeature classification

|Model|knownfamilyAUROC/AUPRC|newfamilyAUROC/AUPRC|
|---|---|---|
|AbLang+MLP|86.35/82.15|62.58/58.75|
|ISM+MLP|80.01/74.87|58.09/54.02|
|DPLM2+MLP|79.50/73.49|47.91/51.21|
|AbMPNN+MLP|73.38/65.89|54.30/54.67|
|onehotLogistic|89.46/87.46|66.35/59.21|
|3DcoordinateLogistic|77/71|52/48|

OnehotnewfamilyAUROCSD10.73;AbLang19.37. Highvarianceemphasized.

### Table2p6 multimodalvssequence

- scFvsplitAUROC92.93±3.61 vs89.46±1.63; AUPRC91.18±4.59 vs87.46±2.33.
- ParentfamilyAUROC88.92±14.93 vs66.35±10.73; AUPRC85.68±20.94 vs59.21±15.65.
- Absoluteimprovements22.57/26.47percentagepoints, not22.6%failureratereduction.
- Fam1AUROC94.64vs87.68;Fam282.96vs71.81;Fam393.33vs82.71.
- AppendixTable7parentaccuracy85.67±7.60 vs60.98±12.53.

### Table3p7 yield

- KnownfamilyPearson.641vs.531,Spearman.741vs.714.
- ParentfamilyPearson.625±.266vs.191±.255;Spearman.508±.264vs.035±.283.
- Fam1Spearman.630vs.646 (multimodalworse);Fam3.241vs.243 (slightlyworse). Donotclaimallmetrics/familiesimprove.
- AppendixTable8AbLangknownfamilyPearson.562 vsonehot.531; showsnotallPLMcomparisonslost.

### AppendixEpp15–17

- Fig10seq+structAcc85.5/AUROC89.2/AUPRC86.3;RMSDaloneAUROC~50/AUPRC39.8;seq+struct+rmsd89.0/85.8 (doesnotimprove).
- Fig11family-specificRMSD-yieldcorrelationspositive/negative/nearzero; correlationnotcausal, predictedstructurenotmeasuredstructuralchange.
- Fam1heldout55variants: passpositiveRecall100%,Precision87.2%,Acc90.9%;5badpredictedpass. Baselinepassfraction61.8→87.2%,absolute25.4pp,~1.4×hypotheticalexperimentprecision. Retrospectivepolicycalculation,notcompanywideprospectivecostsaving. Positiveclasspassherediffersfromfailuretasklabelling.
- SECbinarylabelmainpeakarea280nm≥90%;AUROCscFv97,parent91.4,Fam1100,Fam279.8,lastfamily84.6. Fig12labelsFam3whiletextcallsFam_102; discloseidentifierinconsistency. PureSECareanotbinding/efficacy.

## Visual inspection / oral anchors

Fullpagesrenderedandinspected1,3,4,5,15,16,17. AvailablePNGsinfigures/.

- Fig1p1:naturalIgG/fragmentstomodularengineeredformats; formatvsmultispecificitydistinction.
- Fig2p3(andduplicate7p13):coloredfamilyblockstrain/val/test,entirefamilyheldout vsfewshots vsallfamilies.
- Fig3/4p4(duplicates8/9p14):purple/pinkVHoverlay,blue/yellowVL; predictednotexperimental.
- Fig5p5:threeinputbranches→ML→QC/yield/SEC.
- Tables1/2p6and3p7:readfullnumericvaluesfromPDFtext,notinvented.
- Fig10p15:7featurecombinations,3metrics,seq+structhigh/RMSDlow.
- Fig11p16:family-specificsignedcorrelationbars,heterogeneity.
- Fig12p17:SEC5splitbars,variableperformance/errorbars.

## Primary background sources

1. [Olsen etal.,AbLang](https://pubmed.ncbi.nlm.nih.gov/36699403/),BioinformaticsAdvances2022. Briefcontextonly:antibodysequencepretraining,notcurrentreformattingresults.
2. [Passaro etal.,Boltz2](https://www.biorxiv.org/content/10.1101/2025.06.14.659707v1),2025preprint. Usedonlytoconfirmstructurepredictiontoolcontext; noimportedaffinitybenchmarks.
3. [CurrentpaperarXivrecord](https://arxiv.org/abs/2509.19604)metadata.

## Claims not made

No blanketlarge-modelfailure; noallfamilies/allmetricswin; noexperimentalstructures; nonewcausallyvalidatedstabilitymechanism; noactual1.4×totalcostreduction; noautomationthroughputclaim; nonewclinicalasset; nofullformatgeneralizationbeyondIgG→scFv.
