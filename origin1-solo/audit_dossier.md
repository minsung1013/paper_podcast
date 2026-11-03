# Origin-1 솔로 팟캐스트 사실·배경 감사 메모

이 문서는 대본이 아니라 원문 검증용 자료다. 쪽수는 제공 PDF의 인쇄 쪽수이며 PDF 뷰어의 1부터 세는 페이지와 같다. 본문 주장과 아래 외부 배경 논문을 구분한다.

## 1. 서지정보: 확실한 것과 확인 불가한 것

- 정확한 제목: **Origin-1: a generative AI platform for de novo antibody design against novel epitopes** (p.1).
- 첫 저자는 Simon Levine이며 Jonathan Edward King, Jacob Stern, David Grayson 등을 포함한 다수 저자가 동등 기여자로 표시된다. 교신저자는 Janani S. Iyer, Amir Shanehsazzadeh이다. 이메일은 jiyer@absci.com, ashanehsazzadeh@absci.com (p.1).
- 제공 PDF의 표지에는 정식 기관 소속 목록, 발표일, 투고일, 학술지명, 학회명, DOI가 없다. 따라서 “Absci 연구팀의 Origin-1 기술 원고”라고 소개할 수 있지만, “2026년 1월 14일 게재된 동료심사 논문”이라고 말하면 안 된다. 파일명은 게재일의 근거가 아니다.
- 원문이 제공하는 데이터 주소: https://github.com/AbSciBio/origin-1 (p.1).

## 2. 실제 원문 순서와 도판 지도

| 쪽 | 실제 절/도판 | 청취자에게 전할 핵심 |
|---|---|---|
| 2 | 0 Abstract; 1 Introduction 시작 | 새 에피토프에 대한 항체 설계 문제, 검증 결과 요약 |
| 2–4 | 1 Introduction | 기존 항체 설계 접근의 한계와 zero-prior 설정 |
| 4 | 2 Methods; 2.1 Overview; Figure 1 | 생성→서열→예측 점수→실험 검증의 전체 흐름 |
| 5 | 2.2 AbData; 2.3 Models; 2.3.1 AbsciDiff | 데이터와 원자 수준 구조 생성 |
| 6 | Figure 2, AbsciDiff 모델 개요 | Boltz-1 기반 구조, 조건부 확산과 서열 가설 |
| 7 | Figure 3, reverse diffusion trajectory | 잡음에서 복합체 구조를 점진적으로 복원 |
| 8–10 | 2.3.2 IgDesign2; Figure 4(p.10) | 구조 조건부 CDR 서열 생성, GNN+자기회귀 디코더 |
| 10–11 | 2.3.3 AbsciBind; Figure 5(p.11) | 결합 예측 평가 프로토콜과 8개 시스템 비교 |
| 11–12 | 2.3.4 In silico benchmarking | RFantibody와 계산 비교의 조건 |
| 12–13 | 2.4 Experimental validation; 2.4.1 Target selection; Table 1(p.13) | 열 개 표적, 선정 기준과 AZGP1 예외 |
| 14 | 2.4.2 Epitope, Framework, and CDR Length Selection; Figure 6 | 성공한 네 표적의 지정 에피토프 잔기 지도 |
| 15 | Table 2; 2.4.3 Library Design | 승인 항체 기반 네 프레임워크와 라이브러리 |
| 16 | 2.4.4 Lead Optimization; 2.4.5 In Vitro Methods; 3 Results; 3.1 | 최적화 절차 후 계산 결과 시작 |
| 17 | Table 3; Figure 7 | AbsciBind 점수 분포 비교 |
| 18 | Figure 8; 3.2 SPR Identifies Multiple Hits per Target | OASis 인간 유사성; SPR 히트 |
| 19 | Figure 9, COL6A3 | SPR/BLI/용액 복합체/구조 등 검증 패널 |
| 20 | Figure 10, AZGP1 | 결합·구조 검증과 품질 문제를 함께 읽을 것 |
| 21 | Figure 11, CHI3L2 | 최초 히트와 최적화 후 변이체를 구분 |
| 22 | Figure 12, IL36RA; 3.3 Orthogonal BLI and Complexation Assays | 최초 히트와 최적화 후 변이체를 구분 |
| 23 | 3.4 Affinity Optimization; 3.5 Developability | 약한 두 표적의 개선과 개발적합성 한계 |
| 24 | Table 4; 3.6 CryoEM; 3.7 HEKBlue | 개발적합성 수치, 두 복합체 구조, IL36RA 기능 |
| 25 | 4 Discussion | 의의와 후속 과제. 별도의 Conclusion 절은 없음 |
| 26–32 | 5 Acknowledgments; 6 References | 본문 종료 뒤 참고문헌 |
| 33–64 | 7 Supplementary Material | 세부 데이터/모델/비교/설계/실험 방법 |

