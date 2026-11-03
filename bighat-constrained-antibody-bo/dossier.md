# Constrained antibody BO 사실·구성 자료

## 서지와 실제 구조

제목 Antibody Design with Constrained Bayesian Optimization. 저자 Yimeng Zeng, Hunter Elliott, Phillip Maffettone, Peyton Greenside, Osbert Bastani, Jacob R. Gardner. University of Pennsylvania / BigHat Biosciences. 각쪽 머리글 Published at the GEM workshop, ICLR 2024. 본학회논문으로 확대금지. 제공PDF정확한날짜없음.
9쪽: p1초록/§1서론; p2§2background; p3§3methods; p4Single Sequence VAE계속/§4experiments/4.1setup/4.2oracles; p5Figure1/4.3wetresults/§5discussion; p6acknowledgments/refs p6–8; p9AppendixAcompute. 대본은원문순서,compute부록정보는setup에연결.

## 검증 수준과 핵심 수치

- 실제 **in vitro** 항체합성+KD/Tm측정 있음. optimization내부는학습oracle예측. 동물/임상아님.
- seed주변1–10무작위변이1.8million서열로single-sequenceVAE학습. 비편집부위제거,편집구간만복원. 1.8million wet분자아님(p4).
- TransformerVAE5encoder/5decoderlayers,KLweight.001,latent48dim,reconstructionaccuracy99.8%. 결합성공률아님(p4).
- constraints predictedTm>T, T60/65°C;CDRonly;seed중가장가까운것과editdistance≤k, k1–5. pairwise diversityτ=floor(k/2),따라서k1→τ0. 모든세팅강한다양성아님(p4).
- LOL-BO+SCBO+ROBOT;objective/constraintGP+VAE공동학습(p3). Levenshteindistance사용. 물리적다양성이나epitopediversity검증아님.
- oraclebudget고정없음,수렴까지탐색하고각온도/거리설정의best모아wet(p4).
- VAE6×48GBRTXA6000GPU20h;각최적화1×24GB/48GB A5000/A6000약1–3일(p9). 70wet후보라컴퓨팅도작다는뜻아님.
- affinity/Tm각10CNNensemble;split.8/.1/.1;KD~650kphagedisplaypretrain+1425CFPS/BLImeasurementsfine-tune. Tm같은CFPS항체NanoDSF. SpearmanCV.73KD/.62Tm(p4). 문턱실제충족보장아님.
- 최종방법70항체synthesized. baselineMLM+greedy:CDRproposal,동일oracle,predictedaffinity/Tmnon-dominatedsort,top128synthesisselection. 충분히합성된것측정. 실제측정분모/탈락세부미보고(p5).

## Figure1 직접 시각 확인

PDFp5를fitz렌더해확인. 유일한주요도판.
(a) 세boxplots:PreviousDesigns(분홍),MLM+Greedy(청회),ConstrainedLOLBO(주황). yKD(M),로그축10^-8–10^-4등,**낮을수록강한결합**. 주황median가장낮음;dashedbestseed;여러후보그선아래. 캡션:전체top10중7개최신방법. 원문정확medianKD/개선fold없어대본추정숫자안씀.
(b) percentTm>60C막대,Previous대략65%,greedy약74%,LOLBO약75%로보임. **정확수치원문미보고라대본약수치만**,100%아님. predictedconstraint항상충족과actualconstraint대부분충족구별.

## 해석 주의

- previousdesigns는서로다른시점의작고분포다른학습자료. 저자스스로공정비교곤란해한묶음처리. 전체차이알고리즘독립인과로확대금지.
- 가장좋은중앙값/top10중7은프로그램내측정관찰. 모든항체모든표적에보편적우위아님. 상세통계검정/각개값/생산실패수없음.
- affinity최적화+Tm하한유지. Tm무한최대화아님,모든developability품질확인아님.
- constraint보장대상은predictedTm/직접계산서열범위;실제Tm바로보장불가. 도판75%충족이이를보임.
- seed/CDReditable영역을사전에아는것이작은latent의조건. arbitraryprotein/deNovo새항체발견으로일반화금지.
- 후속diffusion/GAN통합은futurework,실험된구성아님.

## 검색 검증한 1차 배경

1. LOL-BO: Maus et al., NeurIPS35(2022). https://papers.neurips.cc/paper_files/paper/2022/hash/ded98d28f82342a39f371c013dfb3058-Abstract-Conference.html . 원초록확인:trustregion/encoder를deepkernel로공동학습해latent와input국소성정렬. 이번항체wet결과와구별.
2. SCBO: Eriksson&Poloczek,AISTATS2021,PMLR130:730–738. https://proceedings.mlr.press/v130/eriksson21a.html . 비싼고차원blackboxobjective와constraints를다루는방법. 원초록/서지확인. 항체실험아님.
3. ROBOT: Maus et al.,AISTATS2023,PMLR206:1779–1798. https://proceedings.mlr.press/v206/maus23a.html . 사용자정의거리로다양한고성능해집합,rankorderedBOtrustregions. 원초록/서지확인. 로봇실험장비아님.

## 제작 상태

대본 bighat-constrained-antibody-bo_dialogue.md 9,732한글음절/14,448총문자(부록포함). 단독내레이터6장+오프닝/마무리. 주요도판직접확인후구두설명. 실제측정과예측/역사적비교한계명시. 짧은워크숍본문정보량에맞춰반복없는분량으로완성.
