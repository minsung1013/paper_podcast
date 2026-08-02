# 🎙️ 논문 팟캐스트: Protein Design Enters the Artificial Intelligence Era: Foundations, Tools, and Emerging Paradigms (단백질 설계, 인공지능 시대로 들어서다: 기초, 도구, 그리고 떠오르는 패러다임)

> 진행: **내레이터**(전문가 · 오디오 에세이 강의형)
> 📄 게재: Computational and Structural Biotechnology Journal (Comput. Struct. Biotechnol. J.), 2026;35(1):Article 0105 — 발행처는 American Association for the Advancement of Science(AAAS), DOI: 10.34133/csbj.0105 · 2026 (Submitted 28 January 2026, Accepted 20 April 2026, Published 1 June 2026) · 소속: 교신저자 Yanlin Mi — School of Computer Science and Information Technology, University College Cork(UCC), Cork, Ireland (및 Centre for Research Training in Artificial Intelligence, UCC). 공동 소속으로 Yunnan University(중국), Munster Technological University(아일랜드) 등.
> 논문의 구조(초록 → 서론 (The AI-Driven Protein Engineering Landscape) → 방법·기술 (Key AI Technologies in Protein Design) → 도구 (AI-Driven Protein Design Tools) → 결과·논의 (Applications and Impact) → 결론·미래방향 (Challenges and Future Directions / Conclusion))를 그대로 따라가며, 각 파트의 핵심 개념·결과·발견을 내레이터 한 명이 강의처럼 들려줍니다.

---

## 오프닝

**내레이터:** 여러분, 여기 아주 작은 단백질 하나가 있다고 해봅시다. 아미노산 100개짜리, 세포 안에서는 티끌만 한 존재죠. 그런데 이 작은 사슬에 들어갈 수 있는 아미노산 배열의 경우의 수는 20의 100제곱, 대략 10의 130제곱입니다. 우주에 있는 원자를 다 합쳐도 10의 80제곱쯤이니까, 그보다도 압도적으로 큰 숫자예요. 여기서 의문이 하나 생기죠. 그 천문학적인 공간에서, 어떻게 실제로 접히고 기능하는 단 하나의 서열을 골라낼 수 있을까요? 오늘 이야기는 바로 그 질문에서 출발합니다.

먼저 오늘 우리가 함께 읽을 논문을 소개하죠. 제목은 "Protein Design Enters the Artificial Intelligence Era" — 우리말로 "단백질 설계, 인공지능 시대로 들어서다: 기초, 도구, 그리고 떠오르는 패러다임"입니다. 2026년, 저널 'Computational and Structural Biotechnology Journal' 35권에 실린 리뷰 논문이고, 발행처는 미국과학진흥협회 AAAS입니다. 교신저자는 아일랜드 코크대학교, University College Cork의 얀린 미(Yanlin Mi). 컴퓨터과학과 인공지능 연구센터 소속이고, 중국 윈난대학교와 아일랜드 먼스터공대 연구자들도 함께했습니다.

자, 그럼 이 논문이 풀려는 문제가 뭔지 짚어볼까요. 저자들이 먼저 묻는 건, 단백질 설계라는 게 왜 그렇게 오래 어려웠나 하는 겁니다. 전통적인 방법은 크게 두 갈래였어요. 하나는 '합리적 설계' — 구조 지식과 생화학 원리로 이로운 돌연변이를 예측하는 방식. 다른 하나는 '유도 진화' — 실험실에서 자연선택을 흉내 내 성질을 다듬는 방식이죠. 강력했지만 벽이 분명했습니다. 접힘이 워낙 복잡하고, 뒤져야 할 서열 공간이 아까 그 천문학적 숫자거든요.

이 뿌리를 저자들은 안핀슨의 도그마까지 거슬러 올라갑니다 — 아미노산 서열이 3차원 구조를 결정한다는 원리죠. 초기 계산 설계 프레임워크 Rosetta가 바로 이 원리를 물리 기반 에너지 함수로 구현했지만, 계산 비용이 크고 복잡한 동역학에는 약했습니다. 그러다 전환점이 왔죠. AlphaFold2가 구조 예측에서 실험에 준하는 정확도를 달성한 겁니다. 여기서 저자들은 결정적인 관점 하나를 세웁니다. AI는 이 생물물리 원리를 대체하는 게 아니라, 감당 안 되던 에너지 지형 탐색을 '우회'해서, 진화적·공간적 패턴을 데이터에서 직접 학습한다는 거예요. 그래서 흩어진 방법론과 도구를 한자리에 정리할, 이 리뷰가 필요했던 겁니다.

그럼 오늘의 여정을 미리 그려보죠. 우리는 이 논문을 순서 그대로 따라갈 겁니다. 먼저 초록에서, AI가 '서열-구조-기능'의 관계를 해독하기 시작했다는 약속을 듣습니다. 이어 서론, '인공지능이 이끄는 단백질 공학의 풍경'에서는 방금 이야기한 배경과 시장의 판돈을 살핍니다. 그다음 방법, '단백질 설계의 핵심 AI 기술'에서는 이 분야를 떠받치는 네 개의 기둥 — 딥러닝, 확산 모델, 단백질 언어 모델, 지식 그래프를 하나씩 열어봅니다. 도구 파트, 'AI 기반 단백질 설계 도구'에서는 AlphaFold2, RoseTTAFold, ESM-2, ProteinMPNN 같은 스타 플레이어들을 벤치마크 수치와 함께 만나죠. 결과와 논의, '응용과 임팩트'에서는 치료제부터 감미 단백질, 세탁 효소까지 실제 성과를 훑습니다. 그리고 마지막, '과제와 미래 방향'. 사실 오늘 이야기의 진짜 무게중심은 여기 있어요. 컴퓨터가 그럴듯하다고 예측한 설계가 시험관에서는 자주 실패한다는 것, 저자들 표현으로 '환각' 문제, 그리고 성공률 20% 미만이라는 냉정한 숫자입니다.

컴퓨터의 꿈과 시험관의 현실 사이, 그 갭. 자, 그럼 이제 그 이야기 속으로 들어가 봅시다.

---

## [챕터 1] 초록

**내레이터:** 여러분, 방금 우리는 그 아득한 갭 앞에 섰습니다. 이제 저자들이 논문 맨 앞, 초록에서 그 갭을 어떻게 압축해 예고하는지 들어봅시다.

초록의 첫 약속은 이겁니다. 인공지능이 마침내 단백질의 '서열-구조-기능' 관계를 해독하기 시작했다는 것. 이 관계가 왜 핵심일까요? 서열은 우리가 손에 쥔 글자열이고, 구조는 그 글자가 접혀 만든 3차원 모양, 기능은 그 모양이 세포 안에서 하는 일입니다. 이 세 층을 잇는 사슬을 풀어내는 게 단백질 과학의 오랜 숙원이었죠. 저자들은 그 열쇠로 세 가지를 듭니다. 딥러닝, 단백질 언어 모델, 그리고 지식 그래프.

여기서 저는 두 개의 축을 나란히 세우고 싶습니다. 초록이 대비시키는 두 얼굴이거든요. 한쪽은 AlphaFold2. 서열을 넣으면 구조를 맞히는 '판별' 모델이죠. 그 정확도가 실험에 준하는 수준, 논문 표현으로 'near-experimental'입니다. 나중에 자세히 보겠지만, CASP라는 구조 예측 올림픽에서 실험 오차와 거의 구분되지 않는 성적을 냈어요. 다른 한쪽은 트랜스포머 기반 언어 모델. 이건 반대 방향입니다. 정답을 맞히는 게 아니라, 기능이라는 제약 아래 세상에 없던 새 서열을 처음부터 써 내려가는 '생성' 모델, 이른바 데 노보 설계죠. 맞히기와 만들기. 이 두 축이 오늘 이야기 전체를 관통합니다.

그럼 이게 어디에 쓰일까요? 초록은 세 무대를 지목합니다. 병을 겨냥하는 치료 단백질 공학, 산업의 일꾼인 효소 촉매, 그리고 생명을 부품처럼 조립하는 합성생물학. 뒤에서 감미 단백질 sweelin, 세탁 효소 같은 실제 사례로 이 무대들을 하나씩 밟아볼 겁니다.

그런데 말이죠, 이 리뷰가 다른 흥분한 글들과 다른 지점이 바로 여기입니다. 초록은 성과만 자랑하고 끝내지 않아요. 곧바로 세 가지 숙제를 못 박습니다. 첫째, 모델이 왜 그렇게 판단했는지 들여다보기 어렵다는 해석가능성. 둘째, 학습 데이터에 깔린 편향 — 언어 모델은 비슷한 단백질에 쏠려 있고, 구조 예측기는 이미 아는 구조를 외워버릴 위험이 있죠. 셋째, 그리고 가장 무거운, 실험 검증률. 컴퓨터 안에서 아무리 그럴듯해도 시험관에서 실제로 되느냐는 완전히 다른 문제라는 겁니다.

자, 이게 왜 의미 있냐면요. 초록에서 이미 '갭을 메운다'는 말이 나온다는 게 핵심입니다. 이 리뷰는 처음부터 끝까지, AI가 그려낸 설계도와 시험관의 현실 사이 그 틈에 관한 이야기예요. 성과의 축포가 아니라, 그 틈을 정직하게 재고 메우려는 시도. 바로 그 태도가 초록 한 문단에 이미 새겨져 있습니다.

---

## [챕터 2] 서론 (The AI-Driven Protein Engineering Landscape)

**내레이터:** 여러분, 시장이 이만큼 커지고 있다는 건 이 갭을 메우려는 시도에 이미 큰 판돈이 걸려 있다는 뜻입니다.

숫자부터 짚어볼까요. 단백질 공학 시장은 2024년에 약 43억 5천만 달러였습니다. 이듬해 2025년엔 50억 9천만 달러. 그리고 2034년엔 약 208억 6천만 달러에 이를 거라는 전망이 나와 있죠. 연평균 성장률로 따지면 16.97퍼센트. 십 년 사이 네 배가 넘게 커진다는 그림입니다. 그런데 여기서 저는 한 박자 멈추고 싶어요. 이 208억 달러는 어디까지나 '전망'입니다. 불확실하다는 뜻이죠. 실제로 지금 산업 현장을 들여다보면, 95퍼센트 이상은 여전히 전통적인 스크리닝, 그러니까 수많은 후보를 일일이 걸러내는 옛 방식에 기대고 있습니다. 숫자로 규모감은 갖되, 이미 다 이뤄진 미래처럼 착각하진 말자는 겁니다.

