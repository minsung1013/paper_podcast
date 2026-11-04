# IsoDDE 대표자료 감사

## 서지/선정

Isomorphic Labs Team, Accurate Predictions of Novel Biomolecular Interactions with IsoDDE,10February2026,공식회사기술보고서27쪽. 학술지peerreview확인없음. 현재회사엔진직접관계가AF3선행논문보다강해선정. source.json공식URL/PDF기록. 전체27쪽읽음(References21–27).

## 실제순서

p1abstract/Fig1overview,p2intro,p3§1structure/relatedwork,p4Fig2RunsNPoses/§1.2,p5§1.3FoldBench/Table1/1.4Boltz2,p6Fig3cases,p7Fig4/1.5antibody,p8Fig5,6,p9antibodycases/§2Affinity,p10Fig7/2.2evaluation,p11Fig8/2.3results/§3pockets,p12Fig9,10,p13Fig11/3.2results,p14Fig12/§4summary,p15–17suppmethods,p18–20Fig13–16/Tables4–5. 생성알고리즘의전체훈련/architecture공개논문아님. 대본은그공백추정하지않음.

## 숫자와검증범위

- 주요근거 retrospective prediction vs 실험PDB/활성데이터. de novo항체생성성공률/동물/임상아님. 예외로suppFig16사내helicasecrystalsoaking/PanDDA전향사례.
- structuretrainingPDBcutoff2021-09-30(p16). FoldBench/Fig5,6일부추론templates2023-01-01까지,자체AF3평가에도동일. training과inference구별.
- RunsNPoses25samples중topconfidence. lowest(0,20]fulln60:Iso30/60=50%,AF323.3%,gain26.7pp;filtered+clusteredn39:37.2vs16.7%(p4,p18). >2fold는이specificsuccessfraction,clinical/immunogenicity아님.
- Boltz2trainingcutoff2023-06-01→별도허용subset,Fig4/Table5;전체benchmark에무분별비교아님.
- FoldBenchTable1p5:AbAg75.58vs47.90(AF3),기준DockQ≥.23. n334novelAbtest와다름.
- Abtest334PDB(p7):CDRidentity<70% OR epitopeweightedidentity<40%. OR임,모두새분자wet실험아님.
- 1seed highDockQ>.8약39%,2.3xAF3/19.8xBoltz2;correct>.23=63%;H3≤2Å70vs58vs43%. 1000seeds up to82%correct,59%high,84%H3. 1seed/1000seed성능혼합금지.
- affinityChEMBLtimecut2023-01-01,newChEMBL35not34;singlechain≤1800aa,assay≥20ligands,variancefilterSD≥.5(p16). Ki/Kd/IC50/EC50/DC50readouts서로같은물리량아님.
- Fig9FEP4:4targets87neutralmolecules,r.85Iso/.78FEP+. OpenFE39targets873measurements,r.73/.72FEP+. 비교군일부Passaro2025에서가져옴. 원천testtargets≥90%similar제거(p17). CASP16resultonbenchmark이지모두동시blindsubmission입증아님.
- Fig10similaritylow/medium/highmeanr.55/.52/.55. MorganfingerprintTanimotodefinition. GPR3retrospectivecase r.82vs.46.
- pocketresiduewithin5Åligandheavyatom,rankAUPRC. Fig11.75Iso/.51P2Rank/.16random. 잔기지표,75%신약포켓성공률아님. P2RankonIsoDDEstructures.
- CRBNFig12retrospective9SFM,ligandposeRMSD.33ÅSB405483/.12lenalidomide. sequencenoligandpocketprediction후ligandidentity입력cofold. 첫발견아님.
- Fig16prospectivehelicaseinhousefragmentsoaking/PanDDA:recallonPDB1.0vs.83/PanDDA.73vs.33. targettrainingincluded,일부Isoonlypredictedpocketsunconfirmed. 전체대규모독립wet성공률아님.

## 한계

회사보고,핵심architecture/trainingrecipe비공개,외부수치혼용,retrospectivebenchmarks중심. Antibodycontactprediction≠newCDRdesignwetvalidation. Affinitycorrelation≠absoluteerror≠clinicalefficacy. 모델의confidence높아도맞음보장아님.

## 배경검증1차자료

AF3Nature630493–5002024DOI10.1038/s41586-024-07487-w 공식논문https://www.nature.com/articles/s41586-024-07487-w :공동분자구조예측배경,Isomorphic공동개발. 새IsoDDE전체능력으로동일시안함.
RunsNPosesŠkrinjar2025DOI10.1101/2025.02.03.636309 https://edoc.unibas.ch/entities/publication/23648b8d-2e5f-4689-9df1-246c9572045d :학습유사성에따른pose평가배경. 대학공식원서지/초록및dataset확인.

## 완료

대본약8,460실제한글음절. source/pron/title저장. 원보고서순서,주요Fig1–12및13–16필요지점구두설명,자료형태명시. 새wet항체설계논문으로오인하지않게감사.
