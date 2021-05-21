#  Exceptions Demo

##### Without Exception
```java
package in.naresh;

public class TestRuntimeException {

	public static void main(String[] args) {

		String ageStr = "14";
		
		int age = Integer.parseInt(ageStr);
		
		System.out.println(age);
		
	}

}
```

#####  Exception 1: RuntimeException Category = >Invalid Input .. Exception will get raised

```java
package in.naresh;

public class TestRuntimeException {

	public static void main(String[] args) {

		String ageStr = "f14";
		
		int age = Integer.parseInt(ageStr);
		
		System.out.println(age);
		
	}

}

```

```java
Exception in thread "main" java.lang.NumberFormatException: For input string: "f14"
	at java.base/java.lang.NumberFormatException.forInputString(NumberFormatException.java:68)
	at java.base/java.lang.Integer.parseInt(Integer.java:652)
	at java.base/java.lang.Integer.parseInt(Integer.java:770)
	at in.naresh.TestRuntimeException.main(TestRuntimeException.java:9)

```

###### Explain NumberFormatException
```java
public class NumberFormatException extends IllegalArgumentException { }
public class IllegalArgumentException extends RuntimeException {}
public class RuntimeException extends Exception
```

##### Do we need to add try/catch or not ?
* IF YOU ARE GOING TO GET EXCEPTIONS which extends RuntimeException ( Compiler will not force you to add try/catch or declare exception )


##### Exception 2: Checked Exception
```java
package in.naresh;

public class TestException {

	public static void main(String[] args) {
		
		
		//Exceptions which extend Exception class are called checked Exceptions
		//Compiler will force to handle the exception 
		//ClassNotFoundException extends... Exception
		
		try {
			Class.forName("com.postgresql.Driver");
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}

}
```
<img width="506" alt="exception" src="https://user-images.githubusercontent.com/2763774/119126081-3092a900-ba50-11eb-80aa-ab362479b4b1.png">



##### Runtime Exception 2:

```java
package in.naresh;

public class TestDivision {

	public static void main(String[] args) {
		
		
		int a  = 10;
		int b = 0;
		
		int c  = a/b;
		System.out.println(c);
	}
	//java.lang.ArithmeticException extends RuntimeException
}

```

```
Exception in thread "main" java.lang.ArithmeticException: / by zero
	at in.naresh.TestDivision.main(TestDivision.java:11)

```

#### Exception 3:
```java
package in.naresh;

public class TestDivision {

	public static void main(String[] args) {
		
		
		int percentage = 0;
		
		int totalMarks  = 10;
		int noOfSubjects = 0;
		try {
			
			percentage = totalMarks/noOfSubjects; // Possibility of Exception
			System.out.println(percentage);
		} catch (Exception e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		if(percentage > 80) {
			System.out.println("Grade A");
		}
		else {
			System.out.println("Grade B");
		}
		
	}
	//java.lang.ArithmeticException extends RuntimeException
}

```


##### Validation

```java
package in.naresh;

public class GradeValidator {

	public static void validate(int totalMarks, int noOfSubjects) {
		
		if(noOfSubjects <=0) {
			throw new IllegalArgumentException("Invalid no of subjects");
		}
	}
}
```

```java
package in.naresh;

public class GradeValidator {

	public static void validate(int totalMarks, int noOfSubjects) throws Exception {
		
		if(noOfSubjects <=0) {
			throw new Exception("Invalid no of subjects");
		}
	}
}

```
<img width="551" alt="validation_exception" src="https://user-images.githubusercontent.com/2763774/119129240-486c2c00-ba54-11eb-9a31-1a00f88867db.png">

```
```
