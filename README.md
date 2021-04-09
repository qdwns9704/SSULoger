

# SSULoger

### Github Pages를 활용한 블로그 서비스 및 UI구현

> 숭실대학교 오픈소스기반 기초설계 프로젝트
>
> 1. 팀 구성
>    * 20162448 컴퓨터학부 2학년 김병준 (팀장):	qdwns9704
>    * 20162443 컴퓨터학부 2학년 김동규:             donggggg
>    * 20162518 컴퓨터학부 2학년 최승서:             frics
>    * 20180271 소프트웨어학부 2학년 김상엽:       KIM-TABLE-NEXT
>    * 20180285 소프트웨어학부 2학년 박민준:       pmj6541
> 2. 역할
>    * 프로젝트 매니저: 김병준
>    * 프론트엔드 개발: 김동규, 최승서, 김상엽
>    * 문서화 작업: 박민준
> 3. 사용된 정적 사이트 생성기
>    * Jekyll
> 4. 기획 배경
>    * 프로젝트 진행 중 문제 해결 시 따로 정리해두지 않음
>    * 이후 같은 문제 경험 시 기억나지 않음
>    * 이전 경험과 동일한 트러블슈팅을 위한 조사 및 해결 작업 반복
> 5. 기대 효과
>    * Git 활용 및 협업 능력 향상
>    * 웹사이트 개발 및 운용 능력 향상
>    * UI 디자인 설계 능력 향상
> 6. 협업 규칙
>    1. 모든 팀 구성원은 **clone** 명령어로 중앙저장소를 복제한 로컬 저장소를 생성 후 로컬에서 작업
>    2. 모든 **Commit**은 원격저장소의 변경 이력을 로컬저장소에 **동기화** 한 뒤 **Push**
>    3. 새로운 기능을 개발할 때에는 **feature-NAME**으로 **Branch**로 분기 후 해당 Branch에서 작업
>    4. 기능 개발이 완료되면 **Push**한 뒤 **Pull-Request**로 팀장에게 **Merge** 요청
>    5. 각 기능이 개발이 완료되면 **develop**에 **Merge**
>    6. 원격저장소의 **develop**에서 버그가 없는 상태일 경우 **master**로 **Merge**
>    7. 원격저장소에서 보여지는 **README.md**는 **master**에서 수정
>    8. 포스트는 마크다운으로 작성
>    9. 포스트 작성은 **master**에서 작업하며, 작성중인 포스트는 **_draft**, 발행 시 **_posts** 디렉토리에 저장
>    10. 기능 개발은 **_includes** 디렉토리에서 작업하며, 필요한 리소스들은 **assets** 디렉토리에 저장
>    11. 작성 중인 문서는 **master**에서 **post**로 분기하여 작성
>    12. 문서 작성이 완료되면 **master**로 합병
>    13. 합병 이후 각 기능에서 발견한 오류는 **develop**에서 수정 후 커밋
> 7. 진행 현황
>    * README.md (진행중)
>    * header (진행중)
>    * footer (진행중)
>   * 1주차 진행현황
>       * 목표
>	       * 프론트 엔드의 블로그 디자인 및 구성
>	       * 블로그 디자인에 따른 기능 세분화
>	       * 세분화 된 기능 백 엔드에게 전달
>	       * 프론트 엔드와 백 엔드의 코드 오류 내용 문서화에게 전달
>
>	    * 진행 현황
>	       * 팀원 역할분배
>	       * 프로젝트 진행을 위한 블로그 생성
>	       * 블로그 디자인 구상 _CONTENT구상
>	       * 비고. POSTING PART는 아직 대기
>
>	    * 계획
>	       * 블로그 포스트 기능 완성
>	       * 포스트 기능 구현 중 오류사항 문서화 후 포스트
>	       * 세분화 된 기능 중 하나 완성
>
>
>  * 2주차 진행현황
>     * 목표
>	       * Jekyll 스터디
>	       * README.md 작성 시작(지속), Jekyll 설정 초기화
>	       * hearder, footer 기능 구현 시작(지속), CSS 및 페이지 연결, 협업규칙 결정(지속)
>
>     * 진행 현황
>	       * Jekyll Setup
>	       * header, footer 기능 구현(지속)
>	       * 메인, 카테고리 화면 디자인 구상
>	       * 네비게이션 메뉴 페이지 연결
>         * README.md 작성 (지속)
>	       * 협업 규칙 세분화
>
>     * 다음 개발 목표
>	       * 메인 화면 디자인 구현 마무리
>	       * CSS 작성(지속)
>	       * 포스트 리스트 기능
>	       * README.md 작성(지속)