자, 그럼 이 시장에서 '단백질을 설계한다'는 게 정확히 뭘 뜻할까요? 저자들은 그 목표를 두 갈래로 나눕니다. 이게 오늘 서론의 핵심 구분이에요.

첫째는 '조작', 영어로 engineering입니다. 이미 자연에 존재하는 단백질을 뼈대, 그러니까 스캐폴드로 삼고, 그 위에 손을 대는 거예요. 열에 잘 견디도록 안정성을 올린다든가, 촉매가 한 번에 처리하는 회전율을 끌어올린다든가. 있는 집을 리모델링하는 셈이죠.

둘째는 완전히 다릅니다. 'de novo 설계', 데 노보 설계. 라틴어로 '처음부터'라는 뜻이에요. 진화의 기록 어디에도 없던, 자연이 한 번도 시도해본 적 없는 완전히 새로운 위상과 서열을 백지에서 지어 올리는 겁니다. 리모델링이 아니라 맨땅에 설계도부터 그려 새 건물을 세우는 것. 이걸 생물물리 원리로, 혹은 생성 모델의 잠재공간에서 끌어냅니다.

여기서 이 리뷰가 그려 보이는 한 장의 지도를 잠깐 말로 펼쳐 보죠. 논문 첫 그림은 이 분야 전체를 한 장에 담은 조감도입니다. 왼쪽 위에는 이 모든 걸 떠받치는 네 개의 기술 기둥 — 딥러닝, 그 안의 CNN·GNN·어텐션, 그리고 언어 모델, 지식 그래프, 분자동역학이 놓여 있어요. 가운데엔 알록달록한 3차원 단백질 구조가 자리하고, 오른쪽 위로는 그 기술이 낳은 스타 도구들, AlphaFold와 RoseTTAFold가 있죠. 아래로 눈을 내리면 왼쪽엔 세 갈래 응용 무대 — 치료제, 산업, 환경, 오른쪽엔 그 모든 게 만들어내는 시장 임팩트가 있습니다. 그러니까 이 그림은 하나의 흐름이에요. 기술 기둥이 도구를 낳고, 도구가 응용을 낳고, 응용이 시장을 만든다. 오늘 우리가 걸어갈 길 전체가 이 한 장에 미리 그려져 있는 셈입니다.

그래서 이 구분이 왜 중요하냐면요. 조작이냐 데 노보냐 — 이 갈림길이 곧 AI에게 요구하는 난이도의 갈림길이거든요. 있는 걸 다듬는 조작은 그나마 발 디딜 땅이 있습니다. 하지만 아무것도 없는 백지에서 접히고 기능하는 단 하나의 서열을 지어내는 데 노보 설계, 그건 바로 오프닝에서 만난 그 천문학적 공간 한복판으로 걸어 들어가는 일입니다. 그리고 이 어마어마한 판돈과 야심의 한가운데에, AI가 왜 판도를 바꾸는 전환점이 되었는가 — 그 이야기가 이제 우리를 기다리고 있습니다.

**내레이터:** 여러분, 그렇다면 이 어마어마한 서열 공간 앞에서, AI가 등장하기 전 사람들은 대체 무엇을 붙들고 있었을까요? 두 개의 도구였습니다. 하나는 '합리적 설계', 구조 지식과 생화학 원리로 "이 자리를 이렇게 바꾸면 좋아지겠다"를 예측하는 방식. 다른 하나는 '유도 진화', 무작위로 돌연변이를 뿌린 뒤 좋은 것만 골라내길 반복하는 방식이죠. 둘 다 강력했습니다. 프랜시스 아놀드는 유도 진화로 2018년 노벨상까지 받았으니까요. 그런데 벽이 있었어요. 유도 진화로 실제 훑을 수 있는 변이체는 많아야 10의 8제곱에서 13제곱 개 남짓. 아까 그 10의 130제곱짜리 공간에 비하면 티끌의 티끌입니다. 그러니 자주 '지역 최적해'에, 그러니까 근처의 작은 언덕 꼭대기에 갇혀버렸죠.

이 벽의 뿌리에 안핀슨의 도그마가 있습니다. 1961년, 안핀슨은 리보뉴클레아제라는 단백질을 화학물질로 펼쳐놓았다가 그 화학물질을 다시 걷어냈어요. 그랬더니 단백질이 스스로 원래 모양으로 도로 접히더라는 겁니다. 여기서 결론이 나옵니다 — 서열이 최종 3차원 구조를 결정한다, 그리고 단백질은 자유에너지가 가장 낮은, 가장 안정한 형태로 접힌다. 이 공로로 안핀슨은 1972년 노벨상을 받았죠.

자, 그럼 이 원리를 컴퓨터에 심으면 설계가 되겠죠? 바로 그게 데이비드 베이커의 Rosetta였습니다. 물리 기반 에너지 함수 — 반데르발스 힘, 수소결합, 용매화, 정전기 같은 항들을 파라미터 천에서 이천 개쯤으로 손수 조립해, 어떤 구조가 얼마나 안정한지 점수를 매기고, 거꾸로 그 구조에 가장 잘 맞는 최저 에너지 서열을 찾는 방식이죠. 2003년엔 자연에 없던 완전히 새로운 접힘, Top7을 만들어 원리를 입증했습니다. 그런데 한계가 분명했어요. 에너지 함수를 손으로 만들다 보니 근사와 누락이 많아, '접히는 서열'과 '안 접히는 서열'을 원자 수준에서 잘 구별하지 못했습니다. 계산 비용은 크고, 여러 상태를 오가는 동역학에는 약했죠.

그래서 이게 왜 의미 있냐면요. 여기서 AI의 관점 전환이 갈립니다. AI는 이 물리 원리를 뒤엎지 않아요. 다만, 에너지 지형을 힘겹게 한 걸음씩 더듬는 대신, 진화가 남긴 패턴을 데이터베이스에서 직접 학습해 그 탐색을 통째로 '우회'합니다. 지도를 새로 그리는 게 아니라, 수억 번의 진화 실험이 이미 남긴 발자국을 읽어버리는 거죠. 바로 이 우회가, 다음 이야기의 문을 엽니다.

**내레이터:** 자, 그럼 이 판돈이 실제로 얼마나 큰지, 이름과 숫자로 확인해 볼까요? 논문은 최근의 굵직한 AI-제약 파트너십을 표 하나에 정리해 두었습니다. 그 표를 말로 펼쳐 보죠. 가로축엔 발표 시점, AI 회사, 손잡은 제약 파트너, 겨냥한 질환, 그리고 계약의 '최대 잠재가치'가 나란히 적혀 있어요.

숫자를 읽어 드리겠습니다. 구글 딥마인드에서 갈라져 나온 Isomorphic Labs는 일라이 릴리와 최대 17억 달러, 노바티스와는 최대 12억 달러 규모로 손을 잡았습니다. Generate Biomedicines는 암젠과 최대 19억 달러 — 여기엔 'Chroma'라는 생성 AI 플랫폼이 쓰였죠. Absci는 머크와 최대 6억 1천만 달러, 항체 설계로. BioMap은 사노피와 10억 달러 이상. 표 하나에 담긴 계약만 합쳐도 마일스톤 기준으로 열 자릿수를 우습게 넘깁니다.

여기서 세 가지 흐름이 읽힙니다. 첫째, 재정 규모가 크다. 둘째, 겨냥이 넓어지고 있다 — 처음엔 항체 같은 큰 분자에서 시작했는데, 이제 저분자, 그러니까 작은 화학 약물로까지 범위를 넓히고 있어요. 셋째, 방향이 '생성'으로 옮겨가고 있다 — 있는 걸 맞히는 걸 넘어 새것을 지어내는 쪽으로요.

그런데 말이죠, 여기서 반드시 한 박자 멈춰야 합니다. 이 17억, 19억이라는 숫자, 곧이곧대로 통장에 꽂히는 돈이 아니에요. 대부분은 '마일스톤 포함 최대 잠재가치', 업계에서 농담처럼 '바이오벅스'라 부르는 겁니다. 개발 단계마다 목표를 달성해야 조금씩 풀리는 조건부 금액이죠. 실제 계약할 때 먼저 건네는 선지급금은 그 극히 일부입니다. 릴리 딜의 선지급은 약 4,500만 달러, 사노피 딜은 약 1,000만 달러 수준으로 알려져 있어요. 발표된 총액과 실제 선지급 사이 격차가 수십 배에 이르는 겁니다.

그래서 이게 왜 의미 있냐면요. 이 표가 진짜로 말하는 건 두 가지예요. 하나, 세계 최대 제약사들이 AI 설계에 판돈을 걸 만큼 이 분야를 진지하게 본다는 것. 둘, 그럼에도 이 모든 계약이 공통으로 안고 있는 난관 — 컴퓨터가 그려낸 디지털 설계도를, 사람 몸에 안전하고, 효과 있고, 대량 생산까지 되는 '진짜 약'으로 번역하는 일. 표의 마지막 칸이 하나같이 이 '번역'을 핵심 과제로 꼽습니다. 큰 돈은 이미 걸렸지만, 그 돈이 실제로 풀리느냐는 바로 그 번역에 달려 있는 거죠. 다시, 우리가 오프닝에서 만난 그 갭입니다.

---

## [챕터 3] 방법·기술 (Key AI Technologies in Protein Design)

**내레이터:** 자, 그럼 이제 그 우회를 실제로 해내는 엔진룸으로 내려가 봅시다. 저자들은 AI 단백질 설계를 떠받치는 네 개의 기둥 — 딥러닝, 확산 모델, 단백질 언어 모델, 지식 그래프를 세우는데, 그 모든 걸 관통하는 첫 번째 갈림길이 하나 있습니다. 바로 '맞히기'냐 '만들기'냐입니다.

여기서 의문이 하나 생기죠. 같은 딥러닝인데 왜 굳이 둘로 나눌까요? 방향이 정반대이기 때문입니다. 한쪽은 '판별 모델'입니다. 서열을 넣으면 구조 좌표를 내놓죠. 대표선수가 AlphaFold2예요. "이 글자열은 어떤 모양으로 접히는가?" 정답을 맞히는 쪽입니다. 다른 한쪽은 '생성 모델'. 이건 역문제를 풉니다. 원하는 위상이나 기능을 먼저 정해두고, 거꾸로 "그 모양이 되려면 어떤 서열이어야 하나?"를 지어내죠. 고정된 3차원 백본에 어울리는 서열을 채워 넣는 ProteinMPNN, 아예 새 백본 자체를 노이즈에서 빚어내는 RFdiffusion이 여기 속합니다. 사진을 보고 이름을 맞히는 사람과, 이름만 듣고 얼굴을 그려내는 화가의 차이라고 보시면 됩니다.