주요 보충 도판: Supp. Fig.1 atom14(p.34), Fig.2 RFantibody 초기화(p.35), Fig.13 AbsciBind(p.48), Fig.14(p.49), Fig.15–16 설계 라이브러리(p.49–50), Supp. Table 5–7(p.52–54), Fig.17 SPR(p.57–58), Fig.18 복합체 겔(p.59), Fig.19 AZGP1 cryo-EM(p.62), Fig.20 COL6A3 cryo-EM(p.63). HEKBlue 상세 방법은 p.64다.

## 3. 반드시 구분해야 하는 주장

### 무엇이 de novo이고 무엇이 zero-prior인가

항체 전체를 아무 기반 없이 만든다는 의미가 아니다. 승인 항체 프레임워크를 토대로 중쇄·경쇄의 여섯 CDR을 설계한다. 실험에는 trastuzumab, relatlimab, dupilumab, sotrovimab의 네 프레임워크를 사용한다(Table 2, p.15). 계산 비교에는 trastuzumab, relatlimab, sotrovimab의 세 프레임워크를 사용한다(p.12). 둘을 혼동하지 않는다.

Zero-prior는 알려진 항체-항원 또는 단백질-단백질 복합체 구조로 해당 에피토프의 결합 방식을 직접 참고하지 않는 설정이다. 항원 구조까지 없다는 뜻이 아니다. 고품질 항원 구조, 사용자가 고른 에피토프, 프레임워크, 서열 정보를 조건으로 준다. 항원 선정은 해상도 3.5Å 미만, 적은 결손 잔기, 구매 가능한 단량체 시약, 알려진 복합체가 있는 단백질과의 서열 유사성 제한 등을 사용한다(p.12–14).

**AZGP1 예외:** 비항체 단백질과의 기존 복합체가 있었지만 PDB biological assembly 오류로 선정 당시 놓쳤다고 Table 1 주석에 밝힌다. 연구진은 그 기존 결합면과 다른 에피토프를 골랐다고 설명한다(p.13). “열 표적 모두 기존 복합체가 전혀 없다”는 단정은 부정확하다.

열 표적은 COL6A3, AZGP1, IL36RA, CHI3L2, ALCAM, AMBP, CLEC4A, KLK1, FOLR1, FOLR2다(Table 1). 뒤 여섯은 이 선택·설계·실험 프로토콜에서 히트를 얻지 못했다는 의미이며 영원히 설계 불가능한 표적이라는 의미가 아니다.

### 소수 실험과 대규모 계산은 동시에 사실이다

최종 최초 실험 라이브러리는 표적당 95개 설계다. 하지만 전체 계산 생성이 95회인 것은 아니다. 3,360개 설계 조건에서 Wide 단계 80,640개 구조를 생성하고 10,080개를 유지한다. Deep 단계는 241,920개 구조 생성, 30,240개 유지다. 두 단계의 유지된 40,320개 구조-서열 후보에서 500개 구조를 선택하고, 구조당 320개씩 총 160,000개 서열을 샘플링하는 과정 등을 거쳐 최종 95개를 고른다(p.15–16; p.49–54). 구조 생성 수와 서열 샘플 수는 다른 단위이므로 합쳐서 단일 ‘분자 수’로 발표하지 않는다.

최적화에서는 부모 항체별 94개 단일 변이체를 추가 시험한다(p.16, p.54–55). 따라서 “표적당 100개도 안 되는 최초 실험 후보”는 맞지만 “모든 최적화까지 100개 이하”는 틀리다. 계산 자원/벽시계 시간의 정확한 총량은 이 숫자만으로 단정하지 않는다.

### RFantibody와의 비교는 계산 평가다

RFantibody의 CDR 초기화를 이상화 좌표로 바꾸어 원래 루프 구조에 대한 사전정보를 줄였다. 그 밖의 설정은 기본값을 사용했다고 한다(p.11; Supp. Fig.2, p.35). AbsciGen에서는 다양성을 위해 beam search를 끈다. 비교 대상은 실제 성공한 네 표적이며 열 표적 전체에 대한 독립적인 실험 정면 비교가 아니다. 표적당 102개 설계 조건에서 조건당 구조 1개, 서열 8개를 생성한다(p.12).

