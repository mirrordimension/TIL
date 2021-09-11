# 2021.09.03. TIL (Byte code)

### Q. Java에서 바이트 코드란 무엇일까??

```
: 자바 바이트 코드(Java bytecode)란 자바 가상 머신이 이해할 수 있는 언어로 변환된 자바 소스 코드를 의미합니다.

: 자바 컴파일러에 의해 변환되는 코드의 명령어 크기가 1바이트라서 자바 바이트 코드라고 불리고 있습니다.
  (Q. 어떻게 바이트 코드로 변환되면 명령어 크기가 1바이트로 변환되는가???)

: 이러한 자바 바이트 코드의 확장자는 .class입니다.

: 자바 바이트 코드는 자바 가상 머신만 설치되어 있으면, 어떤 운영체제에서라도 실행될 수 있습니다.
```

<br>

### Q. 바이트 코드는 어떻게 생성되는가?
```
: 자바 컴파일러는 자바를 가지고 작성한 자바 소스 코드를 자바 가상 머신이 이해할 수 있는 자바 바이트 코드로 변환합니다.

: 자바 컴파일러는 자바를 설치하면 javac.exe라는 실행 파일 형태로 설치됩니다.
```

<br>

### Q. 자바 소스코드 -> 바이트 코드로 변환되고 이를 JVM에서 읽는 과정은?

### <자바 가상 머신의 구성> 

1. 자바 인터프리터(interpreter)

>: 자바 컴파일러에 의해 변환된 자바 바이트 코드를 읽고 해석하는 역할을 하는 것이 자바 인터프리터(interpreter)입니다.

2. 클래스 로더(class loader)

>: 동적으로 클래스를 로딩해주는 역할을 하는 것이 바로 클래스 로더(class loader)입니다.

3. JIT 컴파일러(Just-In-Time compiler)

>: JIT 컴파일러(Just-In-Time compiler)란 프로그램이 실행 중인 런타임에 실제 기계어로 변환해 주는 컴파일러를 의미합니다.

>: 동적 번역(dynamic translation)이라고도 불리는 이 기법은 프로그램의 실행 속도를 향상시키기 위해 개발되었습니다.

>: 즉, JIT 컴파일러는 자바 컴파일러가 생성한 자바 바이트 코드를 런타임에 바로 기계어로 변환하는 데 사용합니다.

4. 가비지 컬렉터(garbage collector)

>: 자바 가상 머신은 가비지 컬렉터(garbage collector)를 이용하여 더는 사용하지 않는 메모리를 자동으로 회수해 줍니다.

>: 따라서 개발자가 따로 메모리를 관리하지 않아도 되므로, 더욱 손쉽게 프로그래밍을 할 수 있도록 도와줍니다.


<br>

### <JVM 프로세스>

1) 작성한 자바 소스(.java)를 자바 컴파일러(javac)를 통해 자바 바이트 코드(.class)로 컴파일 합니다. 

2) 컴파일 된 바이트 코드를 JVM의 클래스 로더에게 전달한다.

3) JVM의 클래스 로더는 동적 로딩을 통해 필요한 클래스들을 로딩 및 링크하여 런타임 데이터 영역 (Runtime Data Area), 즉 JVM의 메모리 영역에 올립니다. 

4) 실행엔진( Execution Engine)은 JVM 메모리에 올라온 바이트 코드들을 명령어 단위로 하나씩 가져와서 실행합니다. 이때, 실행엔진은 2가지 방식으로 동작할 수 있습니다.

   - 자바 인터프리터( Java Interpreter )

   - JIT 컴파일러( Just In Time Compiler)