**한국어** | [English](README.en.md)

# Jinyoung Jang — Product Portfolio

> 고객의 문제를 제품으로 연결하는 Product Manager · Product Builder입니다.

사업과 고객 현장에서 오래 일한 뒤 개발을 시작했습니다.

iOS에서 출발해 직접 제품을 만들며 Web, Backend, Cloud, ML까지 개발 과정 전반을 경험했습니다. 문제를 정의하고 필요한 사람과 기술을 연결해 실제로 작동하는 제품까지 만드는 역할에 강점이 있습니다.

---

## Selected Products

### 01. Rangeon
**가상자산 시장 데이터 기반 Forecast Analytics SaaS**

Rangeon은 클라이언트 요청으로 BotBlue와 BotBlue Orbit을 개발하며 가상자산 선물시장과 장기간의 시장 데이터를 다루면서 시작한 프로젝트입니다.

최대 약 8년 규모의 분봉 데이터를 다루는 과정에서 많은 시장 데이터가 존재하지만, 실제 투자자가 자신의 포지션을 통계적으로 이해할 수 있도록 돕는 시각화 서비스는 부족하다고 느꼈습니다.

### 문제 정의

단순한 과거 통계 범위만으로는 충분하지 않았습니다.

과거 데이터를 기준으로 계산한 범위는 지나치게 넓어 실제 활용성이 낮았고, 다양한 시장 지표와 파생 컬럼을 구성해 반복적으로 실험하며 의미 있는 정보와 그렇지 않은 정보를 구분했습니다.

이후 Machine Learning 모델을 적용하여 넓은 통계적 범위보다 오차를 줄인 Forecast Range와 Movement를 제공할 수 있는지 지속적으로 평가하고 제품화했습니다.

### 제품 원칙

Rangeon은 사용자의 투자 방향을 결정해주는 서비스가 아닙니다.

**Buy / Sell 또는 Long / Short 신호를 제공하지 않고**, 사용자가 스스로 판단할 수 있도록 시장의 통계적 맥락을 시각화하는 것을 핵심 가치로 두고 있습니다.

사용자는 다음 정보를 확인할 수 있습니다.

- 예상 가격 범위 (Forecast Range)
- 예상 변동폭 (Movement)
- 현재 가격의 통계적 위치
- 예상 변동 중 실제 발생한 정도
- Forecast Quality
- 과거 예측 결과와 품질 지표

모델의 예측값만 보여주는 것이 아니라 **예측 품질을 지속적으로 평가하고 사용자에게 공개**하도록 설계했습니다.

### 담당 범위

- 제품 기획 및 UX 설계
- 시장 데이터 수집 및 처리 구조
- Feature / Market Indicator 실험
- Forecast Range / Movement 모델 개발 과정
- Forecast Quality 평가 구조
- Frontend 및 Responsive Web
- Backend API
- Realtime WebSocket 통신
- Firebase Authentication
- Subscription / Entitlement 구조
- GCP / Cloud Run / VM Infrastructure
- 배포 및 운영 검증
- QA / Recovery Flow

### 해결한 문제

**1. 의미 있는 Forecast Range 만들기**

단순 과거 통계는 범위가 너무 넓어 활용하기 어려웠습니다.

다양한 Feature와 시장 지표 조합을 반복적으로 실험하고 ML 모델을 적용하면서, 기존 통계 범위보다 실제 활용 가능한 예측 범위를 만들기 위한 평가를 지속했습니다.

**2. 시장 데이터와 인프라 제약**

분봉 데이터 처리, 거래소 API Rate Limit, 실시간 호출량, 병렬 처리와 하나의 VM에서 처리해야 하는 Computing Resource 등을 고려해 데이터 수집과 Inference 흐름을 구성했습니다.

**3. 기술 제품을 실제 서비스로 출시하기**

처음에는 통계 시각화 도구로 시작했지만 실제 상용화를 준비하면서 금융·가상자산 관련 서비스 분류, 투자자문과 Analytics의 경계, 결제 사업자의 SaaS 심사와 구독 구조 등 코드 외적인 문제까지 직접 검토하고 대응했습니다.

### 현재 상태

- Production 배포 완료
- 결제 서비스 승인 후 상용 서비스 오픈 예정

> 상용 서비스를 준비 중인 프로젝트이므로 Source Code는 Private으로 유지하고 있습니다.

---

### 02. Kivvo
**기억 상태를 관리하는 Adaptive Learning Platform**

Kivvo는 학습한 내용을 잊는 것을 실패가 아닌 자연스러운 과정으로 보고, 사용자가 필요한 시점에 단어를 다시 떠올릴 수 있도록 **기억을 관리하는 것(Memory Management)**을 목표로 하는 학습 서비스입니다.

