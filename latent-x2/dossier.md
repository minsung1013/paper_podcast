# Latent-X2 source dossier

## Source / company relation

- ActualPDF27pages,stored `/Users/minsung.choi/bioeu/protein/papers/latent-x2.pdf`;fulltextextractedinsameepisodefolder.
- Exacttitle:Drug-like antibodies with low immunogenicity in human panels designed with Latent-X2.
- CorporateauthorLatentLabsTeamand17namedcontributors;HenryKenlay/DaniellaPretoriusequalcontribution;SimonKohlcorrespondence. Rombach/Nelsonadvisors,notprior-employerpaper.
- Reportdated16December2025;arXiv2512.20263v1submitted23December2025. Companytechnicalreport/preprint;peer-reviewedvenuenotestablished.
- Officialproductpagehttps://www.latentlabs.com/latent-x2/directlylinkshttps://arxiv.org/abs/2512.20263.
- Selection:corecurrentcompanymodelacrossVHH/scFv/macrocycle,actualbinding/developabilityand10donorhumanPBMCassay;moredirectthanfounderAlphaFoldhistoryoragentorchestrationLatentY.

## Actual paper order / reading

p1abstract;pp2–3intro;Results2.1antibodybinding/developabilitypp3–5;2.2TNFL9followup/exvivoimmunogenicitypp5–7;2.3macrocyclespp7–8;Methodspp7–11;Discussionp11;contributorspp11–12;referencespp12–14;SupplementApp–B/C/Dpp15–27.

Readmaintext/methods/allappendixtextandtables;renderedandvisuallyinspectedFig1p2,Fig2p4,Fig3p6,Fig4p8;computationalfigpages20/21rendered. NarrationfollowsactualsequenceResultsbeforeMethods;appendixdetailsinsertedintocorrespondingtopic.

## Core method and disclosure limits

- Allatomjointsequence/structuregeneration,complexconditionedtargetstructure+1–4hotspotresidues+binderformat+framework/CDRlengthforantibodies. Noendtoendarchitecture/loss/trainingcompositionreproductiondetails;donotfabricatediffusiontype/parametercount.
- Actualtargetinputbackboneatomsonly;512residuejointtarget+bindercontext;cropdistalregions/dropunresolvedresiduesincludingidentities. Allatomoutputnotallatomtargetinput.
-5VHH/5Fvframeworks,knownscaffoldsfromclinical/research. All3VHH/6FvCDRsgenerated,frameworkfixed;HCDR3length±2,otherCDRlengthsfixed. Fvdesignedthen(G4S)4linkeraddedVH→VL,notjointlygeneratedfullscFvlinker.
- Hotspotselectioncanuseknowninterfaces/priorvalidatedepitopes/co-crystalstructures. Zero-shotnot“noantibodyorinterfaceknowledgeatall”. Noapplication-specificfinetuningclaimed.
- Structurepredictionconfidence+selfconsistencyDockQfilter;cluster80%CDRidentityonerepresentative;excludeCDRcysteines/N-linkedglycosylationmotifs;noveltychecks. **Abstractwithoutfiltering/selectioncannotbeliteralpipelineclaim**. Scriptclearlydistinguishesnofurtherexperimentalpropertyoptimizationfromactualcomputationalselection.
- ExperimentalvariantLatentX2vscomputationalbenchmarkimprovedX2.1;donotmergeversionresults.
-200targetcomputationalbenchmark3hotspots×5frameworks×100=1500/target;meanVHHin-silicopass1.15%,~85%targetsnonzero. Notwetlabsuccess. Someconfigurationsrequire~1000generationattempts.
- AntibodyCDRnearestSAbDabeditdistance≥11tested,closestvalidated18;fullseqClusteredNR≥16. Noveltynotproofalltrainingmemorizationimpossible.

## Antibody results exact anchors

-18solubletargets,4–24testedpermodality-targetpair;9/18targetsuccess**combinesmodalities**,not50%candidatehitrate. Bestexperimentsupto25%validateddesigns,notoverallaverage.
- SinglepointBLIresponse>.1nmthenmultipointBLI/SPRfollowup;unreproduced/poorfitdiscardedfromvalidatedhits. FormatsproductionvariesCHOwithFcvsCFPStagged,notuniformnakedVHH/scFv.
- HighestHDAC8scFvKD26.2pM **avidityflag**;HDAC8reagentbivalent;doNOTassertintrinsicmonovalent26.2pM. Fig2asterisks1433Balsoavidity.
- OtherconfirmedTableS1examples:1433BVHH2.75nM,BHRF127nM,TNFL931.1nM,LEP44.8nM,MMP277nM,AHSP797nM,ONCM3.26µM,SAE1scFv165nM. Scriptnotesfullspread,noteverythingpM/low-nM.
-47%**confirmedbinders**pass4developabilitycriteria;80%atleast3/4. Notallgenerated/testedcandidates. Expressionseparatemeasurementnotoneof4.
-SECmonomer≥90%;BVPELISAplate-normalizedBococizumab1/Panitumumab0,pass≤1;HICretentionnormalizedLirilumab1,pass≤1;Tm1>Bococizumab61°C. Referencepermissive,noclinicalguarantee.
-10VHH/scFvdomainsfromclinical/approvedtherapeuticsreconstructedFc-fusion,notwholeoriginalapproveddrugdirectcomparison. Allroughprofilesnotallmetricsstrictlybetter.