그런데 이 모델들은 세상을 서로 다른 방식으로 봅니다. 언어 모델은 단백질을 1차원, 그러니까 한 줄로 늘어선 글자열로 봅니다. 여기엔 큰 가정 하나가 깔려 있어요 — 진화적 '공변이'가 구조를 암호화한다는 겁니다. 3차원에서 가까이 붙은 두 잔기는 진화 과정에서 함께 돌연변이하는 경향이 있으니, 서열 통계만 잘 읽으면 구조 정보가 자연히 배어 나온다는 거죠. 반면 그래프 모델과 확산 모델은 처음부터 3차원 공간 표현에 조건을 겁니다. 잔기를 점으로, 가까운 잔기를 선으로 이은 그래프 위에서, 혹은 실제 좌표 위에서 직접 설계하는 겁니다.

논문의 아키텍처 비교 표를 잠깐 말로 펼쳐 보면 이 대비가 선명해집니다. 그래프 신경망 계열인 ProteinMPNN은 고정된 3차원 백본으로 서열을 설계하죠 — 정확하고 빠르지만, 새 폴드 자체를 만들진 못합니다. 언어 모델 계열인 ESM-2나 ProGen2는 방대한 서열로 진화 패턴을 학습하지만, 3차원 제어가 간접적이라 접힘을 보장하진 못하죠. 확산 모델인 RFdiffusion은 자연에 없던 새 폴드를 정밀하게 조건화해 생성하는 대신, 계산이 무겁습니다. 판별에서 생성으로 넘어가는 흐름이 이 표 한 장에 압축돼 있어요.

그런데 이 모든 모델이 공유하는 아킬레스건이 하나 있습니다. 학습 데이터의 편향이에요. 언어 모델은 UniProt 같은 서열 데이터베이스로 배우는데, 여기엔 서로 닮은 단백질, 즉 호몰로지가 잔뜩 쏠려 있습니다. 그러다 보니 데이터에 잘 표현되지 않은 영역으로 나가면 일반화에 실패하죠. 구조 예측기는 다른 함정에 빠집니다. PDB에 이미 있는 구조 모티프를 그대로 '암기'해버리는, 이른바 데이터 누출입니다. 시험 문제를 미리 외운 학생 같은 거죠.

그래서 이게 왜 의미 있냐면요. 판별이냐 생성이냐, 1차원이냐 3차원이냐 하는 구분은 단순한 분류학이 아닙니다. 각 모델이 무엇을 잘하고 무엇에서 무너지는지를 미리 알려주는 지도예요. 그리고 그 지도가 가리키는 공통의 절벽이 바로 데이터 편향입니다. 자연이 이미 걸어본 길은 놀랍도록 잘 따라가지만, 진짜 새것 — 데 노보 — 앞에서는 그 편향이 발목을 잡죠. 우리가 오프닝에서 만난 그 갭이, 사실은 데이터 그 자체에 이미 새겨져 있는 겁니다.

**내레이터:** 여러분, 그럼 이 모델들은 3차원 공간을 대체 어떻게 이해할까요? 여기 아주 골치 아픈 문제가 하나 숨어 있습니다. 같은 단백질을 손에 쥐고 이리저리 돌리거나 옆으로 밀어봐도, 그건 여전히 같은 단백질이잖아요. 회전시켜도, 위치를 옮겨도, 본질은 그대로죠. 그런데 컴퓨터한테는 이게 전혀 당연하지 않습니다. 좌표 숫자가 통째로 바뀌어 버리니까요.

이 회전과 평행이동 전체를 수학에서는 SE(3)라고 부릅니다. "에스이-쓰리". 회전만 따로 떼면 SO(3), "에스오-쓰리"고요. 그래서 모델이 갖춰야 할 성질이 두 가지입니다. 하나는 '등변성' — 입력 구조를 돌리면 출력도 똑같이 따라 돈다. 다른 하나는 '불변성' — 입력을 돌려도 결합력 점수 같은 최종 값은 꿈쩍 안 한다. 이 대칭성을 아키텍처에 아예 심어두지 않으면 어떻게 될까요? 같은 단백질을 온갖 각도로 뒤집은 데이터를 무한정 밀어 넣어야 합니다. 낭비도 그런 낭비가 없고, 일반화에도 실패하죠.

AlphaFold2는 이걸 아주 영리하게 풉니다. 'Invariant Point Attention', 줄여서 IPA라는 장치죠. 각 아미노산을 저마다의 국소 3차원 좌표틀, 그러니까 회전과 이동으로 정의된 작은 프레임 위에 올려놓습니다. 그리고 "벡터의 길이는 아무리 돌리고 옮겨도 변하지 않는다"는 단순한 수학을 씁니다. 어떤 각도로 뒤집어 놓든 같은 답이 나오는 거예요.

자, 이제 논문의 워크플로우 그림 속 세 패널을 말로 펼쳐 보죠. 첫 번째 패널은 CNN, 팽창 합성곱입니다. 이게 뭐냐면, 시야를 점점 넓혀가며 보는 창이에요. 팽창 폭을 1, 2, 4, 8로 키워가면서, 바로 옆 잔기부터 저 멀리 떨어진 잔기까지 여러 스케일의 패턴을 한꺼번에 잡아냅니다. 여기에 '잔차 연결'을 더해, 층이 깊어져도 학습 신호가 사라지지 않게 붙들어 두죠. 두 번째 패널은 GNN, 그래프 신경망입니다. 잔기를 점으로 놓고, 그 사이의 공유결합은 물론 수소결합·소수성·정전기 같은 비공유 상호작용까지 '선'의 특징으로 새겨 넣어요. 그리고 이웃끼리 정보를 주고받는 '메시지 패싱'을 여러 번 반복하는데, 이 층들이 바로 SO(3)-등변, 즉 회전을 존중하도록 설계돼 있습니다. 세 번째 패널은 위치 특이 어텐션 — 서열상 멀리 떨어진 잔기라도 3차원에서 가까우면 서로에게 높은 가중치를 주며 관계를 학습하죠.

그래서 이게 왜 의미 있냐면요. 대칭성을 아키텍처에 새겨 넣는다는 건, 물리 세계의 상식을 모델에게 '공짜로' 쥐여주는 일입니다. 돌려도 같다는 걸 데이터로 억지로 가르치는 대신, 구조 자체에 못 박아 두는 거죠. 바로 이 대칭성 존중이, AlphaFold2가 그토록 적은 낭비로 그토록 정확할 수 있었던 숨은 뼈대입니다.

**내레이터:** 확산 모델, 여기서 새로운 질문이 하나 열립니다. 앞서 본 그래프 모델은 이미 있는 백본에 서열만 채웠고, 언어 모델은 글자열만 다뤘죠. 그런데 자연에 아예 없던 3차원 골격 자체를, 백지에서 빚어내려면 어떻게 해야 할까요? 저자들의 답이 바로 확산 모델입니다.

원리는 뜻밖에도 '망가뜨리기'에서 시작합니다. 일상 비유를 들어볼게요. 맑은 물 한 잔에 잉크를 한 방울씩 떨어뜨려 완전히 뿌옇게 만든다고 상상해 보세요. 확산 모델은 진짜 단백질 구조에 가우시안 노이즈를 조금씩, 조금씩 더해 결국 완전한 무작위 상태로 뭉갭니다. 그리고 신경망에게 시킵니다 — 이 과정을 거꾸로 돌려봐라. 뿌연 데서 노이즈를 한 겹씩 걷어내며, 없던 구조를 빚어내게 하는 거죠. 신경망이 실제로 배우는 건 "지금 이 자리에서 노이즈를 어느 방향으로 지워야 진짜에 가까워지나", 그 방향, 이른바 '스코어'입니다.

이걸 세 갈래로 나눠 볼게요. 첫째, RFdiffusion. 연속형입니다. 3차원 좌표 공간에서 직접 백본을 확산시키죠. RoseTTAFold를 확산 모델로 개조한 건데, 핵심 재주가 '모티프 스캐폴딩'입니다. 효소의 활성부위 같은 결정적 기하 구조는 고정해 둔 채, 그 주변 골격만 새로 자라나게 하는 거예요. 둘째, Chroma. GNN 기반 점수 모델에 '프로그래밍 가능한 제약'을 겁니다 — 대칭이면 대칭, 크기면 크기, 원하는 조건을 명령처럼 걸 수 있죠. 셋째, EvoDiff. 이건 결이 다릅니다. 이산형이에요. 3차원 구조 사전정보 없이, 20종 아미노산이라는 범주형 서열 공간에서 직접 확산합니다. 그래서 정해진 구조가 없는 본질적 무질서 단백질, 그리고 완전히 새로운 위상을 만드는 데 강점을 보이죠.

논문의 아키텍처 비교 표에서 확산 모델은 이렇게 정리됩니다. 자연에 없던 새 폴드를, 대칭이나 크기 같은 제약으로 정밀하게 조건화해 생성한다 — 이게 강점이에요. 앞선 그래프 모델이 새 폴드를 못 만들고, 언어 모델은 3차원 제어가 간접적이라던 그 빈칸을, 확산이 메웁니다. 다만 표의 '한계' 칸이 두 가지를 짚죠. 하나, 계산이 무겁다 — 노이즈를 여러 단계 걷어내야 하니 추론 비용이 큽니다. 둘, 생물학적 기능까지 보장하진 못한다.

그래서 이게 왜 의미 있냐면요. 확산 모델은 기존 생성 방식, 그러니까 한 글자씩 순서대로 뽑는 자기회귀나 GAN에 비해 훨씬 다양하고, 훨씬 세밀하게 제어됩니다. 백지에서 새 골격을 빚되, 원하는 조건을 명령으로 걸 수 있는 것 — 이게 데 노보 설계의 진짜 문을 연 열쇠입니다. 다만 그 문 너머, 만들어낸 모양이 정말 기능하느냐는 여전히 시험관의 몫으로 남죠.

**내레이터:** 자, 그럼 방금 본 확산 모델과 달리, 단백질을 '글'처럼 읽는 쪽은 어떻게 새 서열을 지어낼까요? 여기서 논문은 아주 직관적인 평행 비유를 하나 그려 보입니다. 한쪽엔 영어 언어 모델이 있어요. 'Politics'나 'Sports' 같은 제어 태그를 앞에 붙여주면, 그 주제에 맞는 문장을 척척 써 내려가죠. 그 옆에 나란히 단백질 언어 모델을 놓습니다. 이번엔 태그가 'Immunoglobulin', 그러니까 면역글로불린이나 'Phage Lysozyme', 파지 라이소자임 같은 단백질 패밀리 이름이에요. 그 명세를 프롬프트로 주면, 모델은 생화학적으로 유효한 아미노산 서열을 생성합니다. 문장을 쓰듯 단백질을 쓰는 거죠.