사용자는 짧은 Play 세션에서 학습 내용을 떠올리고, 바로 기억나지 않을 때는 Hold를 통해 힌트를 점진적으로 확인할 수 있습니다.

시스템은 반응 속도, Hold 시간, 힌트 사용 여부와 반복되는 정답·오답을 함께 보고 각 항목의 Memory Status와 Memory Strength를 관리하여 다음 복습 시점을 조절합니다.

기억이 안정적인 단어는 점차 적게 노출하고, 기억이 약해진 단어는 다시 자주 노출합니다.

### 주요 제품 개념

- Memory Status
  - `new`
  - `at-risk`
  - `fragile`
  - `mastered`
- Memory Strength
- Adaptive Review Interval
- Forgetting-based Memory Decay
- 사용자별 Learning Rhythm
- CSV Vocabulary Import / Export
- Personal Dashboard
- Group / Admin Dashboard

### 현재 상태

- Product / UX Design 완료
- Frontend 마무리 단계
- Data Model 설계 완료
- Backend / Algorithm 개발 예정

> 개발 중인 제품이므로 Source Code는 Private으로 유지하고 있습니다.

---

### 03. Momento

**하루의 기록을 실물 다이어리까지 연결하는 Mobile Product**

하루에 하나의 글이나 사진을 남기고, 연인·친구·가족이 같은 공간에서 각자의 하루를 기록할 수 있는 모바일 서비스입니다.

기록이 충분히 쌓이면 앱 안에서 실물 다이어리 제작을 주문할 수 있도록 설계해, 디지털 기록이 실제로 손에 남는 경험까지 제품으로 연결했습니다.

현재 App Store에서 운영 중이며 약 **120명의 사용자**가 이용하고 있습니다.

---

## Earlier Mobile Projects

### Gzee
**AI 기반 영어 학습 및 Grammar Feedback iOS App · 개인 프로젝트**

영어 학습 관리와 AI 기반 문법·오타 피드백을 제공하는 iOS 앱입니다.

### 구현 경험

- Firebase Authentication 기반 로그인 / 회원가입
- Firestore 사용자 및 콘텐츠 저장
- GPT API 연동
- 문법 / 오타 Feedback
- Google Translate API
- 사용자 간 어휘·문장 공유
- 한국 / 일본 / 미국 Localization 및 배포

**Technologies**

`SwiftUI` `Firebase` `GPT API`

---

### WanderBoard
**여행 기록 및 공유 iOS App · 5인 Team Project**

여행 기록과 사진을 다른 사용자와 공유할 수 있도록 개발한 팀 프로젝트입니다.

### 담당 영역

- Firebase Authentication
- Firestore 데이터 저장
- Data Modeling
- UI Animation
- 사진 Metadata를 활용한 MapKit 위치 표시

**Technologies**

`UIKit` `SwiftUI` `Firebase` `MapKit`

---

## How I Build Products

AI는 구현 속도를 크게 높여주지만, 빠르게 만드는 것과 제대로 만드는 것은 다른 문제라고 생각합니다.

`Problem Definition`
→ `Requirement Breakdown`
→ `Design`
→ `Implementation`
→ `Review`
→ `Testing`
→ `Deployment`
→ `Production Validation`

AI를 적극적으로 활용하되, 무엇을 요청할지, 어디까지 믿을지, 무엇을 다시 확인할지는 직접 판단합니다.

변경된 Diff와 Log를 확인하고, Build와 Smoke Test를 거쳐 배포한 뒤 실제 Production 환경에서 동작과 복구까지 검증하는 방식으로 작업하고 있습니다.

---

## Business Background

소프트웨어 개발을 시작하기 전에는 B2B 영업과 사업 운영을 경험했습니다.

### 주요 경험

- 사무용기기 및 전산용품 렌탈 사업
- (주)대우건설 계약
- (주)코스트코코리아 계약
- Lexmark Korea 온라인 총판 계약
- G-Star RAW 국내 독점 판매 계약
- 현대백화점 입점
- 롯데백화점 입점

이 경험을 통해 소프트웨어도 단순히 기능을 구현하는 것으로 끝나는 것이 아니라 **사용자의 문제를 해결하고 실제 사업적 가치를 만들어야 하는 제품**이라는 관점으로 바라보고 있습니다.

---

## Recognition

### 문제해결능력 우수상

**팀스파르타 — 실무형 iOS 앱 개발자 양성과정**

교육과정 수료 중 문제해결능력 우수상을 수상했습니다.

---

## Contact

- LinkedIn: [linkedin.com/in/mgynsz](https://www.linkedin.com/in/mgynsz/)
- GitHub: [github.com/mgynsz](https://github.com/mgynsz)
- Email: [mgynsz@gmail.com](mailto:mgynsz@gmail.com)
