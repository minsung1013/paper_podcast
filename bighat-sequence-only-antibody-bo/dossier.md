# Sequence-only antibody BO 사실 검증 자료

## 서지

정확한 제목: Is Sequence Information All You Need for Bayesian Optimization of Antibodies?
저자: Sebastian W. Ober, Calvin McCarter, Aniruddh Raghu, Yucen Lily Li, Alan N. Amin, Andrew Gordon Wilson, Hunter Elliott.
소속: BigHat Biosciences / NYU (p.1). arXiv:2509.24933v1, 2025-09-29. p.1은 “Accepted into the AI for Science workshop (NeurIPS 2025)” 명시. NeurIPS 본학회 채택으로 바꾸지 않음.
원문: https://arxiv.org/abs/2509.24933

## 원문 순서와 도판

p.1 Abstract, §1 Introduction; p.2 §2 Background, §3 Methods, §3.1 Pareto-aware batch BO; p.3 §3.2 sequence-only, §3.3 structure, §3.4 antibody-specific; p.4 §3.5 soft constraint, §4 Experiments, §4.1 sequence, §4.2 structure; p.5 Figure1 sequence-only, Figure2 structural, §4.2.1 antibody-specific, §4.3 soft constraints; p.6 Figure3 representative soft-constraint results, §5 Discussion & future work; p.6–8 references; p.9 Appendix A Related work and B methods; p.10 B.2 Kermut, B.3 oracles, C ablation; p.11 Figure4 Kermut modifications, Figure5 antibody-specific variants, C.1; p.12 Figure6 full constraints, D, E structural exploration, F summary; p.13 Figure7 predicted RMSDs, Table1 methods.

그림1–6: x축0–9반복, 매반복50관측. 친화도 y축 부모 대비 KD 개선배수의 log10(위가 좋음); 안정성 y축 Tm °C. 선은3반복평균, 표준오차 막대. 그림7은 IgFold 예측구조 정렬 후 부모대비 mean RMSD. 실험구조 아니다. 곡선 끝값의 세밀한 숫자는 본문에 없는 경우 낭독에서 만들지 않았다.

## 설계/숫자 감사

- 새 비교는 전부 **in silico**(p.4). 실제 최적화 캠페인으로 학습한 내부 오라클을 사용. 이번 방법으로 새 후보를 만들고 모두 wet 측정한 연구가 아님. p.6에서 in vitro 검증을 future work로 명시.
- 초기 pool159개 변이체 중50개로 시작;9번 획득;각80개를 골라30개 무작위삭제→50개관측 추가(p.4,p.10). 확률적 누락은 현실의 서열의존 생산실패를 직접 재현하지 않는다.
- 각실험3회;평균+standard error(p.4).
- oracle:10 CARP/ByteNet regressors 기반;친화도 약285,000 phage-display/NGS서열 사전학습+6,881 BLI KD자료 미세조정;안정성 약537,000 NGS서열+9,556 NanoDSF Tm자료. ensemble crossvalidated Spearman .95 affinity/.72 Tm. **실제 simulation에는 속도상 ensemble첫모델하나만 사용**(p.10). ensemble상관을 singleoracle정확도로 동일시 금지.
- 목적은 affinity와Tm를 **별도로** 최적화. mean/uncertainty Pareto batch사용한다고 두 약물성질 동시다목적최적화가 아님.
- 대부분qHSRI acquisition+NSGA-II;LaMBO만 자체acquisition(p.3).
- OneHot-T:onehot+Tanimoto GP. BLO-T:BLOSUM62+Tanimoto. ESM-M:meanpooled ESM2-650M+Matérn5/2. IgFold-M:부모에정렬한 예측Cα좌표만,아미노산종류 직접입력없음. IgFold-ESM-M:좌표+임베딩concat. IgFold-BLO-T:커널가중합.
- Kermut-T는 원Kermut 그대로 아님. 수치정밀도,exact Cholesky,LBFGS,signalvariance매개변수화 수정 및 onehotTanimoto sequencekernel 사용(p.10).
- AbMPNN-Kermut-T:ProteinMPNN을 antibody-specificAbMPNN으로교체. 다른항체특화 ablation들은p.11.
- pLM constraint는 acquisition에 Sapiens pseudo-likelihood 가중. **실측발현가능확률/임상안전성확률 아님**. qHSRI구현은r_i가중,geneticsearch도pLM을고려(p.9).
- complex Ab-Ag구조 사용없음. 항체단독구조 비교. 모든structuralmodel범주의 무용성으로 일반화 금지(p.6).

## 핵심 결과와 제한

1. sequence-only affinity:Tanimoto강함;ESM-M자동우위없음. Tm:ESM초기강점이나Tanimoto후기따라잡음;LaMBO부진원인은smallinitialdata+autoencoder처음학습일가능성,확정원인아님(p.4–5).
2. 구조계열 affinity는BLO-T최종성과초과못함;IgFold-M초기강함;IgFold-BLO-T절충. Kermut-T는Tm강하지만affinity약함(p.4–5).
3. AbMPNN교체:Tm큰차이없고affinity특히초반개선(p.5).
4. softconstraint:affinity변화작거나일부불리;Tm에서C-OneHot-T가구조계열에상응(p.5–6,12). 모든방법에동일이득아님.
5. Fig7 predictedRMSD:sequence방식이부모구조에서더멀어짐. structurepreservation가설지원이나실험구조증거아님.
6. 데이터효율(초기속도)과최종성과 구별. 제목은제한된저자료컴퓨터benchmark에대한질문,모든항체문제에대한보편정리아님.
7. 한캠페인유래자료/학습oracle/세반복/복합체미포함/단순구조통합/실제wet미검증/다른developability미검증이범위제약.
8. 방법별tradeoff관찰과분자자체의affinity-Tm물리상충을동일시하면안됨.

## 검색·검증한 배경 1차 논문

- Ruffolo et al. Nature Communications (2023), DOI10.1038/s41467-023-38063-x, https://www.nature.com/articles/s41467-023-38063-x 및 https://pmc.ncbi.nlm.nih.gov/articles/PMC10129313/ . IgFold는항체언어모델표현+graphnetwork로항체좌표예측. 원문검색에서서지/초록/모델개요확인. 항체-표적복합체자세자동제공과구별.
- Dauparas et al. Science378,49–56(2022), DOI10.1126/science.add2187, https://pmc.ncbi.nlm.nih.gov/articles/PMC9997061/ . 고정구조조건부sequence design용ProteinMPNN;실제단백질설계검증보고. 본문에서는역접힘확률을통계구조kernel에쓰는배경으로만설명.
- Prihoda et al. mAbs14:2020203(2022), DOI10.1080/19420862.2021.2020203, https://pmc.ncbi.nlm.nih.gov/articles/PMC8837241/ . BioPhi는Sapiens인간화및OASis평가플랫폼. 이번논문에서Sapienspseudolikelihood를acquisitionsoftconstraint로재사용. 인간화원논문결과를이번BOwet검증으로혼동하지않음.

## 대본 검수

bighat-sequence-only-antibody-bo_dialogue.md: 실제한글음절16,816개(부록포함), 총문자24,639. 단독내레이터. 본문순서유지;보충도판은본문논의다음별도챕터. 모든수치의계산/실험출처구분. 부록은렌더제외를전제한출처목록.