그럼 이 모델들은 어떻게 배울까요? 세 가지 기법이 나옵니다. 구조를 인지한 채 일부 잔기를 가리고 맞히는 마스크 예측, 비슷한 것과 다른 것을 밀고 당기는 대조 학습, 그리고 쉬운 것부터 어려운 것 순으로 가르치는 커리큘럼 학습입니다.

여기에 논문은 두 축을 더 얹어요. 하나는 지식 그래프. 흩어진 문헌에서 단백질 상호작용 관계를 자동으로 뽑아내, 그 임베딩을 다시 언어 모델의 조건 태그로 써먹습니다. 다른 하나는 분자동역학과 AI의 결합 — 신경망 기반 집단변수, 온라인 편향 퍼텐셜, 그리고 양자계산을 학습한 ML 힘장과 미분가능 힘장으로 샘플링과 정확도를 함께 끌어올리죠.

한마디로, 서열은 문장처럼 생성하고, 문헌은 그래프로 엮고, 움직임은 힘장으로 붙잡는다 — AI가 단백질을 읽는 세 번째 방식입니다.

---

## [챕터 4] 도구 (AI-Driven Protein Design Tools)

**내레이터:** 자, 네 개의 기둥을 세웠으니 이제 그 기둥 위에 올라선 실제 도구들을 만나볼 차례입니다. 그 첫 번째 스타 플레이어, AlphaFold2죠.

여기서 의문이 하나 생기죠. 아까 그 천문학적 서열 공간에서, AlphaFold2는 대체 어떻게 서열 하나만 보고 그 모양을 맞힐까요? 혼자 서열만 노려보는 게 아닙니다. 입력이 세 갈래예요. 표적 서열 그 자체, 그 서열의 친척들을 모아놓은 다중서열정렬 MSA, 그리고 이미 밝혀진 비슷한 구조들, 호몰로지 템플릿. 이 셋을 'Evoformer'라는 블록에 넣고 수십 번 정보를 주고받게 한 뒤, 정적인 3차원 원자 좌표를 뽑아냅니다. 여기에 pLDDT, "피-엘디디티"라는 자기신뢰도 점수까지 잔기마다 붙여주죠 — "이 부분은 내가 확신한다, 저 부분은 좀 자신 없다"를 스스로 실토하는 겁니다.

성적표를 볼까요. 논문의 상업 플랫폼 비교 표, 그러니까 AlphaFold2·RoseTTAFold·ESM-2를 나란히 세운 그 표에서 AlphaFold2 칸을 읽어보면 이렇습니다. 벤치마크 성능으로 CASP14 도메인 중앙값 백본 RMSD가 0.96 옹스트롬. 옹스트롬은 100억 분의 1미터, 원자 하나 크기 수준입니다. 그러니까 예측한 골격과 실제 골격이 원자 하나 남짓밖에 안 어긋난다는 뜻이에요. 실험으로 푼 구조와 사실상 구분이 안 되는 정확도죠. 여기에 더해 CASP14에서 전체 접힘의 닮음을 재는 TM-score가 0.9를 넘는 경우가 흔했고, GDT-TS는 90을 웃돌았습니다. 50년 묵은 단백질 접힘 문제가 처음으로 실험 수준에서 풀린 순간이었어요.

그런데 말이죠, 바로 이 표의 마지막 칸, '핵심 한계'가 훨씬 중요합니다. AlphaFold2가 내놓는 건 어디까지나 '정적인 단일 구조', 딱 한 장의 스냅샷이에요. 단백질은 살아서 꿈틀대는데 말이죠. 그래서 시간에 따라 모양이 바뀌는 동역학, 한쪽을 건드리면 먼 곳이 반응하는 알로스테릭, 접혀가는 경로 — 이런 건 시뮬레이션하지 못합니다. 게다가 결정적으로, 그 예측 구조가 실험실에서 실제로 발현되고 접힐지, 그 실험적 실현성은 보장하지 않아요.

그래서 이게 왜 의미 있냐면요. AlphaFold2는 '맞히기'의 정점입니다. 옹스트롬 단위로 구조를 맞히죠. 하지만 한 장의 정지 사진일 뿐, 살아 움직이는 단백질도, 그게 시험관에서 진짜 되는지도 말해주지 않습니다. 다시, 우리가 오프닝에서 만난 그 갭. 정확한 예측조차 아직 시험관의 판정을 대신하진 못하는 겁니다.

**내레이터:** 자, AlphaFold2가 '맞히기'의 정점이었다면, 같은 문제를 조금 다른 방식으로 푼 도구가 바로 옆에 있습니다. 베이커 연구실의 RoseTTAFold죠. 여기서 의문이 하나 생기죠. AlphaFold2가 이미 그렇게 잘 맞히는데, 왜 또 다른 도구가 필요했을까요? 핵심은 '구조를 바라보는 방식'에 있습니다.

RoseTTAFold의 별명은 '3-트랙 아키텍처'예요. 단백질을 딱 한 관점에서 보지 않고, 세 개의 정보 흐름을 나란히, 동시에 굴립니다. 첫 번째 트랙은 1차원, 그러니까 한 줄로 늘어선 서열 정보. 두 번째 트랙은 2차원, 잔기와 잔기 사이 거리를 담은 거리맵. 세 번째 트랙은 3차원, 실제 원자 좌표죠. 세 명의 전문가가 각자 다른 각도에서 같은 단백질을 들여다보며 쉴 새 없이 메모를 주고받는 장면을 떠올려 보세요. 서열 전문가가 알아챈 힌트를 거리 전문가가 받고, 그걸 다시 좌표 전문가가 실제 3차원에 반영하고, 또 그 결과가 서열 쪽으로 되돌아가는 겁니다. 이 세 트랙의 대화가 RoseTTAFold의 심장이에요.

성적표를 볼까요. 논문이 AlphaFold2·RoseTTAFold·ESM-2를 나란히 세운 상업 플랫폼 비교 표, 그 RoseTTAFold 칸을 읽어보면 단량체 기준 TM-score가 0.8을 넘습니다. TM-score는 0에서 1 사이 값으로, 전체 접힘이 얼마나 닮았는지를 재는 지표인데, 보통 0.5만 넘어도 같은 폴드로 봅니다. 0.8이면 상당히 정확하다는 뜻이죠. 다만 같은 표의 한계 칸이 짚습니다 — 계산 비용이 크고, 단일 사슬에 한정된다는 점. 그럼에도 실전에 안착했어요. Outpace Bio, Arzeda 같은 회사들이 이 도구를 상용화 파이프라인에 올렸습니다.

자, 그런데 이 표의 세 번째 자리엔 결이 완전히 다른 선수가 앉아 있습니다. 메타의 ESM-2죠. 앞선 둘이 구조를 '맞히는' 도구라면, ESM-2는 단백질을 '글'로 읽는 언어 모델입니다. 규모부터 압도적이에요. 33층짜리 트랜스포머에, 파라미터가 최대 150억 개. 실무에서는 6억 5천만짜리 변이형을 흔히 쓰지만요. 그런데 놀라운 건 성적입니다. 표를 읽어보면, 2차 구조 예측 정확도가 85퍼센트를 넘고, 어느 잔기와 어느 잔기가 3차원에서 맞닿는지를 맞히는 접촉 예측 정밀도가 70퍼센트를 넘습니다. 게다가 돌연변이가 기능에 미치는 효과를 예측하는 상관계수가 0.7을 넘는데, 이게 '제로샷', 그러니까 그 과제를 따로 배운 적 없이 서열만 방대하게 읽고 나온 성적이라는 겁니다.

그래서 이게 왜 의미 있냐면요. 여기서 결정적인 전환이 보입니다. AlphaFold2와 RoseTTAFold는 구조를 맞히려고 서열의 친척들, MSA를 끌어와야 했죠. 그런데 ESM-2는 명시적인 정렬 없이, 오직 방대한 서열을 '읽은' 것만으로 구조의 접촉이며 돌연변이 효과까지 짚어냅니다. 진화가 서열 안에 새겨둔 통계를, 언어 모델이 통째로 삼켜버린 거예요. 맞히기에서 만들기로 넘어가는 다리가, 바로 이 언어 모델 위에 놓입니다.

**내레이터:** 여러분, 그렇다면 스타 도구 몇 개 말고, 그 사이사이를 채우는 일꾼들은 누구일까요? 논문은 표 하나에 이 전문 도구 생태계를 죽 늘어놓습니다. 도구 이름, 개발자, 핵심 기술, 특징, 주 응용을 나란히 세운 표죠.

가장 먼저 눈에 띄는 건 베이커 연구실의 ProteinMPNN입니다. 앞서 만난 '만들기'의 대표선수죠. 고정된 3차원 백본을 그래프로 보고, 그 모양으로 접힐 가능성이 가장 높은 서열을 채워 넣습니다. 성적이 놀라워요. 자연 서열을 그대로 되맞히는 회복률이 약 52퍼센트 — 옛 물리 기반 Rosetta의 33퍼센트 남짓보다 20퍼센트포인트가량 높습니다. 게다가 속도는 단백질 하나에 1초 미만. Rosetta가 약 4분 걸리던 걸 200배 가까이 앞지른 겁니다.

그 곁에 특기별 선수들이 늘어섭니다. OmegaFold는 MSA 없이도, 친척 서열이 없는 고아 단백질조차 TM-score 0.7을 넘겨 접습니다. ProGen2는 10억 개가 넘는 서열을 배워 최대 400 아미노산짜리를 백지에서 써 내려가죠. 여기에 ColabFold, ESM-IF1, trRosetta, ProtGPT2까지 — 저마다 다른 빈틈을 메웁니다.

한마디로, 코어 플랫폼 뒤에는 각자 한 가지씩 특기를 지닌 전문 도구들의 생태계가 받치고 있는 겁니다.

---

## [챕터 5] 결과·논의 (Applications and Impact)

**내레이터:** 여러분, 그럼 이 모든 도구와 기둥이 결국 무엇을 만들어냈을까요? 이제 실제 응용의 무대로 내려가, 그 첫 무대인 치료제 이야기부터 열어봅시다.