Table 3(p.17): 평균 AbsciBind 점수는 RFantibody 0.270±0.112, AbsciGen 0.422±0.116이다. 0.5 이상 비율은 1.49% 대 28.37%로 약 19배다. 이는 **내부 예측 점수 임계값 통과 비율**이며 “실제 항체 결합 성공률이 20배” 또는 “임상 성공률이 20배”가 아니다. AbsciBind는 연구진의 자체 평가 프로토콜이다. 이 점수를 직접 최적화하도록 학습하지 않았다는 진술은 있으나 평가계의 독립성·일반성 한계를 없애지는 않는다.

RFantibody가 더 높은 다양성을 보이는 지표도 있다. 구조 조건부 HCDR3 고유 비율은 보충 표에서 대략 AbsciGen 49%, RFantibody 90%다(p.40–43). AbsciGen의 더 높은 점수가 모든 축의 우위를 의미하지 않는다.

AbsciBind의 8개 실험 시스템 검증에서는 AF-Multimer 다섯 체크포인트 중 최대값을 이용한 접근이 8개 중 7개에서 강한 성과를 보인다(Fig.5, p.11). 실제 운용에는 시간 약 80% 절약을 위해 Model 2 체크포인트를 쓴다. “운용 Model 2 자체가 7/8에서 최고”라고 바꾸지 않는다. 점수는 실제 결합친화도 KD나 자유에너지 자체가 아니다.

### 최초 히트, 직교 검증, 최적화 히트의 층위

SPR 최초 히트는 COL6A3 3개, AZGP1 4개, CHI3L2 1개, IL36RA 1개다(p.18). 4/10은 **표적 단위** 성공이며 모든 시험 분자의 40%가 결합한다는 뜻이 아니다.

최초 mAb의 BLI에서는 COL6A3 1개와 AZGP1 2개가 확인된다. CHI3L2, IL36RA의 최초 히트는 제한적인 BLI 신호만 보여 초기 단계에서 확정되지 않는다(p.22–23). 두 표적 부모의 KD는 2µM보다 약한 수준이었다. 최적화 한 차례 후 CHI3L2 약 4배, IL36RA 약 68배의 친화도 개선이 관찰되고 이후 직교 BLI 및 용액 복합체가 확인된다. 다른 변이체의 개선은 각각 약 2배, 26배다(p.23; Fig.11–12). 모든 최초 zero-shot 후보가 모든 검증을 통과한 것처럼 설명하지 않는다.

COL6A3 Fab은 항체 고정 방향에서 결합하지만 항원 고정 방향에서는 결합하지 않았다. 작은 항원 크기나 태그 간섭을 저자가 가설로 제시한다(p.22). 검증된 원인이라고 단정하지 않는다. AZGP1 Fab은 두 방향에서 결합한다.

### 구조 정확도는 두 복합체에서 확인했다

COL6A3와 AZGP1의 cryo-EM 해상도는 각각 3.0Å, 3.1Å다(p.24). 설계 모델과 실험 구조 사이 지표는 다음과 같다.

| 지표 | COL6A3 | AZGP1 |
|---|---:|---:|
| 전체 all-atom RMSD | 2.56Å | 1.79Å |
| Interface RMSD | 0.96Å | 1.35Å |
| Ligand RMSD | 1.48Å | 1.90Å |
| DockQ | 0.83 | 0.73 |
| HCDR3 RMSD | 0.661Å | 1.411Å |

해상도와 모델-실험 간 RMSD는 서로 다른 지표다. 네 표적 전체의 원자 수준 구조 검증이 아니다. cryo-EM은 Fab 복합체에서 수행했다. 도판 보조 결합체가 최종 치료 항체의 구성요소라는 오해를 피한다.

### 개발적합성과 실제 약물 개발 사이

Table 4(p.24)의 최고 후보들에서 COL6A3, CHI3L2는 대체로 양호한 개발적합성 결과를 보이지만 IL36RA에는 소수성 관련 경고가 있다. AZGP1은 자기회합, 소수성, 다중반응성 경고를 가진다고 본문이 직접 설명한다(p.23). 특히 AZGP1 AC-SINS는 25.7이며 COL6A3 1.6, IL36RA 0.6, CHI3L2 -0.1이다. AZGP1의 높은 열안정성 DSF 77.86°C가 다른 품질 문제를 없애지는 않는다.

