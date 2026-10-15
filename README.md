# ThRead · SSAFY 관통 프로젝트 03

HTML · CSS · Bootstrap 5.3.3을 사용한 반응형 도서 추천·독서 커뮤니티 화면입니다.

- 배포: https://windycar.github.io/03-pjt/
- GitHub: https://github.com/windycar/03-pjt
- GitLab 제출: https://lab.ssafy.com/jyc686397/03-pjt

## 참여 및 제출 설정

- 정용철: 저장소 Owner
- 김정훈 (`kjh5647jh`): 팀원 · GitLab Developer
- 김준철 강사님 (`kjc1125`): GitLab Maintainer
- GitLab 프로젝트명: `03-pjt`, 개인 계정 `jyc686397` 아래 비공개 저장

## 실행

`index.html`을 브라우저에서 열거나, 이 폴더에서 `python -m http.server 8033` 실행 후 `http://localhost:8033`으로 접속합니다. Bootstrap과 지도는 외부 연결이 필요합니다. 별도의 API 키나 빌드 과정은 없습니다.

## 구성과 요구사항

| 번호 | 구현 내용 | 소스 |
| --- | --- | --- |
| F301 | 투명·절대 위치 Navbar, 지정 폰트·색상, 576px 메뉴 전환 | 01-navbar.html |
| F302 | Hero 배경·오버레이·브랜드, 모바일 줄바꿈 | 01-navbar.html |
| F303 | 12권을 4권씩 묶은 자동 Carousel, 다음 버튼만 표시, 표지 150×220 | 02-bestseller.html |
| F304 | 80% 너비, Bootstrap 7:5 Grid와 강조 문구 | 03-ai_recommendation.html |
| F305 | 80% 너비의 Flexbox 4열, 576px 미만 1열, 장르 오버레이 | 04-genre_list.html |
| F306 | Bootstrap Card 3열·모바일 1열, 하단 저자·도서명, Pagination | 05-popular_thread.html |
| F307 | 전체 섹션 통합, 필수 Flexbox 장르 목록 유지 | index.html / 06-main.html |
| F308 | 로그아웃 Modal, 닫기·취소·로그아웃·바깥 클릭으로 닫기 | index.html / 06-main.html |
| F309 | 992px 이상에서 베스트셀러를 Hero 하단에 겹쳐 배치 | index.html / 06-main.html |
| F310 | 크기가 다른 장르 타일을 CSS Grid로 배치, 모바일 1열 | 04-genre_list_grid.html |
| F311 | 채식주의자 상세, 전체 화면 Hero, 탭·지도·쓰레드 목록 | 07-book_detail.html |

메인 페이지의 채식주의자 표지를 누르면 상세 페이지로 이동합니다. 메인 하단의 링크에서 심화 Grid 화면을 볼 수 있습니다. `assets/`에 제공된 이미지와 폰트를 보관합니다.

## 검사와 수정

최신 ZIP의 구현 파일을 이전 스켈레톤 ZIP 및 프로젝트 03 명세서와 비교했습니다. 배포 진입점·README를 추가했고, 좁은 화면에서 장르가 4열을 유지하지 못하는 문제를 수정했습니다. 통합 화면은 필수 Flexbox 장르 목록을 사용하고 심화 Grid를 별도 파일로 보존했습니다. 320px 화면의 표지 넘침, 중간 화면의 베스트셀러 배치, 모바일 메뉴 가독성, 메인·상세 연결도 보완했습니다.

실제 검증 결과와 화면 캡처는 `docs/검사결과.md` 및 `docs/screenshots/`에서 확인할 수 있습니다.

## 구현 과정에서 확인한 점

- 고정 200px 장르 타일은 화면이 좁아지면 자동으로 2~3열이 됩니다. 필수 4열을 유지하려면 타일 너비를 부모 너비와 간격에서 계산해야 합니다.
- Bootstrap의 breakpoint와 사용자 정의 CSS breakpoint를 함께 맞춰야 표지·제목이 겹치지 않습니다.
- 독립 HTML에서 정상인 경로도 통합·배포 후 다시 확인해야 합니다. 상대 경로를 사용하면 GitHub Pages의 `/03-pjt/` 하위 경로에서도 동작합니다.
- 필수 Flexbox 구현과 심화 CSS Grid 구현을 각각 보존하면 두 요구사항을 별도로 확인할 수 있습니다.
- Bootstrap JS는 Carousel·Collapse·Modal·Tab 동작에 필요합니다.

## 구현 범위와 제출 전 확인

이번 과제는 화면 구성 단계입니다. 로그인·실제 로그아웃·개인화 AI·실시간 검색·실제 대여 조회·쓰레드 작성/저장·페이지별 데이터 조회는 백엔드와 연결되지 않은 화면 예시입니다. Navbar의 마이 페이지는 현재 추천 섹션으로 연결됩니다. 지도는 국회도서관 위치 예시이며 실제 소장·대여 여부를 보장하지 않습니다.

원본 강의 PDF와 강의 예제의 API 관련 파일은 공개 배포에 포함하지 않았습니다. 사용자 제공 이미지·폰트는 과제 화면 표시 목적으로 사용했습니다. 담당 강사 Maintainer와 팀원 Developer 등록을 완료했습니다. 학습·느낀 점은 위 기술 기록을 참고해 본인의 경험으로 보완할 수 있습니다. 외부 지도 응답은 HTTP 200을 확인했지만 검사 브라우저의 iframe에서는 빈 화면으로 보여, 상세 페이지에 Google 지도 직접 열기 링크를 추가했습니다.