여기서 의문이 하나 생기죠. AI로 설계한 항체가 기존 항체보다 대체 뭐가 나을까요? 논문이 드는 첫 사례가 '항체 나노케이지'입니다. 나노케이지, 이름 그대로 아주 작은 우리, 케이지예요. AI가 항체들을 아무렇게나 붙이는 게 아니라, 정교한 기하학적 배열로, 그러니까 대칭적인 새장처럼 딱 맞춰 조립합니다. 이렇게 배열을 설계하면 뭐가 좋을까요? 두 가지입니다. 하나, 조직 침투가 좋아집니다. 원하는 곳까지 더 잘 파고들죠. 둘, 표적 외 효과가 줄어듭니다. 엉뚱한 곳을 건드리는 부작용이 줄어드는 거예요. 무작정 흩뿌린 항체가 아니라, 기하 구조로 정밀하게 조율된 항체 — 이게 AI 설계가 여는 새 문입니다.

그럼 이게 돈이 되는 이야기냐? 됩니다. 앞서 우리가 파트너십 표를 펼쳐 봤죠. 그 표의 한 조각을 다시 들여다보면, 2023년 4분기, 그러니까 단 한 분기에만 이런 굵직한 파트너십 네 건이 몰렸고, 그 규모를 합치면 총 22억 달러에 이릅니다. 넉 달 남짓한 시간에 20억 달러가 넘는 판돈이 치료 단백질 설계 한쪽으로 쏠린 거예요. 시장이 이 방향을 얼마나 진지하게 보고 있는지, 숫자가 대신 말해줍니다.

무대를 백신으로 옮겨볼까요. 여기선 두 갈래가 나옵니다. 하나는 판을 까는 큰 이니셔티브예요. 하버드 T.H. Chan 공중보건대학원과 Human Vaccines Project가 함께 세운 'Human Immunomics Initiative' — 인간 면역계 전체를 데이터로 읽어내 백신 설계에 쓰겠다는 큰 그림이죠. 다른 하나는 아주 구체적인 성과입니다. Magar 연구진이 머신러닝 모델을 세워, 1,900개가 넘는 항원-항체 서열을 분석했어요. 그리고 그 방대한 서열 더미에서, COVID-19에 듣는 후보 항체 8종을 골라냈습니다. 수천 개의 후보를 컴퓨터가 먼저 훑어 여덟 개로 좁혀준 거죠.

그래서 이게 왜 의미 있냐면요. 치료제야말로 AI 단백질 설계가 가장 큰 판돈과 가장 큰 기대를 동시에 받는 무대이기 때문입니다. 항체를 기하학적으로 조율해 더 잘 듣게 만들고, 수천 개 서열에서 될 만한 후보만 빠르게 추려내는 것 — AI는 여기서 놀라운 속도로 '가설'을 만들어냅니다. 다만 잊지 마세요. 22억 달러의 판돈도, 여덟 개의 후보 항체도, 아직은 출발선입니다. 그게 진짜 약이 되는지는, 다시 시험관과 임상이 판정합니다.

**내레이터:** 여러분, 그럼 AI 단백질 설계가 우리 혀끝까지 온다면 어떤 모습일까요? 여기 아주 맛있는 사례가 하나 있습니다. 감미 단백질, 이름하여 'sweelin'입니다.

먼저 배경을 깔아보죠. 자연에는 설탕이 아니면서도 강렬하게 단맛을 내는 단백질들이 있어요. 그중 하나가 열대 베리에서 나오는 monellin, 모넬린입니다. 문제는 이 단백질이 열에 약하다는 거예요. 45도만 넘어가도 구조가 풀어져 버립니다, 이른바 변성이죠. 그런데 식품 공정을 생각해 보세요. 토마토소스를 끓이고, 초콜릿을 녹이고 — 열이 안 들어가는 데가 거의 없습니다. 아무리 달아도 45도에서 무너지는 단백질은 식품에 못 쓰는 겁니다.

자, 여기서 이스라엘의 Amai Proteins가 등장합니다. 이들이 쓴 도구가 'AI-CPD', 그러니까 AI 기반 계산 단백질 설계 플랫폼이에요. 이 플랫폼의 영리한 점은 학습 재료였습니다. 극한 환경에서 사는 생물들의 단백질 구조를 분석한 거예요. 펄펄 끓는 온천이나 혹독한 조건에서도 멀쩡히 버티는 단백질들 말이죠. 거기서 "무엇이 단백질을 뜨거운 데서도 안 풀어지게 하는가"라는 열안정성의 문법을 읽어냈습니다. 그리고 그 문법을 모넬린에 옮겨 심어, 열에 강한 새 감미 단백질 sweelin을 설계했습니다.

결과가 어땠을까요? 세 가지가 핵심입니다. 첫째, 열안정성. 원본 모넬린은 45도에서 변성됐지만, sweelin은 고온에서도 안정적으로 버팁니다. 둘째, 당 감축. 맛을 해치지 않으면서 설탕을 40에서 70퍼센트까지 줄일 수 있었어요. 셋째, 그리고 가장 인상적인 대목 — 실제 관능 검사입니다. 토마토소스와 초콜릿에 넣어 전문 시식자들에게 맛보게 했는데, 이들이 기존 제품과의 차이를 감지하지 못했습니다. 게다가 미국에서 GRAS, 그러니까 '일반적으로 안전하다고 인정되는' 지위까지 받았죠.

그래서 이게 왜 의미 있냐면요. 앞서 본 항체나 효소가 실험실의 성취였다면, sweelin은 AI 설계 단백질이 규제를 통과해 실제 식탁 위 제품으로 가는 문턱을 넘은 사례입니다. 흥미로운 건 여기서 AI가 한 일의 성격이에요. 백지에서 완전히 새것을 꿈꾼 게 아니라, 자연이 이미 극한 생물에 숨겨둔 열안정성의 원리를 학습해, 쓸모 있는 단백질에 이식한 거죠. 앞서 이야기한 '조작'의 손맛에 가깝습니다. 발 디딜 땅이 있는 문제. 바로 그래서 이 사례는, AI 설계가 가장 빠르게 현실이 되는 지점이 어디인지를 조용히 일러줍니다 — 자연이라는 거대한 데이터베이스에 이미 답의 조각들이 흩어져 있는, 그런 문제에서 말이죠.

**내레이터:** 산업 응용, 여기서 질문을 하나 던져봅시다. 앞서 본 감미 단백질이 우리 혀끝의 이야기였다면, 눈에 안 보이는 곳에서 조용히 세상을 굴리는 단백질은 어디 있을까요? 바로 산업 효소, 생촉매입니다.

먼저 판의 크기를 보죠. 산업 효소 시장은 2019년에 약 86억 3천만 달러였습니다. 그리고 2027년엔 약 145억 달러에 이를 거라는 전망이 나와 있어요. 십 년이 채 안 되는 사이에 거의 두 배 가까이 커지는 그림이죠. 왜 이렇게 커질까요? 효소는 우리가 아는 가장 정교한 촉매거든요. 세제 속에서 얼룩을 분해하고, 종이를 표백하고, 바이오연료를 만들고 — 화학 공정을 상온·상압에서, 훨씬 적은 에너지로 돌립니다. 지속가능성이라는 시대의 요구와 정확히 맞아떨어지는 거예요.

그럼 AI는 여기서 뭘 했을까요? 두 기업 사례가 그 답을 손에 잡히게 보여줍니다.

첫째, Unilever와 Arzeda의 협업입니다. 이들은 세탁 세제에 들어가는 얼룩 제거 효소를 새로 설계했어요. 결과가 인상적입니다. 같은 세정력을 내면서도 필요한 성분을 50퍼센트나 줄였습니다. 절반으로요. 그런데 진짜 놀라운 건 개발 속도예요. 이 효소를 18개월 만에 만들어냈습니다. 전통적인 방식으로는 이런 개발에 몇 년씩 걸리던 걸, 대략 다섯 배 빠르게 앞당긴 겁니다. 여기서 AI가 한 일의 성격을 짚어볼까요. 앞서 유도 진화 이야기에서, 실제로 훑을 수 있는 변이체가 아무리 많아야 10의 8제곱에서 13제곱 개 남짓이라 지역 최적해에 갇히기 쉽다고 했죠. AI는 그 방대한 서열 공간에서 될 만한 후보를 미리 좁혀줍니다. 그래서 다섯 배라는 속도가 나온 거예요.

둘째, BASF의 'Emollient Maestro'입니다. 이건 결이 조금 달라요. 효소 하나를 설계하는 게 아니라, 머신러닝으로 최적의 에몰리언트, 그러니까 피부를 매끄럽게 하는 화장품·개인관리 제품 성분들의 조합을 탐색하는 도구입니다. 수많은 성분을 어떻게 배합해야 원하는 감촉과 성능이 나오는지, 그 방대한 조합의 공간을 AI가 대신 뒤져주는 거죠. 단백질 하나를 넘어, 제품 배합 전체로 AI 설계의 손길이 뻗은 사례입니다.

그래서 이게 왜 의미 있냐면요. 치료제 무대가 가장 큰 판돈과 가장 먼 결승선을 동시에 가졌다면, 산업 효소는 AI 단백질 설계가 이미 조용히 성과를 내고 있는 무대입니다. 성분 절반, 개발 기간 다섯 배 단축 — 이건 전망이 아니라 이미 일어난 일이에요. 다만 잊지 마세요. 이런 성공 사례들 뒤에도, 앞서 말씀드린 현실이 버티고 있습니다. 지금 이 순간에도 산업 현장의 95퍼센트 이상은 여전히 전통적인 스크리닝에 기대고 있어요. AI가 문을 열어젖힌 건 분명하지만, 그 문으로 세상 전체가 넘어간 건 아직 아닌 겁니다.

**내레이터:** 여러분, 그럼 이 모든 성과를 딛고, 이 시장은 앞으로 어디까지 갈까요? 논문은 2034년 약 208억 6천만 달러라는 전망을 다시 꺼냅니다. 하지만 곧바로 못을 박죠 — 10년짜리 예측은 매우 불확실하다고요.

왜 이 숫자를 곧이곧대로 믿으면 안 될까요? 현실이 아직 그만큼 안 왔기 때문입니다. 지금 이 순간에도 상업적 단백질 공학의 95퍼센트 이상은 여전히 전통적 스크리닝에 기대고 있어요. 병목은 두 가지입니다. 하나, AI 설계의 낮은 in vitro, 그러니까 시험관 검증률. 컴퓨터가 그럴듯하다 해도 실제로 되는 건 일부죠. 둘, 그 검증을 대량으로 돌릴 자동화 습식실험을 구축하는 비용이 만만치 않습니다.

