# Xaira 관련 RFantibody 원논문 감사

## 선정/회사관계/판본

Bennettetal.,AtomicallyaccuratedenovodesignofantibodieswithRFdiffusion,Nature649183–193,issue2026-01-01;online2025-11-05,DOI10.1038/s41586-025-09721-5. Received2025-02-25/Accepted2025-10-08. 제공29쪽정식PDF,©2025modifiedpublication2026. 창업자관계만으로선정한것아님: p12CompetingInterests직접근거로NRB/JLW/PJYL/BH현재Xaira재직,여러발명자가해당기술Xaira라이선스관련대가지급공개. **회사관계라벨 UW/IPD 논문; Xaira 라이선스·공저자 재직 연계.** 대학중심연구로X-DesignVega현재회사모델직접검증으로부르지않음. 회사공식research페이지도초기preprint연구등재.
원문전체PDF29쪽읽음. p1–11main+refs,p12data/code/interests,p13–26extendedfigures,p27–29reportingforms. p3Fig1/p9Fig5직접시각확인. 외부별도SI는이번PDF에없으므로SI-only수치를추가발명하지않음.

## 원문 순서/주요도판

p1abstract/intro,p2TrainingRFdiffusion/Fine-tuningRF2/DesignVHH,p3Fig1,p4Fig2VHHSPR,p5VHHcryoEM/OrthoRep/SARSfailure/scFv시작,p6Fig3VHHstructures,p7scFvcombinatorial/TcdB/PHOX2B/scFvcryoEM/improvedoracle시작,p8Fig4scFvbiochem,p9Fig5scFvstructures/improvedoracle,p10filterresults/Discussion,p11refs,p12code/interests,p14ExtFig1caption,p16ExtFig2,p18ExtFig3,p19ExtFig4,p20–21ExtFig5–6,p22ExtFig7,p24ExtFig8,p25ExtFig9,p26ExtFig10.

## 핵심 방법·수치

- antibody-tunedRFdiffusionbackbone+ProteinMPNNCDRsequence+fine-tunedRF2filter. frameworksequence/structurefixed;internaltemplateinvariantpermitsnewdock;hotspotepitopeconditioning(p2–3). 전체항체모든부분무제약생성아님.
- RF2filterprivilegedholo-targetstructure/hotspots조건,노hotspotspredictiveweak(p2,p16). 범용무정보bindingclassifier아님.
- humanizedVHHframeworkh-NbBcII10FGLA. VHH3CDR,scFv6CDR,IgGfullconverted. 2chain≠bispecific.
- VHHscreen:yeast9000designs/target(RSVI/III,RBD,HA);E.coliSPR95designs/target(TcdB,IL7Rα,HA). HA두방법. success0–2%mainp4,모든결과95개에서얻음아님.
- Figure2Kd:RSVsiteIII1.4µM,HA78nM(others546/698/790nM),SARSRBD5.5µM,TcdB262nM(본문~260). fourdiseaserelevantepitopessuccess,allcampaignsuccess아님.
- TcdBcompetesFZD48,doesnotbindTcsL70%homology;CSPG4KOVerocellneutralizationEC50460nM(p5/Ext4),limitedcellconditionnotanimal/clinical.
- HAcryo4testedoneeffectiveglycosylatedtrimerbinder;3.0Åmap~66%particlesmax2VHHpertrimer;glycanN296possiblepartialoccupancy. VHHbackboneRMSD1.45Å,H3~.8/.84Å(p5–6). resolution≠RMSD.
- OrthoRepevolution~2ordersaffinityimprovement(p5),notAIonepass. TcdBparent4.6Å/mature5.7Åmapsrigidbodyposeconfirmation;notindividualsidechainproofatallmaps.
- **SARSRBDmaturedVHH**targetsepitopebutframework-mediatedpose≠design;authorsclassifydesignfailure(p5). Binding/competition≠accuratedesign.
- scFvlibraryfixedpairingnohits;structureclusteredheavy/lightcombinatorialhits,theoreticalcomplexity~10million(p7). 10millionnotallisolatedquantitativewetmeasurement. Randomstruct-agnosticpairingpoorcomputationally.
- TcdBscFv6Kd72nM→full IgG1 68nM;scFv5460nM→IgG380nM(p7–8). on-targetFzd7competitionnotCSPG4.
- PHOX2BpeptideMHC HLA-C*07:02notintracellularproteinAbdirect;targetsR6. stabilizedpHLAprepared. SPR400nM/ITC~1µM;R6Anegative. **CARincorporationnoTcellkilling**multipleNBcelllines(SIp14citedmainp7),affinity/antigendensitypossiblecausesnotconfirmed.
- scFv6cryo3.6Å;compositeparentmodeloverallRMSD.9Å;H1.4,H2.3,H3.7,L1.2,L21.1,L3.2Å. highresolutionselectedcase. scFv5map6.1Åposeconfirmationlowerdetail(p7–9).
- AF3**retrospective**filteranalysis:VHHipTMAUC.86dominatedHA;orderedVHH9%ipTM>.6. scFvinitial4%>.85but5/6confirmedpass. Notnewprospectivefilteredexperimentalsuccessrate(p10/Ext10).
- originalProteinMPNNnotantibodyfinetuned;CDRhumannessOASislowerthantherapeuticAbs;developabilityimprovementfuture(p10). humanizedframework≠clinicalimmunogenicitysafety.
- codeRFantibodyreleasedacademic/personal/commercialp12;trainingZenodo. actuallabcomplexitystillnecessary.

## 해석 주의/한계

본문첫문장‘no method exists’는연구시점문제설정으로설명,2026모든경쟁자현황단정안함. InitialvsOrthoRep,correctepitopevsaccuratepose,highresvsrigidfit,bindervsCARfunction,wetcountvscombinatorialtheory모두분리. 실제wet/structure/cell있음,clinical없음. Xaira현재사업pipeline수치로대체안함.

## 검증한배경1차자료

Watsonetal.RFdiffusionNature6201089–1100(2023),DOI10.1038/s41586-023-06415-8. https://www.nature.com/articles/s41586-023-06415-8 . 일반골격생성/regularsecondarystructure접촉배경,후속antibodyloop문제와구별. 원초록/방법개요검증.
Paulk,Williams,Liu.RapidlyInducibleYeastSurfaceDisplayforAntibodyEvolutionwithOrthoRep,ACSSynthBiol13:2629–2634(2024),DOI10.1021/acssynbio.4c00370. https://pubmed.ncbi.nlm.nih.gov/39052526/ 및PMC13134537. autonomousmutation+yeastsurface/FACSaffinitymaturation배경,이번generation모델아님. 원초록검증.

## 완료

대본10,413한글음절,원문흐름7챕터,Fig1–5/Ext2,7,10구두해설. source/fulltext/title/pron완비. source에전체저자/라이선스관계기록. renderer제목H1있음.
