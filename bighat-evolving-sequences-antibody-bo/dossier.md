# CloneBO evolving-sequences source dossier

## Source scope and metadata
- Supplied25pagePDF, allmaintext, references, appendices A–D fully read through extractedtext; key figureimages actually inspectedp6,8,10,11,23.
- *Bayesian Optimization of Antibodies Informed by a Generative Model of Evolving Sequences*.
- Alan Nawzad Amin;Nate Gruver;Yilun Kuang;Lily Li;Hunter Elliott;Calvin McCarter;Aniruddh Raghu;Peyton Greenside;Andrew Gordon Wilson. NYU+BigHat. Equal contribution marked forGruver,Kuang,Li.
- ActualPDFarXiv:2412.07763v1[stat.ML],10Dec2024. Do notinventconferenceacceptance basedonothercompanylistings.
- Main sectionorderfaithful:abstract/introduction,relatedwork/background,§4fitnessprior,§5CloneLM,§6CloneBO,§7computationalthenwetlab,§8conclusion,§9reproducibility. Appendixdetailsintegratedatrelevantbeats.

## Claims and numerical anchors
- Candidate-seedediterativeoptimization,notde novozero-shotbindingdiscovery.
- OAS humanclonalfamilies inferredFastBCR;familysize>=25;908kheavyfamilies,34klightfamilies. Separate377MautoregressiveLMs,notpairedheavy-lightmodel. Mistral7Barchitecture scaleddown,not7Bweightsmodel. Testperplexities1.276heavy/1.267light.
- Familyconditional sequence logprobability is assumedfitness proxy;exchangeability and ignoringlineagerelations are explicitidealizations. Noantigenstructurerequired. Morefamilycontext→stablepredictive+lowerperplexityisnotdirectfitnesswetvalidation.
- Fig3humannessisIgLMscorechangeafter3mutations,notmeasuredimmunogenicityorclinicalstability. Avoidoverstatedoriginalintro'sstable=noimmuneevents claim.
- Labfitnessf ispositiveaffinetransformoffamilyfitnessF+homoskedasticGaussiannoise;simplemodel limitation. MartingaleposteriorfamilyrepresentationandfiniteLM/tSMCapproximation distinguishedfromexactBayes.
- PracticaltSMCD4,M6;topK4startsequences,maxL3substitutions;subset75mostrelevantmeasurementsto reducecost;~10h/100stepssingleA10080GB.
- Fig4example75Tmmeasurements,IS300vs tSMC4particles;R2.48vs.76,illustrativetraining-datafit,notindependentnewcandidatepredictiontest.
- Clonalfamilyoracletrained10015sequencefamily;maintextinitialization1sequencevsAppendixB.2says2sequences. Scriptdoesnotclaimexactinitialnforfirstoracle. **Originalinternaldiscrepancy**.
- Lab-derivedoracledata6880sequences;10CARP/Bytenetensemble;crossvalSpearmanKD.95,Tm.72.1000initialsequences useoraclepredictedY,100furthercomputationalsteps,not100wetrounds.
- Table1bestmeanacross10replicates:CloneBO normalizedbinding.3713,LaMBO-Ab.3381;Tm72.92vs70.44°C;bothpredicted. MainFig5p=.018binding,.006stabilityagainstnextbest. AvoidconvertingnormalizedbindingtopreciseKD.
- SupplementCoVpredictorslimiteddiversedata/highuncertainty;notwetneutralizationorproofallstructuremethodsbad.

## Wet evidence: crucial parsing
- **p11footnote3 says94/1000Tm,997/1000KD. Extracted'394/1000' joinsfootnotenumber3and94; actualfigureimageconfirms94.**
- Actualonewetdesigniterationafterprior~1000sequences. Maintextdescribes200designs;ambiguousallocationavoided(noclaim200perarm).
- Fig6a **predictedP(Synth)**fromsupervisedpredictorAUROC.87,notobservedsynthesissuccessrate. Predictedp<1e-5comparison.
- Followedbyselectionforpredictedproducibility;notall200tested. Maintext20sequenceswordingnotunambiguouslypooledvsperarm;scriptdoesnotspecifyallocation.
- ActualnewmeasurableaffinitiesCloneBO9,LaMBO-Ab11;newTmCloneBO19,LaMBO-Ab10. Previouslymeasuredaffinity+2eachincludedinFig6;scriptspellsout.
- CFPS96well,ProteinAmagneticbeadpurification,BLI(OCTET)affinity,NanoDSFUncleTm. Productionnotlarge-scalemanufacturing,affinitynotcell/animal/clinicalefficacy.
- StrongestCloneBO binderbeatenby2of997previoussequences:nearbest,**didnotbeatpreviousbestKD**. HighestTmdoesbeatpreviousbest. Fig6KDnormalized soexactnMKDnotdisclosed.
- Measuredaffinitydifferencep=.021MannWhitney;smallselectedsubset;dropoutandpreviouslymeasuredstatusmaycorrelatewithfunction. Fig16new-onlyqualitativelysimilar.
- BindingandTmareoptimizedseparately;simultaneousMOO explicitlyfuturework,notestablished.

## Figure anchors (oral descriptions in script)
- Fig1p2family/experimentalfeedbackconceptdiagram.
- Fig2p5alignedrealandgeneratedfamilies;sharedbluechangesandvaryingfamilypatterns,notbindingvalidation.
- Fig3p6MvsdistributionKL,Mvsperplexity,implicitfunctionsampling,IgLMhumannesschange.
- Fig4p8fitFvsmeasuredTm,logevidencevsM;tSMCvsimportance.
- Fig5p10computationaloptimizationstepsvsfitness;bestpredictedbinding/Tmbenchmark.
- Fig6p11predictedproducibility;measurednormalizedbindingandTmwithhistoricalhistograms/verticalbestline.
- Fig7p18initialpooldistances/UMAP,notusedfornumericclaims.
- Fig8/9pp18/19extraheavy/lightfamilies;indelsmayreflecttruncatedOASinputs.
- Fig10p19bindingfit;Fig11/Table1p20stepwiseoracle/meanresults.
- Fig12p21CoVsurrogatelimitedanalysis;Fig13p21ablations;Fig14p22poolsize/priormismatch;Fig15p23hyperparameterparticularlynoise;Fig16p23newaffinityonly.
- MathematicalappendixDpp24–25convergenceunderassumptions,notfiniteimplementationguarantee.

## Primary background sources checked
- Frazier2018tutorial https://arxiv.org/abs/1807.02811 ;Bayesianoptimizationoverview,BOuncertainty/acquisitionexplanation.
- FastBCRauthortoolrelease https://zenodo.org/records/8320531 ;paper DOI https://doi.org/10.1016/j.crmeth.2023.100601 .Familyinferencecontext.
- Sella&Hirsh2005primary https://doi.org/10.1073/pnas.0501865102 .Evolutionaryfrequency/fitnessidealization;scriptreliesmainarticleforassumptionnotuniversalclaim.
- Mainhttps://arxiv.org/abs/2412.07763 ;code/weights https://github.com/AlanNawzadAmin/CloneBO .

## Reproducibility and delivery
- Publiccode/weights;iterativecampaignsequencesproprietary. Do notclaimfullwetdatareproducibility.
- Dialogue15161Hangulsyllables(excludingappendix),72narratorparagraphs,21400characters. Continuoussolonarrationwithpaperorder.
- pron.json andtitle.txtincluded. RootcontrolsQCrenderandpublication.
