---
name: toss-tech-design-v2
description: toss.tech 공개 디자인 아티클 143편의 본문에서 뽑은 제품 디자인 원칙, 문제 정의와 해결 과정, 의사결정 기준, 한국어 UX 라이팅(에러·마케팅·푸시 문구 포함), 퍼널과 사용자 흐름, 접근성(스크린리더·시니어·외국인), UX 리서치, 협업과 디자인 시스템 운영, 내부 툴·B2B, 인터랙션·브랜딩의 판단 기준, 시각 스타일(색·타이포·여백·라운드·컴포넌트·모션·아이콘·그래픽), AI 활용을 출처(글 제목·URL)와 함께 적용한다. 비공식이며 Toss와 제휴 관계가 없다. 화면이나 UI를 만들 때(references 전체에서 비슷한 화면의 사례와 이미지 묘사를 찾아 끝까지 읽고 만든다), 화면이나 플로우를 설계·리뷰할 때, 가입·인증·송금·결제 퍼널의 이탈을 줄일 때, UX 문구·에러 메시지·푸시를 쓰거나 고칠 때, 다크패턴인지 판단할 때, 접근성을 점검할 때, 리서치나 A/B 테스트를 설계할 때, 기능을 만들지 뺄지 정할 때, 팀 프로세스나 사내 툴의 비효율을 풀 때 쓴다.
---

# Toss Tech Design Skill v2

버전: **v2** (2026-11-21). 바뀐 내용은 `CHANGELOG.md`에 있다.

> 비공식 스킬. toss.tech 디자인 아티클 본문만 근거로 정리했고, Toss(비바리퍼블리카)와 제휴하거나 승인받은 관계가 없다. reference의 모든 규칙에는 출처 글의 제목과 URL이 붙어 있고, 「」 안은 원문 그대로다.

## 담은 것
- 디자인 원칙, 문제를 정의하고 푸는 과정, 의사결정 기준, UX 라이팅, 퍼널과 사용자 흐름, 접근성, 리서치·협업 방식, 글에 나온 Before→After 사례와 문구 예시.
- 시각 스타일: 본문에 나온 색, 타이포, 여백, 라운드, 컴포넌트(ListRow, BottomCTA, BottomSheet, Toast, Dialog 등), 모션, 아이콘·그래픽 규칙과 수치(`visual-style.md`). 값이 이미지에만 있으면 "이미지 기준", 어디에도 없으면 "아티클에 근거 없음"으로 표시했다.

## 화면이나 UI를 만들 때
화면은 부품(색·버튼)보다 조립, 곧 무엇이 어떤 순서와 덩어리로 놓이는지가 더 중요하다. 그 근거는 여러 파일에 흩어져 있다. 그러니 정해진 파일 몇 개만 읽지 말고, 토큰을 아끼지 말고 references 전체에서 넓게 찾아 읽은 뒤 만든다.

1. **만들 화면을 정의한다.** 화면 유형(입력, 목록, 홈, 상세, 선택, 완료·대기, 에러 등), 이 화면의 핵심 과업 하나, 사용자가 이 화면 직전과 직후에 거치는 흐름을 적는다.
2. **references 전체에서 근거를 찾는다.** 화면 유형·도메인·컴포넌트를 가리키는 낱말과 그 비슷한 말로 `references/` 전체를 검색한다(예: 입력 화면이면 입력, 키보드, 필드, 가입, 인증, CTA). 특히 다음은 빠짐없이 찾는다.
   - `visual-style.md`의 "이미지 기준" 항목. 실제 화면의 배치를 묘사한 유일한 자료다.
   - 모든 파일의 "Before → After"·"문제→해결" 사례 가운데 만들 화면과 같거나 비슷한 화면.
   - 그 화면에 들어갈 문구의 규칙(`ux-writing.md`, `ux-writing-errors-marketing.md`)과 접근성 규칙(`accessibility-inclusion.md`).
3. **찾은 절은 끝까지 읽는다.** 검색 결과 한 줄만 보고 판단하지 않는다. 파일이 커서 한 번에 안 읽히면 나눠 읽는다. `visual-style.md`는 앞부분에서 멈추지 말고 끝(§10, 점검 질문)까지 읽는다.
4. **화면 뼈대를 먼저 적는다.** 읽은 사례와 이미지 묘사를 바탕으로 위에서 아래로 놓일 요소와 덩어리의 순서를 적고, 결정마다 근거가 된 사례를 붙인다. 사례끼리 부딪히면 이 화면의 맥락에 더 가까운 쪽을 따르고 이유를 적는다.
5. **그다음 색·타이포·여백·라운드·컴포넌트·모션을 입힌다.** `visual-style.md`의 규칙을 따른다. 값이 없는 항목(§10 "아티클에 근거 없음")은 §10의 "정할 때의 기준"에 따라 정하고, 결과물에 "아티클에 근거 없음"이라고 밝힌다.
6. **만든 뒤 다시 대조한다.** 결과를 2에서 찾은 사례·이미지 묘사와 나란히 놓고 구조가 다른 곳을 고친다. 실행 환경이 허락하면 렌더링한 스크린샷으로 확인한다.

