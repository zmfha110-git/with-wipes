# Design

## Source of truth
- Status: Draft
- Last refreshed: 2026-06-29
- Primary product surfaces: [index-v7.1.html](/Users/mgrv/work/with-wipes/index-v7.1.html), 제품 규격 비교 시안, 견적 문의 랜딩
- Evidence reviewed:
  - [index-v7.1.html](/Users/mgrv/work/with-wipes/index-v7.1.html)
  - [PLAN.md](/Users/mgrv/work/with-wipes/PLAN.md)
  - [CONTENT-TODO.md](/Users/mgrv/work/with-wipes/CONTENT-TODO.md)
  - 사용자 제공 레퍼런스 이미지 3장

## Brand
- Personality: 공장 직거래의 담백함, 과장 없는 신뢰, 조용한 자신감
- Trust signals: 직접 생산, 결품 없는 공급, 규격 통제, 세금계산서 발행, 위생용품 신고
- Avoid: 너무 스타트업스러운 장식, 과한 그래디언트 놀이, 근거 없는 프리미엄 톤, 정보 없는 감성 카피

## Product goals
- Goals:
  - "직접 만드는 제조사"라는 차별점을 첫 화면과 스크롤 흐름에서 분명히 전달
  - 제품 종류뿐 아니라 원단·평량·매입까지 상담 전에 감을 잡게 하기
  - 전화 문의 전환을 높이되, 못 받는 상황까지 정직하게 설명하기
- Non-goals:
  - 가격표를 공개해 즉시 비교구매를 유도하는 랜딩
  - 지나치게 화려한 브랜드 쇼케이스
- Success signals:
  - 사용자가 "우리 가게엔 어떤 규격이 맞는지" 감을 잡는다
  - "중간 유통 없음 / 직접 관리"를 기억한다
  - 전화 또는 카톡 문의로 자연스럽게 넘어간다

## Personas and jobs
- Primary personas: 식당·카페·매장 사장, 구매 담당
- User jobs:
  - 우리 업장 용도에 맞는 물티슈 형태를 고르기
  - 너무 얇지 않고 단가도 맞는 규격 감 잡기
  - 공급이 안 끊기는 거래처인지 확인하기
- Key contexts of use: 모바일에서 빠르게 훑기, 통화 전 사전 확인, 가족 운영 제조사에 대한 신뢰 판단

## Information architecture
- Primary navigation: 직접 생산, 후기, 제품, FAQ, 견적문의
- Core routes/screens: 단일 랜딩 페이지
- Content hierarchy:
  - Hero: 직접 제조 + 결품 없는 공급
  - Direct production cinema: 왜 싼가 / 왜 안 끊기나 / 왜 품질이 일정한가 / 왜 믿을 수 있나
  - Social proof
  - Product section
  - Spec explanation block
  - FAQ
  - Inquiry

## Design principles
- Principle 1: 스크롤마다 주장 하나. 한 섹션에서 한 메시지만 강하게 말한다.
- Principle 2: 예쁜 것보다 "믿을 만한 공급자"처럼 보여야 한다.
- Principle 3: 스펙 정보는 숨기지 말고, 상담 전에 판단 재료를 먼저 준다.
- Tradeoffs:
  - 시네마형 직접생산 섹션은 유지하되, 제품/스펙 섹션은 정적 구조로 읽기 쉽게 간다.
  - 실제값이 없으면 임시 통념과 확정값을 구분해 허위처럼 보이지 않게 한다.

## Visual language
- Color: 밝은 쿨그레이 배경 + 흰 카드 + 인디고 포인트 최소 사용
- Typography: Pretendard, 굵기 대비 강하게, 장식 폰트 금지
- Spacing/layout rhythm: 넓은 여백, 큰 라운드 카드, 2단/3단 카드 중심
- Shape/radius/elevation: 큰 radius, 얕은 그림자 또는 거의 없는 입체감
- Motion: 직접생산 섹션만 강한 모션, 나머지는 정적
- Imagery/iconography: 공장/창고/원단/제품 실사진 중심, 아이콘 의존 최소화

## Components
- Existing components to reuse:
  - Hero
  - Trust stats
  - Direct production cinema
  - Product gallery cards
  - Inquiry block
- New/changed components:
  - 원단·평량·매수 정보 보드
  - 원단별 스펙 비교 컴포넌트
  - 비교 시안 토글
- Variants and states:
  - 원단 비교안 A/B/C
  - 실제값 확정 전 경고 상태
- Token/component ownership: repo-local static HTML

## Accessibility
- Target standard: 기본 웹 접근성 준수
- Keyboard/focus behavior: 토글 버튼과 카드 선택은 키보드 포커스 가능
- Contrast/readability: 본문 대비 충분히 확보, 연회색 위 연회색 금지
- Screen-reader semantics: 비교 시안 토글은 버튼+aria-pressed 사용
- Reduced motion and sensory considerations: 큰 애니메이션은 직접생산 섹션에만 제한

## Responsive behavior
- Supported breakpoints/devices: 모바일 우선, 데스크톱 대응
- Layout adaptations:
  - 비교 시안 토글은 모바일에서 1열
  - 3안 카드 구조는 모바일에서 세로 스택
- Touch/hover differences: hover 없이도 정보가 다 보여야 함

## Interaction states
- Loading: 없음
- Empty: 실사진 미확보 시 placeholder
- Error: 실제값 미확정 시 경고 플래그
- Success: 비교안 선택 후 구현 단계로 이동
- Disabled: 확정값 없는 평량 구간은 활성화하지 않음

## Content voice
- Tone: 사장님 대상, 짧고 단정하게
- Terminology: 원단, 평량, 매입, 개별포장, 캡형, 대용량 리필
- Microcopy rules: 성능 과장 금지, 실제 확인 필요 항목은 표시

## Implementation constraints
- Framework/styling system: 단일 HTML + CSS + 약한 JS
- Design-token constraints: 기존 `v7.1` 토큰 최대한 재사용
- Performance constraints: 이미지 없이도 구조가 읽혀야 함
- Compatibility constraints: 최신 브라우저 기준
- Test/screenshot expectations: 로컬 브라우저에서 A/B/C 안 비교 가능해야 함

## Open questions
- [ ] 원단 텍스처 실사진 또는 샘플 이미지 제공 여부
