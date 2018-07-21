# intelliJ 가이드
- [IntelliJ를 시작하시는 분들을 위한 IntelliJ 가이드](https://www.inflearn.com/course/intellij-guide/) 수강 후 정리.

## Toolbox 소개 (추천)
- [Toolbox App](https://www.jetbrains.com/toolbox/app/)을 통해 JetBrains IDE 제품들을 Install, Update, Setting(Maximum heap size...) 등의 작업을 할 수 있음.

## 프로젝트 생성
- Create New Project
- 순수 Java Application
    - Java 선택보단, Maven이나 Gradle 같은 빌드 환경 선택 추천
        - java application을 작성한다 하더라도 junit같은 테스트코드를 작성할때 필요한 라이브러리나, apache commons 등이 필요
        - Maven, Gradle 의존성 관리가 가능
- Gradle을 선택하고 프로젝트 생성
     - GroupId - 프로젝트 그룹
     - ArtifactId - 그룹의 하위 모듈, 스프링을 예로들어) spring security, spring mvc 같은 것
- OS 마다 단축키가 다름
    - 맥에서 개발할 때 해당 단축키가 윈도우나 리눅스에서는 어떻게 보이는지 알 수 있는 플러그인 : `Presentation Assistant`

## 코드 Edit

### 메인메소드 생성 및 실행

- 디렉토리, 패키지, 클래스 등 생성 목록 보기 : `Alt + Insert (Mac: Command + N)`
    - Project, Directory 우클릭 New 단축키
    - 내가 현재 위치에 생성할 수 있는 모든 리스트
- Code templete (흔히 사용하는 메소드 미리 정리 : 축약어)
    - `psvm` : public static void main() 생성
    -  `sout` : System.out.println() 생성
- Run (실행환경 실행)
    - 헌재 포커스 : ` Shift + Ctrl + F10 (Mac : Ctrl + Shift + R)`
    - 이전 실행 : `Shift + F10 (Mac : Ctrl + R)`

### 라인 수정하기
- 라인 복제하기 : `Ctrl + D (Mac : Command + D)`
- 라인 삭제하기 : `Ctrl + Y (Mac : Command + Delete(백스페이스))`
- 문자열 라인 합치기 : `Ctrl + Shift + J (Mac: Ctrl + Shift + J)`
- 라인 단위로 옮기기
    - 구문 이동 : `Shfit + Ctrl + 위아래 화살표 (Mac :Shift + Command + 위아래)` 
    - 라인 이동(구문에 관계없이 이동) : `Shift + Alt + 위아래 (Mac : Shift + Alt + 위아래)`
- Element 단위로 옮기기 : `Alt+ Ctrl + Shift + 좌우 화살표 (Mac: Option + Shift + Command + 좌우)`