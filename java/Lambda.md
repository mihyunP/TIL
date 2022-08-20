람다식(Lambda Expression)
함수형 프로그래밍
(매개변수) -> {실행문;}

StringConcat.java // 인터페이스
```
package lambda;

public interface StringConcat {
	
	public void makeString(String s1, String s2);
}
```

StringConcatImpl.java // 인터페이스 구현체
```
package lambda;

public class StringConcatImpl implements StringConcat{

	@Override
	public void makeString(String s1, String s2) {
		// TODO Auto-generated method stub
		System.out.println(s1+" "+s2);
	}

}
```

TestStringConcat.java
```
package lambda;

public class TestStringConcat {

	public static void main(String[] args) {
		StringConcat sImpl = new StringConcatImpl();
		sImpl.makeString("OOP:", "hello java"); // 객체 지향 프로그래밍 : 인터페이스에서 메소드 선언 -> 인터페이스impl(인터페이스에서 선언한 메소드 구현함) -> test에서 impl에서 구현한 메소드 사용
		
		StringConcat concat = (s1, s2) -> System.out.println(s1+" "+s2);
		concat.makeString("Lambda:", "hello java"); // 함수형 프로그래밍(람다식) : 인터페이스 -> test에서 인터페이스에서 선언한 메소드 람다식 구현 및 사용 
		
		
		StringConcat concat2 = new StringConcat() {
			
			@Override
			public void makeString(String s1, String s2) {
				// TODO Auto-generated method stub
				System.out.println(s1+" "+s2);
			}
		}; // 람다식 내부적 동작 원리 : 익명 객체 생성 <- 익명  함수
		concat2.makeString("AnonymousInnerClass:", "hello java");
	}

}
/*
 * 객체 지향 방식 : 메소드 여러개 구현 가능
 * 람다식, 익명 내부 클래스 : 메소드 한개씩만 구현 가능
 */
```

-----
람다식 활용 방안 : 1. 변수, 2. 매개변수, 3. 리턴값
LambdaTest.java
```
package lambda;

interface PrintString{
	void showString(String str);
}

public class LambdaTest {
	
	public static void main(String[] args) {
		
		PrintString lambdaPrint = str -> System.out.println(str);// 1. 람다식 변수로 사용
		lambdaPrint.showString("test"); 
		
		showMyString(lambdaPrint); // 2. 람다식 매개변수로 사용
		
		PrintString reStr = returnPrint(); // 3. 람다식 리턴값으로 사용
		reStr.showString("hello");
	}
	
	public static void showMyString(PrintString lambda) { // 2.
		lambda.showString("test2");
	}
	
	private static PrintString returnPrint() {
		// TODO Auto-generated method stub
		return s->System.out.println(s+" world"); // 3.
	}

}
```