그래서 제약사들은 어떻게 움직일까요? 앞서 본 파트너십 표가 답입니다. 회사를 통째로 인수하기보다, 전략적 파트너십으로 신중하게, 한 발씩 채택하고 있어요. 예측과 실험 사이 그 갭이, 아직은 완전히 메워지지 않았다는 뜻입니다.

한마디로, 판돈도 전망도 크지만 — 그 미래를 실제로 여는 열쇠는 여전히 시험관이 쥐고 있습니다.

---

## [챕터 6] 결론·미래방향 (Challenges and Future Directions / Conclusion)

**내레이터:** 여러분, 성과의 무대를 다 밟았으니 이제 논문이 가장 정직해지는 대목, 남은 숙제 앞에 설 차례입니다.

저자들이 맨 먼저 인정하는 건 이겁니다. AI는 정적인 구조, 그러니까 한 장의 정지 사진은 놀랍도록 잘 맞힙니다. 그런데 단백질은 살아서 꿈틀대죠. 시간에 따라 모양이 바뀌는 동역학, 한쪽을 건드리면 먼 곳이 반응하는 알로스테릭, 원자부터 복합체까지 여러 스케일을 아우르는 통합 — 이건 여전히 미해결입니다. 여기서 의문이 하나 생기죠. 구조를 그렇게 잘 맞히는데 왜 기능은 못 맞힐까요? 기능을 좌우하는 결합친화도, 촉매활성, 안정성 — 이런 값들은 정지 사진 한 장이 아니라 그 움직임에서 나오기 때문입니다. 게다가 막단백질이나 본질적 무질서 단백질은 애초에 고품질 데이터 자체가 부족하고, 모델이 왜 그렇게 판단했는지 들여다보는 해석가능성도 여전히 벽입니다.

그리고 가장 아픈 대목, '환각'입니다. 이 말, 재미있게도 원래 베이커 연구실의 정식 설계 기법 이름이에요. 구조예측망을 거꾸로 돌려, 무작위 서열을 신경망이 '이상적'이라 여기도록 최적화해서 새 단백질을 '꿈꾸게' 만드는 방식이죠. 그런데 이 꿈에는 그늘이 있습니다. 컴퓨터 안, 인 실리코에서는 그럴듯한데, 막상 시험관에서 발현시키면 접히지 않거나 뭉쳐 응집해 버리는 겁니다.

숫자로 보면 더 냉정해요. 그 환각 원논문에서 설계한 129개 중, 제대로 접힌 건 27개. 약 21퍼센트입니다. 바로 여기서 '신규 기능성 단백질 실험 성공률 20퍼센트 미만'이라는, 이 리뷰를 관통하는 숫자가 나옵니다. 다섯 개를 꿈꾸면 하나가 될까 말까라는 얘기예요. 효소는 더합니다. 데 노보로 설계한 효소는 자연 효소 수준의 촉매 회전율, kcat에 도달하려면 결국 실험실에서 유도 진화를 한 번 더 태워야 합니다. 컴퓨터가 밑그림은 그려주지만, 마지막 성능은 옛 방식이 마저 채우는 거죠.

그래서 이게 왜 의미 있냐면요. 이 20퍼센트라는 숫자가, 오프닝부터 우리를 따라온 그 갭의 정체입니다. AI는 천문학적 공간에서 그럴듯한 후보를 놀랍도록 빠르게 꿈꿔냅니다. 하지만 그 꿈의 다섯 중 넷은 시험관 문턱에서 무너져요. 그리고 저자들이 내놓는 처방은 '더 큰 모델'이 아닙니다. AI를 자율 설계자가 아니라 효율적인 '가설 생성기'로 앉히고, 그 가설을 실험과 손잡은 폐루프로 거르는 것 — 바로 그 하이브리드가, 다음 이야기의 문을 엽니다.

**내레이터:** 자, 그렇다면 그 폐루프는 실제로 어떻게 생겼을까요? 논문은 두 개의 이름으로 답합니다. 하나는 AlphaDesign. 여기 영리한 발상이 있어요. AlphaFold를 그저 완성된 예측기로 옆에 두는 게 아니라, 설계 회로 안에 '미분가능한 모듈'로 통째로 끼워 넣습니다. 미분가능하다는 게 뭐냐면, 서열을 살짝 바꿨을 때 예측 구조가 어느 쪽으로 얼마나 움직이는지, 그 기울기를 따라갈 수 있다는 뜻이에요. 그러니 원하는 구조가 나올 때까지 서열을 자동으로 밀고 당기며 다듬을 수 있죠. 다른 하나는 SAGE-Prot. 이건 설계를 고처리량 스크리닝과 묶습니다. 컴퓨터가 후보를 쏟아내면, 대량 실험이 곧바로 그걸 걸러 다시 설계로 되먹이는 거죠.

여기서 논문의 워크플로우 그림을 말로 펼쳐 보겠습니다. 이 그림은 하나의 순환 파이프라인이에요. 왼쪽 출발점은 표적 서열과 그 친척들을 모은 다중서열정렬. 거기서 AI 추론 단계로 넘어가는데, 갈래가 둘입니다. 판별 모델은 구조 좌표를 예측하고, 생성 모델은 새 백본을 합성하죠. 그다음이 핵심인 'in silico 정제' 칸입니다. 물리 기반 에너지로 채점하고 분자동역학으로 열역학적 안정성을 따져, 그럴듯한 것만 남겨요. 그리고 마지막, 오른쪽 끝의 '습식 검증'. 바로 여기가 시험관이 판정을 내리는 자리입니다.

그 판정은 세 개의 도구로 이뤄집니다. 첫째, CD, 원편광이색성. 단백질이 2차 구조를, 그러니까 알파 나선이나 베타 병풍을 제대로 갖췄는지 봅니다. 둘째, SEC, 크기배제크로마토그래피. 이 단백질이 얌전한 단량체로 있는지, 아니면 뭉쳐 응집했는지를 가려내죠 — 앞서 말한 환각의 그 응집을 잡아내는 관문입니다. 셋째, X선 결정학과 cryo-EM, 저온전자현미경. 3차 구조, 최종 3차원 모양을 원자 수준에서 확인합니다.

그래서 이게 왜 의미 있냐면요. 이 그림 전체가 화살표 하나로 끝나지 않고 다시 처음으로 돌아온다는 것 — 검증 결과가 다음 설계의 입력이 되는 겁니다. AI는 자율 설계자가 아니라, 이 고리를 빠르게 돌리는 효율적인 가설 생성기예요. 그리고 미래는 여기에 능동 학습과 자동화 실험 플랫폼을 붙여, 사람이 일일이 손대지 않아도 설계와 실험이 스스로 되먹임하는 고리로 나아갑니다. 컴퓨터의 꿈과 시험관의 현실, 그 둘을 잇는 다리가 바로 이 폐루프인 거죠.

**내레이터:** 자, 그렇다면 이 폐루프는 무엇을 향해 나아가고 있을까요? 방향은 분명합니다. 지금까지 우리가 만난 도구들은 대개 단백질 사슬 하나, 그것만 다뤘죠. 그런데 실제 세포 안에서 단백질은 혼자 일하지 않습니다. DNA와 RNA를 붙들고, 저분자 약물이나 금속을 품고, 몸에서는 당사슬 같은 번역후수식이 덕지덕지 붙죠. 그래서 다음 도약은 단일 사슬 예측에서 '멀티모달 생체분자 모델링'으로 넘어갑니다.

두 이름이 이 문을 엽니다. 하나는 AlphaFold 3. 이전 버전이 아미노산마다 좌표틀을 씌워 접었다면, 이번엔 그 틀을 버리고 확산으로 원자 좌표를 직접 빚어냅니다. 그 덕에 단백질뿐 아니라 핵산, 저분자 리간드, 금속, 번역후수식까지 PDB에 등재된 분자종의 99퍼센트 이상을 한 그릇에서 다뤄요. 다른 하나는 베이커 연구실의 RoseTTAFold All-Atom. 잔기 단위와 원자 단위 표현을 결합해, 공유결합으로 변형된 자리의 46퍼센트를 오차 2.5 옹스트롬 이내로 맞혔습니다. 여기에 파인튜닝한 RFdiffusionAA로 heme, 그러니까 헴 같은 저분자를 감싸 쥐는 단백질을 설계하고 실험으로 확인까지 했죠. 단백질과 그 파트너를 '함께' 설계하는 시대가 열린 겁니다.

그런데 말이죠, 여기서 정직하게 짚어야 할 그늘이 있습니다. 이 강력한 모델들은 '자신 있게 틀리기'를 합니다. 매듭이나 위상 장벽을 무시하고, 반복 서열엔 있지도 않은 β-솔레노이드를 높은 신뢰도로 그려내죠. 그래서 규제기관이 나섭니다. FDA는 2025년 1월, 첫 AI 전용 초안 지침을 냈어요. 핵심 요구가 뭘까요? AI가 내린 결정의 타당성과 재현성을 증명하라는 겁니다. 표준 계산 벤치마크, 그리고 습식 검증 기준 — 이게 없으면 아무리 화려한 예측도 규제의 문턱을 넘지 못합니다.

그래서 저자들의 최종 판정은 무엇일까요? 놀랍도록 겸손합니다. 우리는 이 변혁적 접근의 잠재력을 이제 막 실현하기 시작한 '초기 단계'에 있다는 것. 관건은 더 큰 모델도, 더 화려한 데모도 아닙니다 — 계산과 실험, 두 진영의 과학자가 손을 맞잡는 협업입니다.

그래서 이게 왜 의미 있냐면요. 우리는 안핀슨의 도그마에서 출발했습니다. 서열이 구조를 결정한다는 60여 년 전의 통찰. AI는 그 원리를 뒤엎지 않고, 패턴 학습으로 우회해 답하기 시작했죠. 이제 단백질 하나를 넘어 그 파트너들까지 함께 꿈꾸는 데까지 왔습니다. 하지만 컴퓨터의 꿈과 시험관의 현실 사이 그 갭 — 성공률 20퍼센트 미만 — 은 여전히 남아 있어요. AI는 가설을 놀랍도록 빠르게 만들어냅니다. 그러나 그 가설이 진짜 약이, 진짜 효소가 되는지는 — 여전히 시험관이 판정합니다.

---

## 마무리

**내레이터:** 여러분, 긴 여정이었습니다. 우리는 초록에서 AI가 마침내 단백질의 서열-구조-기능을 해독하기 시작했다는 약속을 들었고, 서론에서 안핀슨의 도그마와 Rosetta라는 뿌리를, 그리고 10억 달러짜리 판돈이 걸린 시장을 지났죠. 방법에서는 딥러닝·확산·언어 모델·지식 그래프라는 네 기둥을 열어봤고, 도구에서 AlphaFold2부터 ProteinMPNN까지 스타 플레이어를 만났습니다. 응용에서는 감미 단백질 sweelin과 세탁 효소를 맛보았고, 마지막 결론에서 그 모든 성과 뒤에 버틴 정직한 숫자, 성공률 20퍼센트 미만 앞에 섰습니다.

