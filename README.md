# 안녕하세요, 고성윤입니다.

현재 **삼성청년SW·AI아카데미(SSAFY) 16기 임베디드 트랙**에서 교육을 받고 있습니다.<br>
소프트웨어로 실제 장치를 움직이고, 서로 다른 시스템을 연결하는 데 관심이 있습니다.

[Email](mailto:kosy6410@naver.com) · [GitHub](https://github.com/kosyunderbar)

## 프로젝트

### 가상 제조공장 관제와 3D Factory

공정 사이를 이동하는 차체와 운반 차량을 모델링하고, 생산 데이터의 수집·이력 조회·관제를 연결했습니다. 기본 관제 시스템을 만든 뒤, 공장과 차량의 움직임을 살펴볼 수 있도록 3D로 확장했습니다. 공장의 동작과 센서 상태는 Python 모델로 생성합니다.

[![3D Factory의 AGV 추적 시점](assets/factory-3d.png)](https://github.com/kosyunderbar/3Dfactory)

<sub>3D 관제 실행 화면 — 차체를 운반하는 AGV의 추적 시점</sub>

**기본 관제 · Smart Factory**

- 눈에 보이는 빈자리도 이동 중인 차체의 목적지일 수 있어, 대기량과 예약량을 함께 계산해 배차 여부를 결정했습니다.
- 데이터를 받았다는 응답과 관제에 반영됐다는 사실을 구분했습니다. 원본과 전달 대기 정보를 함께 저장하고, 재전송된 보고가 실적을 중복 증가시키지 않도록 처리했습니다.
- 기본 버전에서 차체 100대의 작업·검사·운송 기록을 대조하고, 통신 단절과 서비스·DB 재시작 이후의 전달·반영을 검증했습니다.

**3D 확장 · 3D Factory**

- Three.js로 설비와 차량을 표현하고, AGV·AMR의 이동 경로·적재 상태와 차량 추적 시점을 연결했습니다.
- 통로 예약·양보와 AMR의 부품 보급을 모델링했습니다. 부품 재고는 배송 완료 시 증가하고 조립 시작 시 소비하도록 구분했습니다.
- 설비 고장 시 작업 진행량을 보존하고, 사용자의 점검·조치 이후 남은 작업을 이어가도록 했습니다.

요구사항과 공정 규칙을 정의하고 결과를 검토했으며, AI 개발 보조를 활용해 구현·검증을 진행했습니다.

`Java` `Spring Boot` `PostgreSQL` `Python` `Vue 3` `Three.js` `TCP` `REST / SSE`

[기본 관제 저장소](https://github.com/kosyunderbar/smartfactorysimul) · [3D 확장 저장소](https://github.com/kosyunderbar/3Dfactory)

---

### 캠퍼스 환경 지킴이

**2023.04 – 2023.10 · 팀 리더 / SW·AI·장치 제어**

카메라로 재활용품을 인식하고, 종류에 맞춰 분류·압축·파쇄 장치를 구동한 융합 캡스톤 프로젝트입니다. 기계·전기 전공 팀원들과 함께 제작했습니다.

- 실제 투입 환경에서 촬영한 데이터를 수집·증강해 YOLOv5를 학습하고, 인식 결과를 GPIO·모터 드라이버·릴레이 동작으로 연결했습니다.
- UI와 제어를 담당하는 두 Raspberry Pi 사이의 통신이 불안정해, Node.js 소켓 서버로 연결 구조를 바꿨습니다.
- 팀원들이 각자 장치를 테스트할 수 있도록 GPIO 연결·전압 기준과 SW 동작 순서를 가이드로 정리했습니다.

LINC 3.0 캡스톤디자인 경진대회 수상

`Python` `YOLOv5` `Raspberry Pi` `GPIO` `Node.js` `Linux`

[저장소](https://github.com/kosyunderbar/Capstone-AI-Recycling-Bot)

---

### LUMOS

**2024.04 – 2024.08 · 팀 리더 / AI·데이터 / Django 서비스 개발**

학사 정보 질의응답과 개인별 강의 추천을 제공하는 대학 생활 도우미입니다. AI·추천 기능을 맡은 Django 서비스와 메인 Spring Boot 백엔드를 REST API로 연결했습니다.

- 사용자 질문을 Dialogflow로 분류하고, 강의 추천·졸업 요건 조회·GPT 응답으로 처리 경로를 나눴습니다.
- 강의와 사용자 TECH 역량 데이터를 바탕으로 가중치 기반 추천 로직을 설계했습니다. 추천에 반영되는 기준을 직접 조정할 수 있도록 구성했습니다.
- 팀원들이 서비스 완성을 기다리지 않고 연동 개발을 진행할 수 있도록 JSON 명세와 목업 서버를 공유했습니다.

AISW 졸업작품 전시회 최우수상 · 컴퓨터공학부 졸업작품 1위

`Python` `Django` `MySQL` `Dialogflow` `GPT API` `Postman`

[저장소](https://github.com/kosyunderbar/LUMOS-Description)

---

### Pure C Image Processing

**2025.06 – 2025.08 · 개인 프로젝트**

OpenCV 없이 C로 BMP 파일을 읽고 픽셀을 다루며, 영상처리 알고리즘을 구현했습니다.

- 연결된 영역을 찾는 DFS에서 재귀 호출을 명시적 스택으로 바꿔 호출 스택 사용을 줄였습니다.
- 회전·확대 시 픽셀이 비는 문제를 다루기 위해, 출력 좌표에서 원본 좌표를 찾는 역방향 사상을 적용했습니다.
- Zhang-Suen 세선화, 침식·팽창, 자동 임계값 계산과 미디언 필터를 구현했습니다.

`C` `BMP` `Image Processing`

[저장소](https://github.com/kosyunderbar/Pattern-Recognize-Project)

## 그 외 작업

**CodifyNow** · 2023.04 – 2023.06 · 팀 리더<br>
촬영한 코드 이미지를 OCR로 변환하고 GPT API로 분석·수정하는 모바일 앱입니다.<br>
`Flutter` `Dart` `Google Cloud Vision` `GPT API` · [보고서](https://drive.google.com/file/d/1RhtEUdEpUjk9g2sI9vFQiIVYkYff8rcE/view)

**AI Vision Web** · 2023.09 – 2023.12 · 팀 프로젝트<br>
스타일 변환·초해상도·파노라마·스케치 기능과 이미지 처리 이력 관리를 연결한 웹 서비스입니다.<br>
`Django` `OpenCV` `TensorFlow` `Firebase` · [보고서](https://drive.google.com/file/d/12HLZZRPIO_XaaQbGT7RlUu4QeonH7_Ez/view)

## 사용 기술

| 분야 | 기술 |
| :--- | :--- |
| 언어 | C, C++, Java, Python, JavaScript |
| 장치·운영체제 | Raspberry Pi, GPIO, PWM, Linux |
| 서버·데이터 | Spring Boot, Django, PostgreSQL, MySQL |
| 화면·시각화 | Vue 3, Three.js, Apache ECharts |
| 개발 도구 | Git, Docker Compose, Postman |

## 자격·어학

정보처리기사 · SQLD<br>
TOEIC 885 · OPIc IH
