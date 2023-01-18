# 자바 프로그래밍을 공부하는 이유?
- 기업에서 서버 프로그래밍 시 가장 많이 사용하는 언어

# 자바 언어의 특징
- 객체지향 언어
- 자바 언어는 느리지만, 버전업 되면서 다른 언어들의 장점을 흡수하고 있다.(모던 자바)
  - 람다(Lambda) : 함수형 프로그래밍
  - Stream API : 람다 표현식과 메서드 참조 등의 기능과 결합해서 매우 복잡하고 어려운 데이터 처리 작업을 쉽게 조회하고 필터링하고 변환하고 처리할 수 있도록 한다.
  - 병렬 프로그래밍 : 여러 개의 CPU 코어에서 작업을 배분해서 동시에 작업을 수행한다.

# 자바 프로그램 작성과 실행
- JDK(Java Development Kit)이라는 프로그램을 다운로드하고 설치해야 한다.
- 여러 종류의 JDK가 존재한다. openjdk, Oracle JDK, Azul Julu JDK, Amazon Corretto OpenJDK, Adoptium Temurin 등
- 이클립스 재단(The Eclipse Foundation)의 어댑티움(Adoptium) 프로젝트가 '이클립스 테무린(Eclipse Temurin) 자바 SE 바이너리'의 첫 번째 릴리즈를 출시했다. 이는 인텔 64비트 프로세서 기반 윈도우, 리눅스, 맥 OS용 자바 SE 8, 자바 SE 11, 자바 SE 17의 최신 버전을 다루는 오픈 JDK(OpenJDK)의 '프로덕션 레디(production-ready)' 빌드다.

# JDK 11 설치
- 초보자가 공부할 때는 JDK 8도 충분. 서비스 업체들의 경우 11이상을 사용하는 경우가 많다.
- JDK 17을 고려하는 경우
  - Java 17이 2021년 9월 출시.
  - 10부터는 6개월마다 출시. LTS(Long Term Support)버전은 3년마다 출시.
  - JDK 8 LTS가 JDK 11 LTS보다 유지보수 기간이 더 길다. 그래서, 직접 17로 업데이트하는 것을 고려
- M1 Mac용 JDK는 17 버전에서 지원.
- https://adoptium.net/releases.html?variant=openjdk11&jvmVariant=hotspot
- M1 Mac용 JDK 11 - Azul Zulu JDK
- https://www.azul.com/downloads/?version=java-11-lts&os=macos&architecture=arm-64-bit&package=jdk
- java 8, 11, 17은 LTS 버전이다.
- JDK에 버그가 있거나 그럴 경우 버그 수정등이 필요한데 LTS는 Long-term Support라고 해서 장기 지원 버전을 말한다.
- LTS 버전은 유지보수 기간이 길다.
- 8 버전은 사용자가 많이 사용하고 있기 때문에 유지보수 기간을 다른 LTS보다 더 길게 잡았다. 11 버전보다도 더 길다.

서버 프로그래밍 즉 백엔드 프로그래밍을 할 때 Linux 운영체제를 많이 사용한다.  
Java 개발자라면 Linux 공부를 많이 해야 한다.  

리눅스를 잘 알아야 하는 이유는 
- 자바 개발자들은 리눅스 운영체제로 동작하는 서버에 접속을 해서 여러가지 명령을 수행할 때가 많기 때문이다.

개발자가 Mac 컴퓨터를 좋아하는 이유 중에 하나는 맥과 리눅스가 서로 호환이 되는 부분이 많아서 그렇다.  
맥 터미널이 리눅스와 거의 유사하기 때문에 서버에서 배포하거나 이럴 때 상당히 편리하다. (맥 명령과 리눅스 명령이 많이 호환되니까)

# JDK 11 설치 - Mac 사용자
- 터미널에서 `echo $0`이라고 명령한다.
- zsh라고 나올 경우  
  `code ~/.zshrc` 명령을 수행한다.
- bash라고 나올 경우  
  `code ~/.bashrc` 명령을 수행한다.
- 파일을 열었으면 마지막 줄에 다음을 추가한다.  
  `export JAVA_HOME=$(/usr/libexec/java_home -v 11)`  
  `export PATH=$PATH:$JAVA_HOME/bin`

zsh는 z shell의 줄임말이다.  
이게 의미하는 것은  내가 입력한 명령을 읽어들인 후 그 명령을 대신 실행해주는 것이 `shell(쉘)`이다.  
쉘에는 다양한 종류가 있다. Linux에서 많이 사용되는 shell은 bash, zsh이다.  
이제는 zsh이 기본으로 설치되어 제공되고 있다.  
왜 shell 이름을 알아야 할까요?  
"echo $0"이라고 명령을 내리면 현재 터미널에서 사용되고 있는 쉘이 무엇인지 확인이 가능하다.  
확인을 하는 이유는 shell 마다 설정 파일의 이름이 다르기 때문이다.

환경 변수 설정을 위해 .zshrc 파일을 수정을 하고 수정된 .zshrc 파일을 저장을 해도 이 환경 설정은 바로 적용이 안된다.  
새롭게 설정한 환경변수를 적용하려면 터미널을 새로 열어주던지 `source ~/.zshrc`라고 명령을 입력하게 되면 바뀐 설정이 바로 적용된다.

java -version, javac -version 이라고 실행했을 때 결과가 11로 잘 출력돼야 한다.  

# 자바 프로그램 작성과 실행
- java 컴파일러 javac 명령으로 Hello.java를 컴파일 한다.
  `javac Hello.java`
- 컴파일이 성공하면 오류메세지가 없이 `Hello.class` 파일이 생성된다.
- `ls -la` 명령으로 파일이 생성되었는지 확인한다.
- JVM(자바 가상 머신)으로 `Hello.class`를 실행한다. 
- java 명령이 JVM을 의미한다.
- 이 때 확장자는 입력하지 않는다.(.class) `java Hello`
- 자바라는 프로그램을 실행할 때는 JVM이라고 불리는 프로그램이 필요하다.

정리하자면, 소스코드를 작성한 이후에 실행하기 위해서는 2가지 과정이 필요하다.
- javac 라는 명령으로 소스코드를 컴파일해서 클래스 파일을 생성해야 한다.
- 클래스 파일이 생성되었다면, 이 클래스 파일을 실행하기 위해서 java 라는 명령을 실행해야 한다.
- 클래스를 실행할 때 주의해야할 점은 .class는 생략해야 한다는 것.

공부해야 할 키워드 `컴파일`, `자바 가상 머신`