OASis는 서열의 인간 항체 유사성 지표이며 사람에서의 면역원성/안전성 실험 결과가 아니다. 이 PDF는 동물 약효·약동학·독성 또는 인간 임상 검증을 보고하지 않는다. 세포 기능 실험까지의 성과를 전임상 약물 후보 확립이나 임상 검증으로 바꾸지 않는다.

### IL36RA 실험은 ‘염증 억제’가 아니라 브레이크 해제

IL36RA는 IL-36 수용체의 자연 길항제로 IL-36γ 신호를 억제하는 브레이크다. 이 원고의 항체는 **IL36RA 단백질을 막아 그 억제를 풀고 IL-36γ 의존 신호를 회복**한다(p.13, p.24, p.64). IL-36 수용체 자체를 차단하거나 IL-36γ를 중화하는 항체가 아니다.

HEKBlue 세포에서 NF-κB/AP-1 활성화에 따른 분비형 알칼리인산분해효소(SEAP) 리포터를 읽는다. 방법은 IL-36γ 2pM, IL36RA 50nM, 항체 1µM–1nM 단계 희석, 24시간 후 620nm 흡광도 판독이다(p.64). 부모 항체는 비기능적이고 친화도 개선 후 변이체가 신호 억제를 되돌리며, 최고 기능적 EC50은 104nM이다. 이 숫자는 KD가 아니다. 암 면역 침윤 증강의 잠재성은 생물학적 동기이지 이 원고가 동물 종양 효능을 증명했다는 뜻이 아니다.

## 4. 외부 1차 문헌 배경: 본 원고 결과와 분리해서 사용

아래 서지와 초록은 원 논문/유럽 PMC의 원문 서지·초록으로 확인했다. 배경을 풀어 주는 용도이며 Origin-1 데이터의 추가 실험으로 취급하지 않는다.

1. **Watson et al., De novo design of protein structure and function with RFdiffusion. Nature (2023), DOI 10.1038/s41586-023-06415-8.** https://doi.org/10.1038/s41586-023-06415-8
   - RoseTTAFold를 구조 잡음 제거 과제에 맞추어 생성형 단백질 backbone 설계로 확장했다. 단량체, 대칭 조립체, 결합체 등 여러 과제를 실험으로 검증했다. “확산 모델로 단백질 구조를 만든다”는 개념적 선행 배경이다. 일반 단백질 구조 생성의 성공이 곧 항체 여섯 CDR의 성공을 보장하지는 않는다.
2. **Bennett et al., Atomically accurate de novo design of antibodies with RFdiffusion. Nature, online 2025-11-05; 649, 183–193 (2026 issue), DOI 10.1038/s41586-025-09721-5.** https://pubmed.ncbi.nlm.nih.gov/41193805/
   - 항체에 맞춘 RFdiffusion과 효모 디스플레이 스크리닝으로 VHH, scFv 및 full antibody를 지정 에피토프에 설계한다. VHH/scFv의 결합 자세를 cryo-EM으로 검증하며 최초 수십~수백 nM 친화도의 일부 후보를 OrthoRep로 단일 자릿수 nM까지 개선한다. Origin-1의 계산 비교 상대를 이해하는 배경이다. 출판된 이 논문의 결과와 Origin-1에서 수정해 실행한 RFantibody 벤치마크 결과를 섞지 않는다.
3. **Abramson et al., Accurate structure prediction of biomolecular interactions with AlphaFold 3. Nature 630, 493–500 (2024), DOI 10.1038/s41586-024-07487-w.** https://pubmed.ncbi.nlm.nih.gov/38718835/
   - 확산 기반 구조 예측으로 단백질, 핵산, 소분자, 이온, 변형 잔기의 복합체를 다룬다. 논문은 AF-Multimer v2.3보다 개선된 항체-항원 예측을 보고한다. 구조 **예측**, 새로운 서열 **설계**, 실제 **결합 실험**은 구별해야 한다. Origin-1의 AbsciDiff가 사용한 Boltz-1/AF3 계열 설계 원리를 설명할 때 유용하다.
4. **Towne et al., Interleukin-36 (IL-36) ligands require processing for full agonist (IL-36α, IL-36β, and IL-36γ) or antagonist (IL-36Ra) activity. J Biol Chem (2011), DOI 10.1074/jbc.M111.267922.** https://pubmed.ncbi.nlm.nih.gov/21965679/ ; https://pmc.ncbi.nlm.nih.gov/articles/PMC3234937/
   - IL36Ra가 IL36 수용체 복합체 형성을 막는 자연 길항제임을 기능 실험으로 보여 주며, N말단 가공이 활성에 중요하다고 보고한다. Origin-1 항체의 기능 방향을 이해하는 근거다. “억제자를 억제하면 신호가 회복된다”는 논리를 설명한다. 이 가공 실험을 Origin-1 항체의 독립 재현 증거로 소개하지 않는다.

