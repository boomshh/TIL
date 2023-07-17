# Class
   
1. 클래스
   - 프로그램의 각 요소별 설계도
   - 코틀린에서는 class 키워드를 활용해서 클래스를 만듦
   - 클래스에는 정보(프로퍼티)와 행위(메소드)를 작성한다.
   - 보통 하나의 파일은 한 개의 클래스를 의미하지만, 하나의 파일 안에 여러 개의 클래스가 존재할 수도 있다.
   ```kotlin
   class 클래스이름 {
	    정보1
	    정보2

		 행위1
		 행위2
    }
    ```

    - data class 
        - 개발하다보면 정보(property)만 가지고 있는 클래스가 필요.
        - 기본 생성자에 1개 이상의 매개변수가 변수나 상수로 존재해야함.
        - 유용한 메소드를 자동으로 만들어준다. 
        ```
        💡
        - hashCode(): 객체를 구분하기 위한 고유값을 리턴해줘요
        - eauals(): 동일한 객체인지 비교해서 true 또는 false를 리턴해줘요
        - copy(): 현재 객체의 모든 정보를 복사해서 새로운 객체를 리턴해줘요
        - toString(): 현재 객체의 모든 정보(프로퍼티)를 예쁘게 출력해줘요
        - getXXX()/setXXX(매개변수): 변수의 값을 리턴하거나 설정해줘요  
        ```

        ```
        data class 클래스 이름 {
            정보1
            정보2
        }
        ```
    - sealed class 
        - 클래스 상속과 관련된 개념
        - 상속받을 수 있는 자식클래스들을 미리 정의 가능.
        - 무분별한 상속을 방지할 수 있어요
        - 컴파일 시점에 생성할 수 있는 자식을 알 수 있기때문에 효율적으로 다형성을 구현해요

        ```
        sealed class 부모클래스 {
	        class 자식클래스1 : 부모클래스생성자
	        class 자식클래스2 : 부모클래스생성자
        }
    
    - odject class 
        - Java의 static 대신 사용하는 키워드.
        - 프로그램을 실행하는 동시에 인스턴스함.

2. 생성자의 활용
    - 기본 생성자와 명시적 생성자가 존재.
    - 기본 생성자는 이전까지 클래스를 만들던 행위와 차이가 없음. 
    - 명시적 생성자는 주 생성자와 부 생성자로 구분할 수 있다. 
        - Kotlin 생성자의 종류 
    1. Init (주 생성자)의 사용 예시
    ```kotlin
        // init 
        fun main() {

        } ```
        // 클래스 선언부에 생성자를 명시함
    class Character(_name:String, _hairColor:String, _height:Double) {
    var name:String = ""
    var hairColor:String = ""
    var height:Double = 0.0

		// 매개변수를 직접 넘기지않음
    init {
        println("매개변수없는 생성자 실행 완료!")
    }

    fun fireBall() {
        println("파이어볼!")
    }
    fun compositing(device1:String, device2:String): String {
        var device3 = device1 + device2
        println("새로운 무기인 ${device3}입니다")
        return device3
        }
    }
    ```
   2. Constructor (부 생성자)의 사용 예시
   ```kotlin
   		fun main() {

    }
    
    class Character {
      var name:String = ""
      var hairColor:String = ""
      var height:Double = 0.0

      // 명시적 생성자 (Constructor)
      // _name, _hairColor, _height와 같이 생성자에 변수를 넘기는 경우에 사용함
      constructor(_name:String, _hairColor:String, _height:Double) {
          println("${_name}을 생성자로 넘겼어요")
          println("${_hairColor}를 생성자로 넘겼어요")
          println("${_height}를 생성자로 넘겼어요")
      }

      fun fireBall() {
          println("파이어볼!")
      }
      fun compositing(device1:String, device2:String): String {
          var device3 = device1 + device2
          println("새로운 무기인 ${device3}입니다")
          return device3
       }
     }
