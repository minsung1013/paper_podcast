# Chai-2 source dossier

## Selection and provenance

- ActualPDF22pagesstoredpapers/chai2-zero-shot-antibody.pdf;fulltextsourcein episodefolder. Officialhttps://www.chaidiscovery.com/news/introducing-chai-2linksidenticalhttps://chaiassets.com/chai-2/paper/technical_report.pdf.
- ExacttitleZero-shot antibody design in a 24-well plate. CorporateauthorChaiDiscoveryTeam;contributorsJacquesBoitreaud,JackDent,DannyGeisz,MatthewMcPartlon,JoshuaMeier,ZhuoranQiao,AlexRogozhnikov,NathanRollins,PaulWollenhaupt,KevinWu.
- CompanylaunchJune30,2025;PDFbioRxivfooterpostedJuly6,2025,doi10.1101/2025.07.05.663018. Companytechnicalreport/preprint,notpeerreviewedjournalpaper.
- SelectedoverChai3productannouncementsandlaterChai2challenging-targetreportbecauseinitialreportcontainscoredesign/foldingmodules,trainingcutoff,unseentargetselection,andactualassaymethods. LaterfullmAb/GPCR/cryoEMresults**notascribedtoinitialreport**.

## Actual order / reading / figures

Abstractp1;intropp1–2;Methods2.1/2.2/2.3pp2–4;Results3.1miniproteinp4,3.2antibodypp5–6,3.3controllabilitypp6–7;FutureWork/Limitationsp7;Discussionp8;contributorsp8;Supplementfigs/tablespp9–13;Supplementmethodspp14–18;refspp19–22.

Readallmaintextandsupplementaltext/tables,referenceidentitiescheckedforbackground. MainFig1p3/Fig2p4/Fig3p5/Fig4p7andSupplementS1/S2p9,S4/S5p11renderedandvisuallyinspected. PNGsfigures/. Narrationkeepsactualorder,Supplementmethodsincorporatedwithcorrespondingmainmethodtopics.

## Core architecture and data boundary

- IntegratedendtoenddesignsystemwithfunctionalmodulesChai2d(candidatechains/sequence+backbone+sidechainsallatomgeneration)andChai2f(foldingassessment). Notalllayers/losses/generationcount/selectionthresholdsdisclosed;noinventedparametercountorfullreproducibilityclaim.
- Targetstructure+1–4hotspotresiduesonknownnon-Abproteininterface;antibody5commontherapeuticVHH/5VHVLframeworkoptions;scaffoldsequencefixed,allCDRresidues**andlengths**designed.
- FoldingChai1-likePLMembeddings/MSA/templates/auxiliaryrestraints;syntheticstructures+PDBtraining. Structuraldatacutoff2021-09-30;designmoduleexplicitexcludeschains>70%id/80%coveragewithreserveddesigntargets.
- Targetcatalogin-stock+knownPDBnon-Abheteromericinterface+nohomologknownAbantigenabove70%identity/80%coverage. Broadpanelnotrandomallbiologicaltargetuniverse. Remoteholdout25%id/25%coveragesubsetalsoanalyzed.
- “Zero-shot”noperspecifictargetfinetuningorwetlabiteration/knownstartingbinderpose;knownscaffolds/targetstructure/nativeinterfaceallowed. Do notsaynoinformation.
- Ranking/selectionaftergenerationbefore≤20experimentaldesigns/formattarget;internalgeneratedcountnotreported. Noexact20totalcomputationalbudgetclaim.

## Structure prediction evaluation separate from design validation

-152complexes/255lowhomologyAbAginterfaces,PDB2022-05-11to2023-01-11,DockQ≥.23/.49/.80thresholds.
- Chai2highDockQ~34%vsChai1~17%;with4epitoperestraints>40%withtemplates/~32%without. Notallatomexperimentalconfirmationofnewdesigns.
- SupplementfigS1/S2templatesvsonotemplates;Chaiidentityfilteredtemplates;AF2servercouldexacttemplateleak;AF3notbenchmarked**atreporttime**duelicensing. Don'tassertcurrentAF3licensingstatus.

## Exact experimental numbers and denominators

### Miniproteins

5targetsIL7Ra,InsulinR,PDL1,PDGFRβ,TNFα. Chai2tested23/20/25/21/22respectively,total111;75hits=67.6%rounded68%;5/5targetsuccess. Miniprotein**20–25**notall≤20. Chai1dprototype20/targetbaselineisdesignmodelnotChai1foldingcomparison.

pMexamplesIL7Ra18.3pM/148pM,InsulinR153pM/331pM;PDGFR545pMavidityflag;TNFa4.46nM/11.7nMavidityflag. FigurespredictedcomplexeswithmeasuredBLIcurves,notdeterminedcomplexstructures. Externalpriorratesnotfullycontrolledsameassaydirectcompetition.