## TNFL9 immunogenicity scope / critical caveats

-24TNFL9VHHdesigns→5binders→4selectedfordeepanalysis. One target/fourVHH,notalltargets/formats.
- Results“lownanomolar”wordingoverstatesFig3spread;scriptuses“nanomolarrange”ratherthanexactunsupportedlow-nM. Fig3graphsome~100–300nM.
- AlaninesubstitutionsF116/W99/D113reportedabolishbinding4VHH. SupportsCDRresidueimportance,notdefinitiveatomicpose/epitopeconfirmation;potentialfoldingconfound.
-10healthyhumanPBMCdonors,4concentrations1.11/3.33/10/30µg/mL,duplicatetechnicalreplicates,48h/120h. PositiveImmunoCultCD3/CD28+IL2/PHA;approvedVHHcaplacizumabreference.
- **“T-cell proliferation” actuallyCellTiter-GloPBMCmetabolicactivitysurrogate**,notTcell-specificdivisionreadout. Scriptflagsactualassayvsheadline.
-120h6cytokinesIFNγ,IL10,IL16,IL6,IL8,TNFαviaLuminex;noelevationrelativebackgroundreported,butIL8someaboveULOQacrossconditions. Notallcytokineszero.
- BothreplicatesbelowLLOQreported0;bothaboveULOQaboverange;onevalidonOORvalidonly. Scriptexplainsnondetectionnotbiologicalzero.
- ExvivoearlyhumanassaynotpatientADA/repeateddosing/clinicalimmunogenicityproof;animal/clinicalfutureexplicit.

## Macrocycles

-2targetsPHD2/KRasG12D,10selected/targetaftercomputationalfiltering/novelty,rankmeaninterchainPAE. Nosynthesisfeasibilityfilterbutotherfiltersremain.
- PHD2**9/10**,best**1.54nM**vsresynthesizedRaPIDreference**729nM**.
- KRasG12D**8/10**,best**5.43µM**vs**5.53µM**reference. NotKRASnanomolar. Someothers23.9µM.
- Literaturecomparisonmoleculesresynthesizedsameassay,notallmoleculechemistryidentical:generatedhead-to-taillactam vsdisplayreferencethioethercyclization. Reportcomparisonnotuniversalplatformsuperiority.
-10individualsynthesisvs>10^12pooledlibraryscreen≈11ordersinexperimentaldesigncount,not11ordersintotalcompute/cost.
- NoKRAScellentry/inhibition/tumorefficacyoralbioavailabilityresult. Priorreferencepaperfunctionalclaimsnottransferabletogenerationcandidates.

## Visual oral anchors

Fig1inputtargetgrey/hotspotsyellow,branchesVHHpurple/scFvred/macrocycleorange.
Fig2bestper-targetKDlogaxis+avidityasterisk;developabilityscatterdistributions/greyunfavourableregion+criteria-countbar;BLI/SPRtracesnotexperimentalcomplexstructures.
Fig3designedcomplexcloseup/alaninetest+4candidateheatmap;10donorworkflow;CTGandcytokinesdotplots/controls/outofrange.
Fig4pooledlibrarycountlogaxis,9/10and8/10bars,KDvalues,designedcomplexes+SPRtraces.

## Primary background consulted

- Jainetal.PNAS2017clinicalantibodybiophysicalbenchmark: https://pubmed.ncbi.nlm.nih.gov/28096333/ (briefbenchmarkcontextonly).
- Zhangetal.ACSCentralScience2020KRascyclicpeptideexperimentaldiscovery: https://pubmed.ncbi.nlm.nih.gov/33145412/ (benchmarkhistorynotnewdesignfunction).
- McAllisteretal.ChemicalScience2018PHD2cyclicpeptides: https://pubmed.ncbi.nlm.nih.gov/29899950/ (referenceidentitychecked).

## Final QC

39narratorparagraphs,**8285actualHangulsyllablesnarratorprose**. AllspokeninKorean. H1parserheader/title/pron/sourcepresent. Noimmunogenicityguarantee,unfilteredpipelineclaim,clinicalefficacy,KRASnanoerror,ororiginalapproveddrugformatconflation. Parenthandlesaudio/publishing.
