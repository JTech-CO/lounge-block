# lounge-block

> **네이버 라운지에서 특정 사용자의 글을 숨기는 Chrome 확장 프로그램**

## 1. 소개 (Introduction)

네이버 라운지(lounge.naver.com)는 공식적으로 사용자 차단 기능을 지원하지 않습니다.  
lounge-block은 이를 브라우저 확장 프로그램으로 보완하여, 지정한 사용자의 게시글을 피드에서 깔끔하게 숨겨줍니다.

**주요 기능**
- **사용자 차단**: 닉네임을 입력하면 해당 사용자의 게시글이 피드에서 즉시 사라짐
- **최대 10명** 차단 가능
- **차단 해제**: 언제든지 목록에서 개별 해제 가능
- **자동 적용**: 페이지 로드 및 스크롤로 추가되는 게시글에도 자동 적용
- **SPA 대응**: 라운지 내 페이지 이동 시에도 차단 상태 유지
- **로컬 저장**: 차단 목록은 브라우저 로컬 저장소에만 보관, 외부 전송 없음

## 2. 기술 스택 (Tech Stack)

- **Platform**: Chrome Extension (Manifest V3)
- **Language**: Vanilla JavaScript (ES2020+)
- **Storage**: chrome.storage.local
- **Design**: 흑백 미니멀 UI

## 3. 설치 및 실행 (Quick Start)

**요구 사항**: Chrome 기반 브라우저 (Chrome, Edge, Brave 등)

1. **다운로드 (Download)**
   ```bash
   git clone https://github.com/jtech-co/lounge-block.git
   ```

2. **확장 프로그램 로드 (Load Extension)**
   - Chrome 주소창에 `chrome://extensions` 입력
   - 우측 상단 **개발자 모드** 활성화
   - **압축 해제된 확장 프로그램을 로드합니다** 클릭
   - 클론한 폴더 선택

3. **사용 (Usage)**
   - `lounge.naver.com` 접속 시 확장 프로그램이 자동 실행
   - 우측 하단 차단 버튼 클릭 → 패널 열기
   - 차단할 닉네임 입력 후 **차단** 버튼 또는 `Enter`
   - 해제 시 목록의 **해제** 버튼 클릭

## 4. 폴더 구조 (Structure)

```text
lounge-block/
├── manifest.json              # 확장 프로그램 설정 (Manifest V3)
├── injector.js                # MAIN world fetch 인터셉터 (API 응답 파싱)
├── content.js                 # 핵심 로직 (필터링 + UI)
├── icons/                     # 확장 프로그램 아이콘 (16/48/128px)
├── lounge-block-privacy-policy.html  # 개인정보 처리방침
└── README.md                  # 프로젝트 안내 문서
```

## 5. 정보 (Info)

- **Version**: 1.0
- **License**: MIT
- **Privacy Policy**: [개인정보 처리방침](https://jtech-co.github.io/lounge-block/lounge-block-privacy-policy.html)