### 1. 설치

1. git fetch or pull or clone
2. [Jekyll] 설치

```console
$ git clone git@github.com:qdwns9704/qdwns9704.github.io.git
$ cd qdwns9704.github.io
$ bundle install
```

### 2. 실행(로컬)

```consol
$ bundle exec Jekyll serve
$ open http://localhost:4000
```

### 3. 배포(발행)

```
$ git commit -m '...'
$ git push origin master
```

### 4. 새 글 작성

1. `_drafts` 디렉토리에 `ANY_POST_NAME.md` 이름으로 파일 생성

2. 포스트는 마크다운으로 작성

   - [gfm] 문법, [kramdown] 파서, [rouge] 문법강조기 사용

3. 확인

   ```
   $ bundle exec jekyll serve --drafts
   ```

### 5. 글 쓰기

1. `_posts` 디렉토리에 `yyyy-mm-dd-slug.md` 파일로 복사(or 이동)
   - slug: 해당 포스트의 고유 키로 url의 일부로 사용. 왠만하면 특수문자없이 영문자,숫자,-(하이픈),.(점)...만 사용
   - yyyy,mm,dd: 발행 년,월,일
   - 참고: 최종적으로 포스트의 url(permalink)는 http://qdwns9704.github.io/yyyy/mm/dd/slug/

2. 파일 상단에 [front matter] 작성
 - layout: post # 레이아웃(필수). `page` 레이아웃을 사용하면 목록에 보이지 않는 글을 쓸 수 있음.
 - title: '제목' # 제목(필수)
 - author: `lastname.firstname` # 필자(필수)
 - tags: `[tag1,tag2,tag3,...]` # 태그 목록(선택). 왠만하면 특수문자없이 영소문자,숫자,-(하이픈),.(점)...만 사용.
 - image: http://... # 커버이미지 url(선택)
 - date: `YYYY-MM-DD HH:MM:SS` # 발행일(필수)
### 6. 필자 등록

### 7. 태그 등록

### 8. 구조

> 자세한 내용은 [Jekyll] 참조할 것.

* Gemfile, Gemfile.lock

  > 사이트에 필요한 Ruby Gem을 Bundler에게 알려주는 역할

* _config.yml

  > 환경 설정 파일
  >
  > ```
  > // Jekyll 이 읽어들일 파일의 경로를 변경한다.
  > source: DIR
  >
  > // Jekyll 이 생성할 파일의 경로를 변경한다.
  > destination: DIR
  >
  > // 사용자 플러그인을 비활성화하고 심볼릭 링크를 무시한다.
  > safe: BOOL
  >
  > // 특정 디렉토리나 파일을 변환되지 않도록 제외시킨다.
  > // Site Source 를 기준으로 한 상대경로로 정의하며,
  > // Site Source 디렉토리 바깥의 다른 경로는 지정할 수 없다.
  > exclude: [DIR, FILE, ...]
  > 													
  > // 특정 디렉토리나 파일을 변환 작업에 강제로 포함시킨다.
  > // 사이트 생성 전 Site Destination 을 초기화 때, 유지 할 파일을 지정한다.
  > include: [DIR, FILE, ...]
  > 															
  > // 사이트 생성에 사용할 타임존을 지정한다.
  > // 이 옵션은 루비가 날짜와 시간을 생성/수정할 때 사용하는 환경변수인 TZ 를 설정한다.
  > // IANA 타임존 데이터베이스의 모든 항목을 사용할 수 있다.
  > timezone: TIMEZONE						
  >
  > // 파일의 인코딩을 지정한다.
  > encoding: ENCODING
  > ```

