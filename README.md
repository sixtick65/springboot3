# springboot3
스프링 부트3 학습하기

### 윈도우에 인텔리제이 설치하기
- [커뮤니티버전 다운로드](https://www.jetbrains.com/ko-kr/idea/download/download-thanks.html?platform=windows&code=IIC)
- 설치시에 PATH 등록 체크하기
- 학습 환경은 JDK 17로 한다. (프로젝트 생성시에 다운로드 및 선택 할 수 있다)
- 빌드 시스템은 gradle 을 쓴다. (스크립트 언어로는 groovy 를 쓴다. kotlin 도 있지만 groovy가 디폴트다.)
- 프로젝트 생성시에 고급설정에서 그룹ID를 설정하는데 org.example이 기본인데 배포할때 문제가 되므로 변경한다.

### 스프링부트3 프로젝트 설정하기
- src/build.gradle 을 연다
- ```
plugins {
    id 'java'
    id 'org.springframework.boot' version '3.2.0'  // 추가
    id 'io.spring.dependency-management' version '1.1.0' // 추가
}

group = 'me.shinsunyoung'
version = '1.0-SNAPSHOT'
sourceCompatibility = '17' //추가

repositories {
    mavenCentral()
}

dependencies {
    //testImplementation platform('org.junit:junit-bom:5.10.0')
    //testImplementation 'org.junit.jupiter:junit-jupiter'
    implementation 'org.springframework.boot:spring-boot-starter-web' // 추가
    testImplementation 'org.springframework.boot:spring-boot-starter-test' // 추가
}

test {
    useJUnitPlatform()
}
```