이 논문의 한 줄 기여는 이겁니다. AI 단백질 설계의 흩어진 기술·도구·응용을 한 지도에 정리하되, 축포가 아니라 '예측과 검증 사이의 갭'을 중심에 놓고, 그 갭을 메우는 길이 더 큰 모델이 아니라 실험과 손잡은 하이브리드 폐루프임을 못 박은 것.

물론 다르게 볼 여지도 있습니다. '20퍼센트 미만'이라는 숫자는 이 리뷰가 단일 원출처를 명시하기보다 분야의 통설로 서술한 것에 가깝고, 실제 성공률은 미니바인더냐 항체냐 효소냐, 어떤 도구를 쓰느냐에 따라 크게 갈립니다. 그러니 이 숫자는 절망의 근거가 아니라, 앞으로 얼마나 개선될 수 있는지를 재는 눈금으로 읽는 게 맞겠죠.

그래서 아직 열린 질문은 무엇일까요? 정적인 한 장의 사진을 넘어 단백질의 '움직임' — 동역학과 알로스테릭을 어떻게 설계에 담을 것인가. 결합친화도와 촉매활성을 시험관 전에 얼마나 믿을 만하게 예측할 것인가. 그리고 사람 손을 줄인 자동화 폐루프가, 정말로 성공률을 수십 퍼센트대로 끌어올릴 것인가. 여기에 규제와 임상이라는, AI가 아직 풀지 못한 마지막 관문이 남아 있죠.

큰 그림에서 이 논문은 어떤 벽돌일까요? 그 자체로 새 데이터를 내놓는 실험 벽돌은 아닙니다. 오히려 60여 년에 걸친 벽 — 안핀슨과 레빈탈에서 베이커와 AlphaFold까지 쌓인 벽돌들이 지금 어디쯤 서 있는지를 비춰주는, 균형 잡힌 '이정표' 벽돌입니다. 흥분과 냉정 사이에서 좌표를 찍어주는.

안핀슨의 오래된 통찰 — 서열이 구조를 결정한다 — 에서 시작한 이야기가, AI의 패턴 학습을 지나, 다시 시험관의 판정으로 돌아왔습니다. 컴퓨터는 놀랍도록 빠르게 꿈을 꿉니다. 그러나 그 꿈이 진짜가 되는지는, 여전히 시험관이 답합니다. 오늘 이 긴 이야기를 끝까지 함께해 주셔서 고맙습니다. 다음 이야기에서 다시 뵙겠습니다.

---

### 부록: 논문 구조와 다룬 포인트

**1. 초록** — 리뷰 전체의 주장을 한 문단으로 압축 — AI가 서열·구조·기능 관계를 해독해 단백질 공학을 바꿨고, 성공만큼 한계도 뚜렷하다
   - AI가 바꾼 단백질 공학의 얼개 ★
**2. 서론 (The AI-Driven Protein Engineering Landscape)** — 왜 이 문제가 중요하고 어려웠는지, 그리고 왜 AI가 전환점이 되었는지 동기 부여
   - 시장과 문제 정의: 조작 단백질 vs de novo 설계 ★ _(Figure 1)_
   - 전통적 방법의 한계와 Anfinsen 도그마·Rosetta ★
   - 산업 지형: 10억 달러 규모 AI-제약 파트너십 ★ _(Table 1)_
**3. 방법·기술 (Key AI Technologies in Protein Design)** — AI 단백질 설계를 떠받치는 4개 기술 기둥과 판별/생성 모델의 구분을 해부
   - 판별 모델 vs 생성 모델, 그리고 데이터 편향 ★
   - 딥러닝 아키텍처: CNN·GNN·SE(3) 등변성 ★ _(Figure 2)_
   - 확산 기반 생성 모델: RFdiffusion·Chroma·EvoDiff ★ _(Table 2)_
   - 단백질 언어 모델·지식 그래프·분자동역학 _(Figure 3)_
**4. 도구 (AI-Driven Protein Design Tools)** — 구조 예측에서 설계로의 전환을 대표 도구들의 벤치마크 수치로 구체화
   - AlphaFold2: 구조 예측의 도약과 한계 ★ _(Table 3)_
   - RoseTTAFold와 ESM-2 ★ _(Table 3)_
   - 전문 도구 생태계: ProteinMPNN 외 _(Table 4)_
**5. 결과·논의 (Applications and Impact)** — 치료제·식품·산업 세 영역의 구체적 성공 사례와 시장·상업 임팩트
   - 치료 단백질: 항체 나노케이지와 백신 ★ _(Table 1)_
   - 식품 단백질: 감미 단백질 sweelin ★
   - 산업 응용: 생촉매와 기업 사례 ★
   - 미래 시장과 구현 난관
**6. 결론·미래방향 (Challenges and Future Directions / Conclusion)** — 기술적 한계를 정직하게 나열하고, 하이브리드·실험 통합·멀티모달·규제라는 다음 단계를 제시
   - 핵심 기술 난관: 동역학·해석가능성·검증 갭 ★
   - 하이브리드 패러다임과 실험 통합 ★ _(Figure 2)_
   - 멀티모달 모델링과 규제·결론 ★

### 부록: 다룬 그림/표

- **Figure 1** — AI 주도 단백질 설계의 전체 조감도 다이어그램. 좌상단에 핵심 기술(딥러닝 — CNN/GNN/Attention, 언어 모델, 지식 그래프, 분자동역학), 중앙에 컬러 3D 단백질 구조 일러스트, 우상단에 핵심 도구(AlphaFold, RoseTTAFold). 좌하단에 3대 응용 영역(치료제·산업·환경)과 사용 사례, 우하단에 시장 임팩트. → 이 리뷰가 다루는 전 범위를 한 장으로 조직 — 4개 기술 기둥이 도구를 낳고, 도구가 치료·산업·환경 응용으로 이어지며 시장 임팩트를 만든다는 논문 전체의 지도.
- **Table 1** — 최근 주요 AI-제약 파트너십 개요. 열: 발표일, AI 회사, 제약 파트너, 치료 초점, 최대 잠재 가치(USD), AI 응용, 핵심 기술 난관. 행: Isomorphic Labs–Eli Lilly, –Novartis, Generate Biomedicines–Amgen, Absci–Merck, BioMap–Sanofi. → Isomorphic–Lilly $1.7B, –Novartis $1.2B, Generate–Amgen $1.9B(Chroma), Absci–Merck $610M(항체), BioMap–Sanofi $1B. 마일스톤이 10억 달러를 넘고 생성적 접근으로 이동 중이나, 디지털 설계를 안전·제조 가능한 약으로 번역하는 것이 공통 난관.
- **Figure 2** — AI 단백질 설계의 방법론적 워크플로우 파이프라인. 표적 서열+MSA 수집 → AI 추론 단계(판별 모델은 구조 좌표 예측, 생성 모델은 신규 백본 합성) → in silico 정제(물리 기반 에너지 채점·분자동역학으로 열역학 안정성 평가) → 습식 검증(발현·생물물리 분석 예: SEC, 구조 해석 예: X선/cryo-EM). 패널 A는 팽창 CNN, B는 GNN 메시지 패싱, C는 위치 특이 어텐션 가중치. → 설계는 서열에서 시작해 AI 추론·물리 채점·습식 검증으로 이어지는 폐루프. CNN은 dilation 1/2/4/8 다중 스케일, GNN은 다중 메시지 패싱, 어텐션은 서열+구조 맥락을 함께 반영해 원거리 잔기 관계를 학습.
- **Figure 3** — 자연어 모델과 단백질 언어 모델의 개념적 평행 비교. (A) 제어 태그(예: 'Politics', 'Sports')로 도메인 특화 문장을 생성하는 영어 언어 모델. (B) 단백질 패밀리 태그(예: 'Immunoglobulin', 'Phage Lysozyme')로 아미노산 서열을 생성하는 단백질 언어 모델. → 거대언어모델이 프롬프트로 맥락에 맞는 텍스트를 만들듯, 단백질 언어 모델은 패밀리 명세로 생화학적으로 유효한 아미노산 서열을 생성 — 서열 속 패턴이 NLP와 같은 틀로 포착·생성될 수 있음을 시사.
- **Table 2** — 핵심 딥러닝 아키텍처 비교. 열: 모델 아키텍처, 대표 도구, 조건화 메커니즘, 주 응용, 강점, 한계. 행: GNN(ProteinMPNN), 언어 모델(ESM-2/ProGen2), 확산 모델(RFdiffusion). → GNN은 고정 3D 백본으로 서열 설계 — 새 폴드 생성 불가. 언어 모델은 방대한 서열로 진화 패턴 학습 — 3D 제어 간접적, 접힘 미보장. 확산 모델은 자연에 없는 새 폴드를 정밀 조건화 생성 — 계산 집약적, 생물학적 기능 보장은 과제. 판별→생성 전환을 요약.
- **Table 3** — 상업용 AI 플랫폼 비교. 열: 플랫폼, 핵심 기술, 상업 응용, 벤치마크 성능, 핵심 한계. 행: AlphaFold2, RoseTTAFold, ESM-2. → AlphaFold2 — CASP14 도메인 중앙값 백본 RMSD 0.96 Å, 정적 예측만. RoseTTAFold — 단량체 TM > 0.8, 3-트랙, 계산 비용 큼·단일 사슬 한정. ESM-2 — 2차 구조 정확도 > 85%, 접촉 정밀도 > 70%, 생성 서열은 광범위 실험 스크리닝 필요.
- **Table 4** — 추가 AI 단백질 설계 도구 개요. 열: 도구, 개발자, 핵심 기술, 주요 특징, 주 응용. 행: ProteinMPNN, OmegaFold, ProGen2, EvoBind, ColabFold, ESM-IF1, trRosetta, ProtGPT2. → ProteinMPNN 서열 회복률 약 52%(Rosetta보다 약 20% 우수), <1초/단백질. OmegaFold는 MSA 없이 고아 단백질 TM>0.7. ProGen2는 10억+ 서열 학습, 최대 400 아미노산 zero-shot 생성. 코어 플랫폼을 보완하는 전문 도구 생태계.

### 부록: 배경 조사 참고 자료