* directory

  1. _drafts

  > 아직 게시하지 않은 포스트들을 저장하는 디렉토리로 파일 명 형식에 날짜가 없음.

  2. _includes

  > 재사용하기 위한 파일을 저장한 디렉토리로 필요에 따라서 포스트나 레이아웃을 쉽게 삽입 가능하다.
  >
  > 아래와 같이 Liquid태그를 사용하면 ```_includes/file.ext``` 파일에 담긴 코드가 삽입된다.
  >
  > ```
  > ...
  > {% include file.ext %}
  > ...
  > ```

  3. _layouts

  > 포스트를 포장할때 사용하는 템플릿이다.
  >
  > 각 포스트 별로 레이아웃을 선택하는 기준은 [YAML 머리말]이며, 아래와 같이 Liquid태그를 사용하면 페이지에 컨텐츠가 삽입된다.
  >
  > ```
  > ...
  > {{ content }}
  > ...
  > ```

  4. _posts

  > 게시한 포스트들이 저장되어있는 디렉토리이다.
  >
  > 포스트의 파일 명은 ```YEAR-MONTH-DAY-title.md``` 와 같은 형식을 지켜야한다.
  >
  > [고유주소](https://jekyllrb-ko.github.io/docs/permalinks/)는 포스트 별로 각각 정의할 수 있지만, 날짜와 마크업 언어 종류는 오로지 파일명에 의해 결정된다.

  5. _data

  > 사이트에 사용할 데이터를 적절한 포맷으로 정리하여 보관하는 디렉토리이다.
  >
  >  Jekyll 엔진은 이 디렉토리에 있는 (확장자와 포맷이 `.yml` 또는 `.yaml`, `.json`, `.csv` 인) 모든 데이터 파일을 자동으로 읽어들여 `site.data` 로 사용할 수 있도록 만든다.
  >
  > 만약 이 디렉토리에 `members.yml` 라는 파일이 있다면, `site.data.members` 라고 입력하여 그 컨텐츠를 사용할 수 있다.

  6. _sass

  > Sass 파일들이 저장되어있는 디렉토리이다.
  >
  >  프로젝트의 `main.scss`에 import할 수 있으며 import 후에는 다시 하나의 스타일시트(`main.scss`)로 가공되어 사이트에 사용되는 스타일들을 정의한다.

  7. _site

  > Jekyll 이 변환 작업을 마친 뒤 생성된 사이트(캐시)가 저장되는 디폴트 경로이다. (수정 가능)
  >
  > 대부분의 경우, 이 경로를 `.gitignore` 에 추가한다.

  8. 다른 파일 및 폴더

  > `css` 나 `images` 폴더, `favicon.ico` 파일같이 앞서 언급하지 않은 다른 모든 디렉토리와 파일들은 있는 그대로 생성된 사이트에 복사한다.

* Index.html 또는 index.md 및 다른 HTML, 마크다운, Textile 파일

  > Jekyll 은 [YAML 머리말] 섹션을 가진 모든 파일을 찾아 변환 작업을 수행한다.
  >
  > 위에서 언급하지 않은 다른 디렉토리나 사이트의 루트 디렉토리에 있는 모든 `.html`, `.markdown`, `.md`, `.textile` 이 여기에 해당한다.



[YAML 머리말]: https://jekyllrb-ko.github.io/docs/frontmatter/
[Github Pages]: https://pages.github.com
[Jekyll]: https://jekyllrb.com
[gfm]: https://guides.github.com/features/mastering-markdown/
[kramdown]: http://kramdown.gettalong.org
[rouge]: http://rouge.jneen.net