### Antibodies

- scFv**68/496=13.7%**,target21/43≈49%.
- VHH**41/205=20%**,target10/18≈56%.
- Uniqueunion**26/52=50%**,candidate**109/701≈15.5%**rounded16%. 43+18overlap9,notsum61uniquetargets;21+10successesoverlap5,notsum31uniquesuccesses.
- Remotehomologysubset43unique,24success56%,VHH20%/scFv17%;sameexperimentsfilteredanalysisnotnewindependent43experiments.
- Fig3bper-targethitcountsnonuniform;meanratecannotassumeeachnewtarget20designs→3hits.
- AffinityexamplesEFNA52.2nM*,VATF80nM*,CSF117nM*,UNG265nM. Asterisksavidity;antibodyresultsnotrepresentedbyminiproteinpM.
- CDRminimumeditdistance>10,SAbDabtargetalignedframeworkRMSDvastmajority>10Å/none<2Å. Predictedstructurediversityclustersthreshold3Å;23targetformatpairswith≥2hits,18multipleclusters. Notexperimentalposeconfirmationormemorizationabsolutedisproof.

### Extra target-specific characterization

- CCL2andLIFhaveknownAbinSAbDab,excluded52targetsuccessbenchmark.
- CCL2format+epitopeconditions20per:VHH4/20best82nM;scFv5/20best3.3µM. **Explicitneedadditionalexperimenttoverifyactualepitope**;doNOTclaimbothstrongnM.
- Crossspeciesunnamedhuman/cynomolgoustarget14designs,onebindsbothhuman77nM/cyno121nM;otherscyno-only. Onecrossreactivebindingface≠constructedbispecificmolecule. Targetnotnamed,indication/drugnotinvented.
- Offtarget23designs2threeantigensets:1hasabovesignalofftarget,noKDbecauseinsufficientmaterial. Specificityagainstlimitedpanelnotwholeproteome.
- Polyreactivitywetlab**2CCL2scFvs**againstBVP/ssDNA/dsDNA/insulin/LPS/HSA,tworeplicates. Comparatorconcentrationanddetectiondiffer;noallcandidatescleanclaim. FigcaptioncallsVisilizumabapprovedincorrectly;scriptavoidsapprovalstatusclaim.
- Otherdevelopability/immunogenicity**in silico**charged/hydrophobicpatches,liabilities,humanness;nobroadthermal/aggregation/viscosity/humandonorassay. LaterChai2reportfulldevelopabilitynotimported.

## Assay procedure

- E.colicell-freeIVTT. MinibindersTwinStreptag8µL37°C12h;VHH/scFvHis10tag1mL30°C3h,Ni-purification/A280/SDS-PAGE.
- HitBLIpositivecurve+>.1nmabovebackground+>300%background. Antibodyinitialonepoint**5or10µM**analyte,notallnanomolarscreen. Miniproteinserialconcentrations32.2–1000nM.
- Antibodykinetics4–7point2/3folddilutions,fit1:1or1:2,R²>.98reported. Someantigensmultimeric/avidityexplicit;subsetantigenonsensorvsusualbinderonsensor.
- Twoweeksdesignthroughbindingworkflow/oneplateconceptnotdrugdevelopmentorfullyautomatedrobotthroughput. Currentreportfirstattemptnearlyalltargets,noiterativewetlabfeedbackcomparison.

## Limitations retained

Epitopeintendednotexperimentalatomicvalidation;scFv/VHHtoFab/fullIgGtransferunproven;manypropertiescomputational;bispecifics/ADCs/macrocycles/enzymes/smallmoleculesmentionedfuturepossibilitiesnotcurrentwetlabcoverage;noanimal/cellfunctional/clinicaleffect. Stateofart100×claimcrossstudyconditionslimited.

## Primary background

- Caoetal.,Nature2022,Designofprotein-bindingproteinsfromtargetstructurealone,https://www.nature.com/articles/s41586-022-04654-9 (briefminiprotein/surfacechallengecontextonly).
- Jainetal.,PNAS2017,clinicalstageantibodybiophysicalproperties,https://pubmed.ncbi.nlm.nih.gov/28096333/ (benchmarklogicnotnewChaiwetlabproperties).
- OfficialChai1reportlink403ataccess;notclaimindependentlyreadChai1methods,newreport’sdescriptionsufficientforcomparison.

## Final QC

41narratorparagraphs,**8651Hangulsyllablesnarratorprose**. H1parserheader,soloformat,title/pron/source.jsonpresent. NoCDRposeproof,noIgGdata,nobispecificfabrication,noclinicalpromise,no68%antibodyconfusion. Rootrenders/publishes.