- [AlphaFold: a solution to a 50-year-old grand challenge in biology (Google DeepMind)](https://deepmind.google/blog/alphafold-a-solution-to-a-50-year-old-grand-challenge-in-biology/)
- [Highly accurate protein structure prediction with AlphaFold (Nature, Jumper et al. 2021)](https://www.nature.com/articles/s41586-021-03819-2)
- [High-accuracy protein structure prediction in CASP14 (Proteins, 2021)](https://onlinelibrary.wiley.com/doi/10.1002/prot.26171)
- [Confidence Metrics (pLDDT, pTM) — google-deepmind/alphafold DeepWiki](https://deepwiki.com/google-deepmind/alphafold/6.1-confidence-metrics)
- [CASP14: what DeepMind's AlphaFold 2 really achieved (Oxford Protein Informatics Group / BLOPIG)](https://www.blopig.com/blog/2020/12/casp14-what-google-deepminds-alphafold-2-really-achieved-and-what-it-means-for-protein-folding-biology-and-bioinformatics/)
- [Critical Assessment of Methods of Protein Structure Prediction (CASP) – Round XIV (PMC)](https://pmc.ncbi.nlm.nih.gov/articles/PMC8726744/)
- [Robust deep learning-based protein sequence design using ProteinMPNN (Science 2022)](https://www.science.org/doi/10.1126/science.add2187)
- [Robust deep learning-based protein sequence design using ProteinMPNN - PubMed](https://pubmed.ncbi.nlm.nih.gov/36108050/)
- [De novo design of protein structure and function with RFdiffusion (Nature 2023)](https://www.nature.com/articles/s41586-023-06415-8)
- [Generative AI for Protein Design: How RFdiffusion, ProteinMPNN, and Diffusion Models Are Engineering New Proteins](https://www.technologynetworks.com/informatics/articles/generative-ai-for-protein-design-how-rfdiffusion-proteinmpnn-and-diffusion-models-are-engineering-414657)
- [Improving de novo protein binder design with deep learning (Nat Commun 2023)](https://www.nature.com/articles/s41467-023-38328-5)
- [Anfinsen's dogma - Wikipedia](https://en.wikipedia.org/wiki/Anfinsen%27s_dogma)
- [Levinthal's paradox - Wikipedia](https://en.wikipedia.org/wiki/Levinthal%27s_paradox)
- [Design of a novel globular protein fold with atomic-level accuracy (Top7, Kuhlman & Baker, Science 2003) - PubMed](https://pubmed.ncbi.nlm.nih.gov/14631033/)
- [Design by Directed Evolution - Frances H. Arnold (Acc. Chem. Res. 1998)](https://cheme.caltech.edu/groups/fha/publications/Arnold_ACR_1998.pdf)
- [Machine learning-assisted directed protein evolution with combinatorial libraries (PNAS)](https://www.pnas.org/doi/10.1073/pnas.1901979116)
- [What has de novo protein design taught us about protein folding and biophysics? - Baker (Protein Science 2019)](https://onlinelibrary.wiley.com/doi/full/10.1002/pro.3588)
- [Improving de novo protein binder design with deep learning (Nature Communications 2023)](https://www.nature.com/articles/s41467-023-38328-5)
- [The Rosetta All-Atom Energy Function for Macromolecular Modeling and Design (Alford et al. 2017)](https://www.researchgate.net/publication/316347718_The_Rosetta_All-Atom_Energy_Function_for_Macromolecular_Modeling_and_Design)
- [Evolutionary-scale prediction of atomic-level protein structure with a language model (ESM-2/ESMFold, Lin et al., Science 2023)](https://www.science.org/doi/10.1126/science.ade2574)
- [ProtGPT2 is a deep unsupervised language model for protein design (Nature Communications 2022)](https://www.nature.com/articles/s41467-022-32007-7)
- [ProGen2: Scalable Protein Language Models (overview)](https://www.emergentmind.com/topics/progen2)
- [Origins of coevolution between residues distant in protein 3D structures (PNAS)](https://www.pnas.org/doi/10.1073/pnas.1702664114)
- [Evaluation of residue-residue contact prediction methods (EVfold/PSICOV/GREMLIN, coevolution from MSA)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC8177648/)
- [Structure Without Alignment: How ESM-2 Folds a Single Sequence](https://rewire.it/blog/structure-without-alignment/)
- [BERTology Meets Biology: Interpreting Attention in Protein Language Models](https://www.biorxiv.org/content/10.1101/2020.06.26.174417.full.pdf)
- [facebookresearch/esm: Pretrained language models for proteins](https://github.com/facebookresearch/esm)
- [SE(3) diffusion model with application to protein backbone generation (Yim et al., ICML 2023, FrameDiff)](https://proceedings.mlr.press/v202/yim23a/yim23a.pdf)
- [Invariant Point Attention Explained (Medium)](https://medium.com/@kasothaphie/invariant-point-attention-explained-c71aa56f5f5c)
- [AlphaFold 2 is here: what's behind the structure prediction miracle (Oxford Protein Informatics Group)](https://www.blopig.com/blog/2021/07/alphafold-2-is-here-whats-behind-the-structure-prediction-miracle/)
- [RFdiffusion: Diffusion Models in Protein Design (EmergentMind)](https://www.emergentmind.com/topics/rfdiffusion-df050695-8d1e-4f95-a59e-6db235713fec)
- [Do we need equivariant models for molecule generation? (arXiv 2507.09753)](https://arxiv.org/abs/2507.09753)
- [From Geometry to Biology: How SE(3) and Deep Learning Are Advancing Protein Engineering (Medium)](https://medium.com/@pavan_allu/from-geometry-to-biology-how-se-3-and-deep-learning-are-advancing-protein-engineering-8f42e560ec69)
- [Protein Design Enters the Artificial Intelligence Era: Foundations, Tools, and Emerging Paradigms (CSBJ, 2026) — 리뷰 원문](https://spj.science.org/doi/10.34133/csbj.0105)
- [De novo protein design by deep network hallucination (Anishchenko et al., Baker lab) — '환각' 기법 원논문, 129개 중 27개(~21%) 폴딩](https://pmc.ncbi.nlm.nih.gov/articles/PMC9293396/)
- [AI-Designed Binder Failure Modes: The Gap Between Theory and Practice (Ranomics) — '90% bind'가 오해를 부르는 이유와 5대 실패 모드](https://www.ranomics.com/de-novo-protein-design-failure-modes)
- [RFdiffusion Exhibits Low Success Rate in De Novo Design of Functional Protein Binders (bioRxiv 2025) — 독립 재현 저조 성공률](https://www.biorxiv.org/content/10.1101/2025.02.07.636769)
- [BindCraft AI Model Achieves One-Shot Functional Protein Design (GEN) — 종전 <1% 대비 10~100% 성공률, 11개 중 6개 검증](https://www.genengnews.com/insights/bindcraft-ai-model-achieves-one-shot-functional-protein-design/)
- [Accurate structure prediction of biomolecular interactions with AlphaFold 3 (Nature 2024)](https://www.nature.com/articles/s41586-024-07487-w)
- [Generalized biomolecular modeling and design with RoseTTAFold All-Atom (Science 2024)](https://www.science.org/doi/10.1126/science.adl2528)
- [AI protein-prediction tool AlphaFold3 is now more open (Nature news)](https://www.nature.com/articles/d41586-024-03708-4)
- [AlphaFold 3 Angst: Limited Accessibility Stirs Outcry from Researchers (GEN)](https://www.genengnews.com/topics/artificial-intelligence/alphafold-3-angst-limited-accessibility-stirs-outcry-from-researchers/)
- [AlphaFold 2, but not AlphaFold 3, predicts confident but unrealistic β-solenoid structures for repeat proteins (PMC)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11795689/)
- [FDA Draft Guidance on AI in Drug Development Explained (IntuitionLabs)](https://intuitionlabs.ai/articles/fda-draft-guidance-ai-drug-development)
- [What will be the first AI-designed drug? These disease-fighting antibodies are top contenders (Nature 2025)](https://www.nature.com/articles/d41586-025-03965-x)
- [AI-Designed Antibodies in Clinical Trials 2025 (AntibodyLLM)](https://www.antibodyllm.com/blogs/ai-designed-antibodies-clinical-trials-2025.html)
- [DeepMind's Isomorphic Inks $3B Worth of Deals with Lilly and Novartis in One Day - Inside Precision Medicine](https://www.insideprecisionmedicine.com/topics/precision-medicine/deepminds-isomorphic-inks-3b-worth-of-deals-with-lilly-and-novartis-in-one-day/)
- [Alphabet's Isomorphic stacks two new deals with Lilly, Novartis worth nearly $3B ahead of JPM - Fierce Biotech](https://www.fiercebiotech.com/biotech/alphabets-isomorphic-stacks-two-new-deals-lilly-novartis-worth-nearly-3b-ahead-buzzy-jpm)
- [Novartis inks $1B-plus biobucks deal with Flagship's Generate - Fierce Biotech](https://www.fiercebiotech.com/biotech/novartis-inks-1b-biobucks-deal-flagships-generate-biomedicines)
- [Generate:Biomedicines Announces Multi-Target Collaboration with Novartis](https://generatebiomedicines.com/media-center/generatebiomedicines-announces-multi-target-collaboration-with-novartis)
- [AstraZeneca inks $247M AI-enabled oncology antibody design pact - Fierce Biotech](https://www.fiercebiotech.com/biotech/astrazeneca-inks-247m-ai-enabled-oncology-antibody-design-pact-joining-abscis-list-pharma)
- [Sanofi pays $10M upfront in hope 'biological map of proteins' leads to drug discovery treasure - Fierce Biotech](https://www.fiercebiotech.com/biotech/sanofi-pays-10m-hope-biological-map-or-proteins-leads-drug-discovery-treasure)
- [AI in Drug Discovery: predictions for 2026 - Drug Target Review](https://www.drugtargetreview.com/ai-in-drug-discovery-predictions-for-2026/1865962.article)
- [AI in Drug Discovery: Clinical Failures, Regulatory Reality, and the Validation Crisis Behind the Hype - Pharmaceuticals (MDPI)](https://doi.org/10.3390/ph19060916)
- [Learning from 'Failures and Withdrawals' in AI Drug Discovery: BenevolentAI, Exscientia - Pharma Insight Lab](https://note.com/pharma_insight/n/n7286d0419e9f?hl=en)

### 구성 노트

이 에피소드는 논문의 실제 구조(초록→서론→방법→결과·논의→결론)를 그대로 따라가며 서술하는 '단독 내레이터 강의형'입니다. 개념 해부는 *Ten Simple Rules for Reading a Scientific Paper* (PMC7392212)의 프레임을 참고했습니다.
