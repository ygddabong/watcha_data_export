# Watcha Pedia Exporter
왓챠피디아(Watcha Pedia)에 기록한 영화/TV 평점, 감상일, 리뷰 데이터를 CSV 파일로 추출하는 브라우저 콘솔용 스크립트입니다.

개인 백업용으로 사용할 수 있으며, 추출한 CSV를 기반으로 Letterboxd 등 다른 영화 기록 서비스로 데이터를 옮길 때 활용할 수 있습니다.

---
## Note 
* 2026 년 5월 6일 기준 문제없이 작동하는 것을 확인하였습니다.
* 오리지날 소스(https://github.com/erinyskim/watchapedia-export)가 정상적으로 작동하지 않아, 수정한 후 업로드하였습니다.
* 평점을 매긴 날짜의 데이터가 정상적으로 추출되지 않을 수 있습니다.

---

## Features

- 왓챠피디아 영화 평점 추출
- 왓챠피디아 TV 시즌 평점 추출
- 리뷰/코멘트 추출
- 감상일 추출
- 감독명 추출
- CSV 파일 자동 다운로드
- 429 Rate Limit 발생 시 자동 재시도
- 다운로드 진행률 표시

---

## How to Use

1. 브라우저에서 [왓챠피디아](https://pedia.watcha.com)에 로그인합니다.
2. 본인 프로필 페이지로 이동합니다.
3. 개발자 도구를 엽니다.
   - Chrome / Edge: `F12` 또는 `Cmd + Option + I`
   - Safari: 개발자 메뉴 활성화 후 Web Inspector 실행
4. `Console` 탭을 엽니다.
5. 스크립트를 붙여넣고 실행합니다.
6. 다운로드가 완료되면 .csv 파일이 자동으로 저장됩니다.

---
## Screenshots
### 콘솔 입력 화면
<img width="1920" height="1080" alt="스크린샷 2026-05-06 오후 10 10 18" src="https://github.com/user-attachments/assets/ccf44f60-9f76-4c0f-9885-a16f76ab2b41" />

‼️ 콘솔에서 아래와 같은 에러 메세지가 나오는 경우에는, 붙여넣기 허용 을 입력하고 엔터를 눌러 주세요. 허용이 된 후 스크립트를 입력해 주세요.

*이해하지 못했거나 직접 검토하지 않은 코드는 DevTools 콘솔에 붙여넣지 마세요. 이렇게 하면 공격자가 신원을 도용하거나 내 컴퓨터를 제어할 수 있습니다. 붙여넣기를 허용하려면 아래에 {PH1}을 입력하고 Enter 키를 누르세요.*


### 다운로드 진행 화면
<img width="1920" height="1080" alt="스크린샷 2026-05-06 오후 9 56 31" src="https://github.com/user-attachments/assets/befae43a-9e2f-4282-8acd-ad17af50489e" />


### CSV 결과 예시
<img width="1920" height="1080" alt="스크린샷 2026-05-06 오후 10 12 40" src="https://github.com/user-attachments/assets/c8caa5ec-16da-447a-88ef-bf947f2dd1b6" />


---

## CSV Output

생성되는 CSV 파일은 다음과 같은 컬럼을 포함합니다.

| Column | Description |
|---|---|
| ID | 왓챠피디아 콘텐츠 ID |
| URL | 왓챠피디아 콘텐츠 URL |
| Title | 콘텐츠 제목 |
| Type | MOVIE 또는 TV |
| Year | 제작 연도 |
| Directors | 감독명 |
| WatchedAt | 감상일 |
| Rating | 별점 |
| Review | 리뷰 |
| Spoiler | 스포일러 여부 |

---

## Important Notes

이 스크립트는 본인의 왓챠피디아 데이터를 개인적으로 백업하기 위한 용도로 만들어졌습니다.

주의할 점:

- 다른 사람의 데이터를 수집하는 용도로 사용하지 마세요.
- 과도한 요청을 보내지 않도록 요청 간 딜레이가 포함되어 있습니다.
- 왓챠피디아의 내부 API 구조가 변경되면 작동하지 않을 수 있습니다.
- 브라우저 콘솔에 코드를 붙여넣기 전에 반드시 내용을 확인하세요.
- 알 수 없는 출처의 스크립트를 그대로 실행하지 마세요.

---

## Letterboxd Migration

이 스크립트로 생성된 CSV는 왓챠피디아 백업용 형식입니다.

Letterboxd로 완전히 옮기려면 추가 가공이 필요할 수 있습니다.

특히 아래 항목은 매칭 정확도에 영향을 줄 수 있습니다.

- 왓챠피디아의 한국어 제목
- Letterboxd의 영어 제목
- 같은 제목의 다른 연도 작품
- 감독명 차이
- TV 시리즈 데이터

Letterboxd 이관용으로 사용하려면 영화 데이터만 따로 추출하거나, `Title + Year + Director` 기준으로 다시 정리하는 것을 추천합니다.

---

## Disclaimer

이 프로젝트는 왓챠피디아의 공식 도구가 아닙니다.

왓챠피디아와 관련이 없으며, 개인 데이터 백업을 돕기 위한 비공식 스크립트입니다. 사용자는 각 서비스의 이용약관을 확인하고, 본인의 책임 하에 사용해야 합니다.

---

## License

MIT License