## 핵심 원칙
1. **단순함**: 사용자가 따로 알거나 배울 것 없이 본능적으로 이해하게 만든다. 인지 비용, 심리 비용, 노동 비용을 줄인다. 출처: [크고 복잡한 제품, 과감하게 갈아엎기](https://toss.tech/article/mydoc) → `principles.md` §1.2~§1.5
2. **한 화면에 하나**: 한 화면에서는 메시지 하나에 집중하고 액션 하나만 요구한다(One thing per one page). 출처: [모티베이션을 디자인하기](https://toss.tech/article/design-motivation), [거꾸로 입력하는 가입 화면, 처음에 어떻게 떠올렸을까?](https://toss.tech/article/toss-signup-process) → `principles.md` §1.6
3. **3초 안에 답할 수 있는 질문**: 답이 3초 안에 나오지 않으면 질문을 바꾸거나 그 단계를 없앤다(Easy to answer). 출처: [토스 디자인 원칙, Easy to answer](https://toss.tech/article/insurance-claim-process) → `principles.md` §1.7
4. **가치 먼저, 비용은 나중에**: 입력·인증·동의를 요구하기 전에 얻을 가치를 먼저 보여 준다(Value first, cost later). 출처: [토스 디자인 원칙 Value first, Cost later](https://toss.tech/article/value-first-cost-later) → `principles.md` §1.8
5. **개선보다 제거**: 불편한 단계를 잘 넘게 돕기 전에 그 단계를 없앨 수 있는지 묻는다. 기능은 편의가 아니라 비용이다. 출처: [송금할 때 은행 이름을 꼭 입력해야 할까요?](https://toss.tech/article/toss-money-transfer-bank-recommendation), [독이 되는 레퍼런스 활용법](https://toss.tech/article/bad-reference-uses) → `principles.md` §2.1~§2.2
6. **진짜 문제부터**: 화면을 그리기 전에 문제를 한 문장으로 적고 '왜'를 반복해 원인의 원인을 찾는다. 출처: [문제 원인의 원인을 찾아서](https://toss.tech/article/real-reason) → `problem-solving.md` §2
7. **나는 유저가 아니다, 익숙함은 부채다**: 만드는 사람에게 당연한 것과 업계 관습을 의심한다. 출처: [토스에서 하루 만에 제품 출시하는 법](https://toss.tech/article/launching-product-in-one-day), [송금할 때 은행 이름을 꼭 입력해야 할까요?](https://toss.tech/article/toss-money-transfer-bank-recommendation) → `principles.md` §3.1, §4.3
8. **내 아이디어를 믿지 말고 확인한다**: 개발 전에 프로토타입으로 사용자 반응을 본다. 출처: [내 아이디어를 너무 믿지 마세요](https://toss.tech/article/dont-trust-your-gut) → `research-methods.md` §3.10
9. **에러는 다음 단계로 안내한다**: 최고의 에러는 발생하지 않는 것이다. 남는 에러는 상황·이유·해결책을 사용자 언어로 알린다. 출처: [좋은 에러 메시지를 만드는 6가지 원칙](https://toss.tech/article/how-to-write-error-message) → `ux-writing-errors-marketing.md` §1, `principles.md` §1.10
10. **유저가 아니라 사람이다**: 거부할 권리, 감정, 알아야 할 권리, 정보의 통제권, 다양한 감수성, 접근성을 존중한다. 윤리 원칙은 제품 원칙과 경쟁하지 않고 그 근간에 놓인다. 출처: [토스만의 제품 윤리 원칙 탄생기](https://toss.tech/article/27190) → `ethics.md` §1.4, §1.6
11. **한 사람의 불편을 풀면 모두가 편해진다**: 당장 불편을 겪는 사람의 문제를 해결하면 더 많은 사람의 잠재적 문제까지 해결된다. 출처: [시니어 사용자가 어려워하는 UX 5가지](https://toss.tech/article/senior-usability-research) → `accessibility-inclusion.md` §1.4

## 상황별로 읽을 파일
| 상황 | 먼저 읽을 파일 | 함께 볼 파일 |
|---|---|---|
| 화면이나 UI 만들기 (뼈대·색·타이포·여백·라운드·컴포넌트·모션·아이콘·그래픽) | 위 "화면이나 UI를 만들 때"의 절차 (references 전체 검색) | `visual-style.md` 끝까지 |
| 화면·기능이 좋은 제품의 기준에 맞는지 점검 | `principles.md` | `ethics.md` |
| 광고·혜택·기본값·알림 설계, 다크패턴 판단, 일부러 어렵게 만드는 장치 | `ethics.md` | `ux-writing.md` §5 |
| 기능 요청이나 지표 하락을 받고 진짜 문제를 정의 | `problem-solving.md` | `research-methods.md` |
| 기존 제품을 고칠지 갈아엎을지, 현장에서 끝까지 푼 사례 | `problem-solving-cases.md` | `decision-making.md` §6 |
| 무엇을 만들고 뺄지, 우선순위, 사용자가 적은 제품을 만들지 | `decision-making.md` | `data-and-experiments.md` |
| 지표 읽기, A/B 테스트 설계와 해석, 레퍼런스를 따를지 | `data-and-experiments.md` | `research-ops.md` §2 |
| 화면 문구·이름·버튼·질문, 보이스앤톤, 라이팅 가이드와 시스템 | `ux-writing.md` | `ux-writing-errors-marketing.md` |
| 에러 메시지, 마케팅·푸시·배너, 캠페인 메시지 | `ux-writing-errors-marketing.md` | `ux-writing.md`, `ethics.md` |
| 입력·클릭·질문 줄이기, 가치 먼저 보여 주기, 완료·대기 화면 | `funnels-and-flows.md` | `domain-flows-and-ia.md` |
| 가입·인증·송금·결제·투자 흐름, 추천, 메뉴·정보 구조, 홈 | `domain-flows-and-ia.md` | `funnels-and-flows.md` |
| 스크린리더·시니어·외국인 사용자, 디자인 시스템의 접근성 | `accessibility-inclusion.md` | `research-ops.md` §1 |
| 리서치 방법 고르기, 인터뷰·UT·게릴라 테스트, 현장 관찰 | `research-methods.md` | `research-ops.md` |
| 낯선 도메인·만나기 어려운 사용자, 지표·설문, 리서치 운영 | `research-ops.md` | `research-methods.md` |
| 직무와 역할, 새 팀, 온보딩·채용·성장 | `team-roles-and-growth.md` | `working-with-teams.md` |
| 디자인 시스템·가이드·툴 운영, 라이팅·윤리 기준을 조직에 퍼뜨리기 | `design-systems-and-standards.md` | `ux-writing.md` §6 |
| 개발자와 협업, 팀 설득, 빠른 실행 | `working-with-teams.md` | `team-roles-and-growth.md` |
| 사장님·B2B 제품, CS·운영 툴, 어드민, 슬랙봇, 사내 업무 효율화 | `internal-tools-b2b.md` | `decision-making.md` §5 |
| 인터랙션·모션을 넣을지, 캐릭터·게임 요소 | `interaction.md` | `visual-style.md` §6 |
| 그래픽·로고·이모지·서체·캠페인·공간을 만들 때의 판단 기준 | `graphics-branding.md` | `visual-style.md` §7~§8 |
| AI 상담·리서치 봇·그래픽 생성·업무 자동화 | `ai-practices.md` | `internal-tools-b2b.md` |
| 글 목록과 각 글을 인용한 파일 | `sources.md` | |

파일은 모두 `references/` 아래에 있다.

## 쓰는 법
이 절은 아티클 내용이 아니라 이 스킬을 쓰는 규칙이다.
1. 화면이나 UI를 만드는 요청이면 위 "화면이나 UI를 만들 때"의 절차를 따른다. 그 밖의 요청은 위 표에서 맞는 파일을 열고 "핵심 요약"으로 방향을 잡은 뒤, 관련 내용이 다른 파일에도 있을 수 있으면 references 전체를 검색해 함께 읽는다.
2. 설계안·리뷰·문구 제안에 적용한 규칙의 출처(글 제목과 URL)를 함께 적는다.
3. Before→After 사례와 문구 예시는 비슷한 상황을 판단하는 근거로 쓴다. 문구는 프로젝트의 맥락과 용어에 맞게 다시 쓴다.
4. reference에 근거가 없는 판단이 필요하면 "아티클에 근거 없음"이라고 밝혀 출처 있는 규칙과 구분한다.
5. 결과물에 Toss·토스 명칭, 로고, 서비스명, 캠페인 문구, 전용 자산(토스페이스, Toss Product Sans 등)을 넣지 않는다. 사례 속 서비스명은 출처를 밝힐 때만 쓴다.
6. 결과를 내기 전에 읽은 파일 끝의 "점검 질문"으로 스스로 확인한다.

변경 내역은 `CHANGELOG.md`에 있다.
