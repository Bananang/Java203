## 클래스와 객체
---
### 이론 요약
![클라우드스터딩-자바-클래스와-객체-요약](https://i.imgur.com/zi6B90d.png)  
  
#### 객체 지향 프로그래밍
- OOP라고 한다. 프로그램을 객체의 조립으로 만드는 방식이다.
- OOP는 프로그램의 관리/재사용/확장에 좋다.

#### 클래스 vs 객체
- 클래스는 객체를 만들기 위한 설계도이다.
- 객체의 또 다른 표현으로는 인스턴스(instance)가 있다.
- 때문에 클래스로 객체를 만드는 것을 &quot;인스턴스화&quot;라고 한다.

#### 클래스 설계 및 구현
- 클래스는 필드(상태)와 메소드(동작)로 구성된다.
- 클래스를 도식화한 것을 &quot;클래스 다이어그램&quot;이라 한다.
- 클래스 다이어그램 보고 코드를 작성할 줄 알아야 한다.
  
>### 실습 예제
  정사각형 객체의 넓이를 구하는 예.
``` java
public class SquareTest {
  public static void main(String[] args) {
    /* 1. 객체 생성 */
    Square s = new Square();
    
    /* 2. 필드 초기화(값 변경) */
    s.length = 4;
    
    /* 3. 결과 출력 */
    System.out.printf(&quot;한 변의 길이가 %d인 정사각형의 넓이: %d&quot;, s.length, s.area());
  }
}

/* 4. 정사각형 클래스 구현 */
class Square {
  int length; // 길이
  
  // 넓이 반환
  int area() {
    return length * length;
  }
}

```
                        
## 생성자
---  
### 이론 요약  
  ![클라우드스터딩-자바-생성자-요약](https://i.imgur.com/pMmmkPn.png)

#### 생성자
- 생성자는 객체를 만드는 특별한 메소드다.
- 생성자는 역할은, 객체 생성과 필드 초기화이다.

#### 생성자 특징
- 생성자는, 호출과 정의로 나뉜다.
- 생성자명은, 클래스명과 같아야 한다.
- 리턴 타입은 표기하지 않는다. (void 아님)

---
  
    
## 실습 문제    
### 01. 첫 번째 문제
Q 01. 다음을 만족하는 Grade 클래스를 작성하시오.
-  3 과목의 점수를 입력받는 Grade객체 생성
- Grade 클래스의 main() 메소드에서 Grade 객체를 생성하여 3과목의 성적을 입력 후 출력하라
```java
public static void main(String [] args) {
  // Scanner 객체 생성

  System.out.print("수학, 과학, 영어 순으로 3개의 점수 입력>>");
  int math = scanner.nextInt();
  int science = scanner.nextInt();
  int english = scanner.nextInt();
  Grade me = new Grade(math, science, english);
  System.out.println("평균은 "+me.average()); // average()는 평균을 계산하여 리턴
  
}
```
#### 출력화면
```
수학, 과학, 영어 순으로 3개의 점수 입력>>90 88 96
평균은 91
```
  
### 02. 두 번째 문제
  Q 02. 다음을 만족하는 Song 클래스를 작성하시오.
 - 노래의 제목을 나타내는 title
 - 가수를 나타내는 artist
 - 노래가 발표된 연도를 나타내는 year

```java
public class Song {
  // 매개변수로 모든 필드를 초기화 하는 생성자

  // 노래 정보를 출력하는 show 메소드

  public static void main(String[] args){
    // artist 객체 생성

    // 생성된 객체의 show 메소드 출력

  }
}
```  
#### 출력화면
 ``` java
 2021년 BTS가 부른 Butter
 ```

### 03. 세 번째 문제
  Q 03. 다음을 만족하는 Rectangle 클래스를 작성하시오.
  - int 타입의 x, y, width, height 필드
  - x, y, widht, height 값을 매개변수로 받아 필드를 초기화하는 생성자
  - int square(): 사각형 넓이 리턴
  - void show(): 사각형의 좌표와 넓이를 화면에 출력
  - boolean contains(Rectangle r): 매개변수로 받은 r이 현 사각형 안에 있으면 true 리턴
  
  ```java
  public static void main(String[] args){
    Rectangle r = new Rectangle(2, 2, 8, 7);
    Rectangle s = new Rectangle(5, 5, 6, 6);
    Rectangle t = new Rectangle(1, 1, 10, 10);

    r.show();
    System.out.println("s의 면적은" + s.square());
    if(t.contains(r)) System.out.println("t는 r을 포함합니다.");
    if(t.contains(s)) System.out.println("t는 s를 포함합니다.");
    }
  ```  

#### 출력화면
 ``` java
(2,2)에서 크기가 8x7인 사각형
s의 면적은 36
t는 r을 포함합니다.
 ```
  
    
    
### 04. 네 번째 문제
  Q 04. 다음을 만족하는 MonthSchedule 클래스를 작성하시오.  
  Month Schedule 클래스에는 Day 객체 배열과 적절한 필드, 메소드를 작성하고  
  실행 예시처럼 입력, 보기, 끝내기 등의 3개의 기능을 작성하라.  

  ```java
  class Day {
    private String work; // 하루 할 일을 나타내는 문자열
    public void set(String work) {
      this.work = work;
    }
    public void show() {
      if(work == null)
        System.out.println("없습니다.");
      else
        System.out.println(work + " 입니다.");
    }
  }
  ```
#### 출력화면
 ``` java
이번달 스케줄 관리 프로그램
할일(입력:1, 보기:2, 끝내기:3) >> 1
날짜(1~30)>> 1
할일(빈칸없이 입력)>>자바공부

할일(입력:1, 보기:2, 끝내기:3) >> 2
날짜(1~30)>> 1
1일의 할일은 자바공부입니다.

할일(입력:1, 보기:2, 끝내기:3) >> 3
프로그램을 종료합니다.
 ```
  

### 05. 다섯 번째 문제
  Q 05. 다음을 만족하는 phone 클래스를 작성하시오. 
  - 2개의 클래스 만들기(1.Phone, 2.PhoneBook)
  - name, tel 필드
  - 저장할 사람의 수를 입력받기(배열 생성)  
  *Tip 문자열 a와 b가 같은지 비교할 때 a.equals(b)로 판단

#### 출력화면
 ``` java
인원수>>3
이름과 전화번호(이름과 번호는 빈 칸없이 입력)>>홍길동 777-7777
이름과 전화번호(이름과 번호는 빈 칸없이 입력)>>김철수 888-8888
이름과 전화번호(이름과 번호는 빈 칸없이 입력)>>김영희 666-6666
저장되었습니다...
검색할 이름>>김길동
김길동 이(가) 없습니다.
검색할 이름>>김철수
김철수의 번호는 888-8888 입니다.
검색할 이름>>그만
종료되었습니다...
 ```


