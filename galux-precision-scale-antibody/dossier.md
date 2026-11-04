# Galux Precision-Scale 사실 감사

## 판본·회사관계

Hyeonjin Chaetal.,PrecisionatEveryScale:EfficiencyinAI-DrivenDeNovoAntibodyDesign,bioRxiv10.1101/2025.11.21.689414v2,2026-05-15. 최초v1은2025-11-22(API확인),회사publication목록2025-11-26과구별. 전저자GaluxInc직접소속,임직원financialinterest공개p18. 원문23쪽전체읽음,Tables1/2/Fig2/7이미지직접확인. founder선행학술성과를현재회사검증으로대체한선정아님.

## 순서

p1abstract,p2§1intro/§2ResultsDiscussion/2.1workflow,p3Fig1,p4Fig2/2.2performance,p5Fig3novelty/2.3/2.4characterization,p6Table1,p7Fig4Fzd7,p8Fig5PDL1,p9Fig6predictedcontacts/2.5,p10§2.6commonbenchmark/Table2,p11Fig7/§3Conclusion,p12conclusion끝,p13§4methods4.1design4.2IgG4.3ELISA,p14criteria4.4novelty4.5ELISA,p15–16BLI,p16–17competition,p17BVP/contributions,p18competinginterests/references,p19–20SuppS8ELISAdistributions,p21S9,p22S10kinetics,p23TableS3twofullsequences.

## 수치·분모

- therapeuticset6targets8epitopes,50each=400IgG. strict10.5%=42/400;relaxed31.5%=126/400(개수는보고율로계산). **중첩criteria라합산불가**.
- 7/8epitopestrict=87.5%;ALK7strict0,relaxed1/50=2%. Fzd7site2strict22%;PDL1strict26%. 나머지Fig2직접확인.
- 7epitopes는이전LibraryScale에서검증한부위,8번째Fzd7site2신규. 모든targetsitezero-prior라는가정불가(p3). ALK7항원구조예측사용.
- 생성전체pool수/총계산비용명시없음. 50=wetselectedunique top50. 이전millionlibrary를이번계산budget으로동일시하지않음.
- strict기준100nMonOD>1.8ANDoffOD<10%on. relaxedon>.2AND(off<.2ORoff<10%on). strictestimatedEC50<100nM은단일점proxy,모든candidatefullcurve/KD아님(p14).
- Table1BLIKd(nM):PDL1.1/.17,HER2.87/.92,ACVR2B.46/1.74,Fzd7site2.28/.35,IL11GP1304.2. subset5epitope정량,all8아님.
- Fzd7representativeGX-aFZD7-6ELISAEC50=8.3pM **vs** BLIKd=.35nM. PDLaGX-aPDL1-5EC50=26pM **vs**Kd=.1nM. 단위/지표혼동금지.
- binning4targetsPDL1/HER2/ACVR2B/Fzd7,IL11ref부족. competition은겹치는부위/stericblock,원자접촉동일성증거아님.
- novelCDRmax<65%많음,비교집합PDB/SAbDab. 모든자연항체전체와새로움입증아님.
- FwRMSD29.7ÅFzd7/7.9ÅPDL1는**predictedposevsnearestknownpose**방향새로움. 설계vs실험오차아님. 이번대표후보cryoEM새증거없음.

## Crossplatform별도집합

9targets×50=450;relaxed79/45017.6%,strict49/45010.9%. 8/9strict,IL3onlynegative. BLI정량7/9,MK08ELISApositivebutnotquantifiable(p10–11). Table2PRL1.5,PARVA1.9,FCG3B2.7,AHSP4.7,RNF4329.6,EPCR37,CD22659.4nM. MK08n.q.
BVPnormalizedtrastuzumab0/visilizumab1:PRL.100,PARVA-.022,FCG3B.094,AHSP.284,EPCR-.007,CD226-.001,MK08.064,RNF43n.d. negative≠음의친화도,unmeasured≠pass.
Fig7Galux8/9,JAM25/9,Chai24/9. Galux/JAMwholeIgGvsChaiscFv/assaydifferences. 외부보고비교,동일lab동일budgetheadtohead아님. 2xclinicalsuccess주장불가.

## Methods/품질한계

manual2–6epitoperesiduesfunctional/accessibilitycriteria;knownnaturalinterface/complexwhenavailable(p13). fullmodelarchitecture/trainingrecipe/totalcompute없음. initialIgGoutsourcedBiointronHEK293;selecteddeepcharacterizationExpi293Fproduction. 자체wetcapability있음과initialproduction모두inhouse다름.
1:1BLIglobalfit,assayorientationtarget-dependent,apparentKD. IgGavidity가능,EC50≠KD. off-targetcontrol+BVPlimitedqualityaxes,동물/임상/모든developability아님. fullsequences2binders만공개,6therapeuticrelevance비공개p11.
**원문내화학표현주의:**p9Fig6본문/캡션Arg–R125saltbridge표현은화학적으로의문(둘다일반적으로양전하). 대본은이특정접촉을재생산하지않고predictedcontact가설수준만설명. independentstructure측정아님.

## 배경1차검증

1.Bangetal.Precise,Specific,andSensitiveDeNovoAntibodyDesignAcrossMultipleCases,bioRxivv22025-09-16,DOI10.1101/2025.03.09.642274. https://www.biorxiv.org/content/10.1101/2025.03.09.642274v2.full . 회사선행library/cryoEM연구. 이번campaigncandidate와혼합금지. brief배경만사용.
2.Dunbaretal.SAbDab, NAR42D1140–D11462014,DOI10.1093/nar/gkt1043. https://pubmed.ncbi.nlm.nih.gov/24214988/ . 공개항체구조의일관된주석DB, novelty비교범위설명.

## 완료

대본8,966한글음절,원문순서+Fig1–7/Tables/S8–S10구두설명. source/fulltext/title/pron포함. TTS/root배포대기.