## 5. 한국어 발음·용어 일관성 제안

공식 한국어 발음이 있는지 불분명한 모델·유전자명은 편의를 위한 제안이다. 첫 등장에서 풀어 설명하고 이후 한 표현으로 유지한다.

| 표기 | 낭독 제안 | 첫 등장 설명 |
|---|---|---|
| Origin-1 | 오리진 원 | 이번 항체 설계 플랫폼 |
| Absci | 앱사이 | 연구 기업 |
| AbsciGen / AbsciDiff / AbsciBind | 앱사이젠 / 앱사이디프 / 앱사이바인드 | 생성 묶음 / 구조 생성 / 결합 평가 |
| AbData | 앱데이터 | 학습 데이터 |
| IgDesign2 | 아이지 디자인 투 | 구조 조건부 항체 서열 모델 |
| Boltz-1 | 볼츠 원 | 구조 예측 모델 계열 |
| RFdiffusion / RFantibody | 알에프 디퓨전 / 알에프 앤티바디 | 비교 모델 |
| ProteinMPNN | 프로틴 엠피엔엔 | 구조 조건부 단백질 서열 설계 |
| COL6A3 | 씨오엘 식스 에이 쓰리 | 콜라겐 식스 알파 쓰리 관련 표적 |
| AZGP1 | 에이제트 지피 원 | zinc-alpha-2-glycoprotein |
| CHI3L2 | 씨에이치아이 쓰리 엘 투 | 키티나아제 유사 단백질 쓰리 엘 투 |
| IL36RA | 아이엘 삼십육 알에이 | 인터루킨 삼십육 수용체 길항제 |
| CDR / Fv / Fab / Fc | 씨디알 / 에프브이 / 팹 / 에프씨 | 결합 루프 / 가변부 / 결합 조각 / 상수부 꼬리 |
| mAb | 단클론항체 | 소리로 엠에이비보다 자연스러움 |
| SPR / BLI | 에스피알 / 비엘아이 | 표면 플라스몬 공명 / 생물층 간섭계 |
| cryo-EM | 크라이오 이엠 | 극저온 전자현미경 |
| ipTM / RMSD / DockQ | 아이피티엠 / 알엠에스디 / 도크큐 | 예측 신뢰도 / 구조 편차 / 결합 자세 평가 |
| OASis | 오아시스 | 인간 항체 서열 유사성 |
| HIC / AC-SINS / DSF / DLS | 에이치아이씨 / 에이씨 신스 / 디에스에프 / 디엘에스 | 소수성 / 자기회합 / 열안정성 / 입자 크기 |
| aSEC | 분석용 크기배제 크로마토그래피 | 분자 크기에 따른 분리 |
| HEKBlue / SEAP | 헥블루 / 분비형 알칼리인산분해효소 | 세포 리포터 / 신호를 색 변화로 읽는 효소 |
| KD / EC50 | 케이디 / 이씨 오십 | 결합친화도 / 반최대 기능 농도 |

AZGP1의 정확한 풀 이름은 zinc-alpha-2-glycoprotein이다. 한국어 번역을 무리하게 확정하기보다 표적 기호를 유지하는 편이 안전하다. 반응성을 뜻하는 polyreactivity는 “다중반응성”, multispecific antibody는 “다중특이항체”로 구분한다. 전자는 원치 않는 여러 결합, 후자는 의도적으로 여러 표적에 결합하도록 만든 형식이다.

## 6. 대본 마감 전 최소 사실 점검

- 초기에 95개 실험 설계를 뽑기까지 큰 계산 탐색이 있었음을 한 문장 포함.
- 4/10은 표적 단위, CHI3L2/IL36RA의 직교·기능 검증은 최적화 후라는 점 포함.
- 내부 예측 점수 약 19배와 실험/임상 성공률을 혼동하지 않음.
- AZGP1의 표적 선정 예외 및 개발적합성 문제를 삭제하지 않음.
- IL36RA 중화의 결과는 IL36 신호 회복이며 억제 방향이 반대가 되지 않도록 확인.
- 논문이 하지 않은 동물·임상 결과나 정식 게재일을 추가하지 않음.
