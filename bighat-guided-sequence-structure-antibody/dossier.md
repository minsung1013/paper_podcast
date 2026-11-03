# Dossier — Guided Sequence-Structure Generative Modeling for Iterative Antibody Optimization

## Metadata and evidence scope

- Actualsource `/Users/minsung.choi/bioeu/protein/papers/bighat-guided-sequence-structure-antibody.pdf`,15pages. Readallmaintextpp1–6,AppendicesA/B/Cpp10–15; referenceidentitiespp7–9.
- AniruddhRaghu,SebastianOber,MaxwellKazman,HunterElliott. BigHataffiliations exceptKazmanUW(workatBigHat).
- PDFexplicit **GEMworkshop,ICLR2025**, notICLRmaintrack. arXiv2509.16357v1,19September2025. [record](https://arxiv.org/abs/2509.16357)
- Single ongoing therapeuticantibodyoptimizationcampaign, experimentallydeterminedstartingFab–antigencrystalstructure. Noantigentargetidentityorclinicalassetnameprovided.
- **Leadoptimization**, notde novo antibodydiscovery withoutbinder/complex. Currentseedsalready5–20CDReditsfromstarter; ≤4additionalCDReditspergeneration. Bindingposepreservationassumptioncentral.
- Actualwetlab: CFPSsynthesisscFvs,adequatequantity/purityselectedforBLI(Octet)binding. Noanimal/cellfunctional/clinicalefficacy. Newlygeneratedpolyreactivityoutcomescomputationalonly.

## Actual logic / narration

Opening→Introduction→Methodsbackground(letters,Cαpositions,orientations;maskedCDRs/context)→DiffAbOptpredictedstructures/iterativeranking→oracle-guidedsampling→experimentalsetup→in silicoandwetlabbase/rankingcomparisons→guidancecomputational/wetlab→Appendixstructure/trainingablation/filterdetails→Conclusion/limits/wrapup.

53narratorparagraphs,11,898actualHangulsyllablesinnarratorprose;200+each. Parserheaderprovided,title.txt/pron.jsonincluded. Rendering/publishingparentonly.

## Methods factual anchors

- DiffAb retrainedsamearchitecture;jointresiduetype/Cαposition/localorientationdiffusion inCDRs,framework+antigencontextfixed.
- Partialnoisingofcurrentseedthenreverse,notalwaysfullpriornoise.
- CurrentbestantibodyIgFoldpredicted,rigidalignedtostarterinexperimentallydeterminedAb–Agcomplex. RetainsoriginalAg/pose; notfreshdockingeachround. Assumesposehasnotsubstantiallychanged.
- Experimentalfeedbackthreeplaces:seedselection,post-generationoracleranking,generation-timeguidance. Distinctcausalcontributions; don'tconflatetheirresults.
- PoE∝p_diffusion exp(f)^γ. Sequence-onlyoracleapproximation; perpositioncandidateaminoacidreweightingindependentnormalization. Exactsamplingofeachapproximatedcategorical,notexactwhole-sequencePoE. Positions/orientationsdirectsamplingunchanged,indirecteffectthroughlatersequence-structuresteps.
- Ranker10ByteNet/CARPCNNensemble;inhouseNGS~75kpretraining,4k–8kbindingsequencesperroundfinetune. GuidancecheaperonehotRidge,trainedcampaignbindingdata. Cachedoraclepredictions.
- Polyreactivityrandomforesthandcraftedsequencefeatures,250flowcytometrymeasuredsequences. γ10withnegativepolyreactivityscore;affinityγ2. Scalesdifferent,not5×priority.
- TrainingSAbDab2024-10-17,~30%moredata;excluderesolutionworsethan4Å/nonproteinantigens,HCDR3cluster50%identitytrain/test.
- ExpandedCDR unionChothia/IMGT/Kabat;correctedresiduetypedenosingposteriorvarianceterm;λtype10,λpos1,λorient1.
-200ktrainingsteps,Adam1e-4,patch128residuesnearCDRanchors. Notall-atomdiffusionparameterization; allatomcomplexrepresentationnotclaimed.
- Sampling2/4/8/16tested,all6CDRs8noise+8denoisebestwithin≤4editconstraint;largernoisegivesfewvalidnearvariants.

## Exact experiments and numbers

### Figure1p4: basegenerationandranking

- In silico2seeds10–15CDReditsfromstarter; MLM(Sapiens)5000mutantsperseedVH/VLthencombine;DiffAbOpt5000mutants; rankedversionsByteNettop50;≤4currentseededits.
- Fig1a **predictedfoldaffinityimprovementoverstarter**, logy. DiffAbOptdistributionhigherthanMLM,includingranked; oraclebasedselection/evaluationnotindependentwetlabproof.
- Mid-stageactual: seeds5–10editsfromstarter;MLMranked72designed/66synthesized;DiffAbOptranked22/22. Fig1bmeasuredaffinityfoldimprovementoverstarterhigherforDiffAbOpt.
- Late-stageactual: seeds15–20edits;DiffAbOptranked60/55synthesized;unranked20/15. Fig1cshowsrankingbenefit.
- Do NOT calculateauniversalhit-ratefromcounts: synthesis≠binding,filtered/rankedsubset,assayonlyadequatequantity/purity. Differentgroupsizes. Allwithinasinglecampaign,notmultipleindependenttargets.

### Figure2p5: guidance

- In silico5000designsfrom2seeds10–15edits. Affinityguidanceshiftsunrankedpredictionsup;rankedincrementmodest. Differentguidance/evaluationoracles.
- Polyreactivityguidance lowerspredictedpolyreactivitywithroughlycomparablepredictedaffinity; no newlygeneratedcandidatepolyreactivitywetlabvalidationreported.
- Actualguidancecomparison20selected/groupafterranking+developabilityfilter;unguided19synthesized,guided20synthesized.
- **Fig2captionexplicitguidanceaddedmeasured-affinityimprovement“not statistically significant”**. Mainnarrationstates thisclearly;donotclaimguidancewetlabsuperiorityproved. Suggestingincreasedγisfuturehypothesisnotresult.
- Relativefoldoverstarter≠incrementovercurrentseed≠absoluteKd≠cellpotency. NoabsoluteKd/exactboxmediansinvented.

### AppendixC.4Figures3–5pp13–15

- Fig3top500rankedpredictions,starterseed:experimentalcomplex vs predictedAbalignedtorealpose vs rigidrotatedwrongpose vs noAg. Firsttwohavesimilarmedians/predictedAbwidervariance;wrongposeandnoAgworse. Doesnotprovelate-stageactualposesidentical.
- Fig4top100rankedpredictions:modeloriginal→posteriorfix→expandedCDR→moredata. Smallposteriorfixeffect,biggercombinedgains. In silico,notindependentwetlabablation.
- Fig5top100affinityrankedpolyreactivityguided/unguided;qualitativereducedpolyreactivityatroughlysimilarpredictedaffinity,possibletradeoffsnotstrictPareto-domination.
- C.5developabilityfilterisoelectricpoint/knownsequenceliabilitiesbeforeCFPS/BLI. Exactfilterthresholdsandallrejectedcountsnotprovided.

## Figure images inspected

Fullpages4,5,13,14,15renderedtofigures/pageN.pngandvisuallyinspected.

- Figure1:3panels,computationalvs2wetlabstages;logfoldaxes;notexactmedians.
- Figure2:affinityboxes,2Dpolyreactivity-affinitydensitycontours(leftbetter/upbetter),wetlabguidanceboxes.
- Figure3:4structureconditions,predictedaffinityboxes.
- Figure4:4trainingconditions,predictedtop100distributions.
- Figure5:2Dcontoursbefore/afteraffinityranking;notwetlabpolyreactivity.

## Primary background consulted

- [Luoetal.,DiffAb,NeurIPS2022](https://papers.nips.cc/paper/2022/file/3fa7d76a0dc1179f1e98d1bc62403756-Paper-Conference.pdf):jointCDRsequence/structure diffusion,publicmethodlineage. [authorcode](https://github.com/luost26/diffab)
- [Ruffoloetal.,IgFold,NatureCommunications2023](https://www.nature.com/articles/s41467-023-38063-x):antibodystructurepredictioncontext; ownsourceperformancebenchmarksnotimported.
- [CurrentarXivrecord](https://arxiv.org/abs/2509.16357)metadata.

## Final guardrails

NoICLRmaintrackclaim,nozero-priorde-novobinding,noautomatedwetlabthroughputclaim,noguidanceinvitrosignificantwin,nopolyreactivityexperimentalimprovementclaim,noclinicalefficacy,nomultipletargetgeneralization,nouniversalBLIhit-rate,nospecificdrugname/indicationinvented.
