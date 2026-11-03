# Inverse protein folding / BO-IF 사실 및 구성 자료

## 서지·판본

정확제목 Inverse Protein Folding Using Deep Bayesian Optimization. Natalie Maus*,Yimeng Zeng*,Daniel Allen Anderson,Phillip Maffettone,Aaron Solomon,Peyton Greenside,Osbert Bastani,Jacob R.Gardner. Penn/BigHat. *동등기여. 제공20쪽PDF는arXiv2305.18089v1,2023-05-25,Preprint.Underreview(p1). 정식학술지/학회확정서지로확대금지. https://arxiv.org/abs/2305.18089

## 실제 원문 순서

p1Abstract/§1Intro; p2Intro기여/§2Background; p3Fig1/배경계속; p4BO배경/§3InverseFoldingasOptimization/3.1Strategy; p5latentBO/3.2architecture/3.3extensions; p6extensions/§4Experiments/4.1efficiency; p7§4.2unconditional/Table1/4.3constraints; p8Fig2,3/4.4diverse; p9Fig4,5/§5DiscussionandLimitations; p10discussion끝/referencesp10–15; p16AppendixA/Fig6,7; p17–20Fig8–17sequencealignments. 대본에서appendixdiversity결과를본문같은주제마지막에연결,그뒤논의. 모든주요그림1–6구두설명,7–17군집설명.

## 핵심 검증 수준

**전부계산평가**. 새단백질wet합성/측정/결정구조/기능실험없음. 목표RFdiffusion골격→후보생성→ESMFold예측→TM/RMSD평가. 구조예측오류가목적함수오류로그대로연결(p9–10). 실제fold/기능입증으로표현금지. 항체특이설계논문아니고일반단백질inversefolding,BigHat저자참여.

## 수치·모델

- 24RFdiffusionunconditionalmonomerbackbones,길이100–150aa. 목표별150000sequenceevals(p7).
- 1000ESM-IF초기샘플로BO시작(p6). 기존generativemodel없이독립빈손방법아님.
- baselineESM-IFGVPTransformer;T1e-6시초기몇개뒤개선멈춤→T1사용(p6). baseline단한번vsBO15만번비교아님.
- TransformerVAE6encoder/6decoder,47Mparams,UniRef1.5millionsequenceslength100–300,latent1024,KL1e-4(p5).
- sparsevariationalGPPPGPR;deepkernel2hidden256→256features(p5).
- LOLBO기반,제약SCBO;constraintGP+objectiveGP+VAEjoint. diverseROBOT,editdistance(p5–6).
- Table1p7:BO47M vs GVPTransformer142M;pretrain1RTXA6000vs32RTX8000;GPUdays6vs653;150kevalruntime50vs48GPUhours. 하드웨어차이/모델역할차이있음. 자체VAE작음이전체pipeline소형/기존ESMIFESMFold불필요뜻아님.
- inference둘다1×48GBRTXA6000;baselinebatch20,BOThompsonbatch10;runtime83%ESMFold(p6). p7일반서술~GPUday와Table50h불일치있어대본은구체표50h설명.

## 결과·도판 직접확인

p3,8,9이미지렌더로직접확인.
Fig1:목표파랑(cyan),ESMIF노랑,BO분홍;6예시. 한예.898→.989,다른.781→.925. 예측구조의겹침,실험해상도아님.
Fig2p8:24구조,1-TMscore막대(낮음좋음). error48%reduction,SE±.69%;RMSD28%,SE±.81%. TM자체48%증가아님. all24TM개선저자주장.
Fig3p8:meanpLDDT.732BOvs.710baseline,대체로비슷한확신. 목표닮음과확신구별.
Fig4p9:5다양서열alignment,TM평균.95±.002. 생화학속성색. 작용기전다양성아님.
Fig5leftp9:9구조humanclassifier≥.8;right8구조5해,pairwiseedit≥20. diversity막대평균,오차막대min/max,SE아님. bestsingleBO함께.
Fig6p16:3구조10해,거리≥5로완화. 5해거리20과같은난이도아님.
Fig7–17MSA:5해8구조/10해3구조의서열제시. 서열다양성만,실제접힘기능다양성검증아님.

## 제약 결과 주의

humanclassifier ESM2-150Mfine-tune47khuman64knonhumanUniRef,accuracy93%(p7). **.8threshold=classifieroutput**,80%sequenceidentity/80%humanprotein구성/80%clinicalnonimmunogenicity확률아님.
ESMIF0.2%는humanthreshold와TM>.8 **동시**충족. constraintalone통과율아님.
9구조constrainedvsfilteredbaseline:1-TMerror48.364%±9.480SE,RMSD34.454%±7.082SE.
8구조5diverse,pairdistance20:meanerror48.640%±8.003SE,RMSD33.617%±5.520SE(p8).
classifier인간vs비인간구별정확도와실제면역원성예측정확도동일시금지. deNovodesignclinical검증아님.

## 검색 확인한 1차 배경

1.Hsuetal.,Learninginversefoldingfrommillionsofpredictedstructures,ICML2022PMLR162:8946–8970. https://proceedings.mlr.press/v162/hsu22a.html . 실험구조+12MAlphaFold예측구조증강,GVPTransformer구조→서열. 초록/원서지확인. BOIF현재비교구성의배경.
2.Linetal.,Evolutionary-scalepredictionofatomic-levelproteinstructurewithalanguagemodel,Science3791123–1130(2023),DOI10.1126/science.ade2574. https://pubmed.ncbi.nlm.nih.gov/36927031/ . sequenceonly언어모델기반ESMFold구조추론. 초록/서지확인. 이번BO평가도구,실험정답아님.
3.Watsonetal.,Broadlyapplicableandaccurateproteindesignbyintegratingstructurepredictionnetworksanddiffusiongenerativemodels,bioRxiv2022,DOI10.1101/2022.12.09.519842. https://www.biorxiv.org/content/10.1101/2022.12.09.519842v1 . RFdiffusion당시원고. 검색원초록/서지확인. 목표골격생성,자체BO실험검증과구별.

## 제작

bighat-inverse-folding-deep-bo_dialogue.md:한글음절12,445/총문자18,559(부록포함). header포함,솔로8장. 주요제한/숫자직접감사. pron.json/title.txt함께저장. 오디오·배포root담당.
