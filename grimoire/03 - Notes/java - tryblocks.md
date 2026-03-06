---
cssclasses: pageGrid
---

# :dev_java_original:Exception’s Control | try-catch blocks
## :fab_java: Try - catch
When an exception (error) could be thrown the instruction that may cause that exception has to be enclosed in a try statement, followed by a catch statement specifying the exception that you are intending to control

```java title="try-catch"
try  {
	Scanner input = new Scanner (System.in)
    int value = input.nextInt();
    input.close();
} catch (InputMismatchException ex) {
    System.err.println("Error reading int value");
}
```

## :fab_java: try-with_Resources

Try-with_Resources blocks have the advantage of closing immediately the resources opened in the block.

```java title="Try-with_Resources"
try(Scanner input = new Scanner (System.in)){
	int value = Scanner.nextInt();
	System.out.println(value);
}catch(InputMismatchException ex){
	System.err.println("Error reading input");
}
```

## Try-catch-finally
Try-catch-Finally blocks ensure that the instructions in the `finally` statement are executed whether is an exception or not. 

```java title="Try-with_Resources"
public void divide(int a, int b) {
    try {
        int result = a / b;                          
        System.out.println("Result: " + result);
    } catch (ArithmeticException ex) {
        System.err.println("Error: division by zero");
    } finally {
        System.out.println("Operation attempted");
    }
}
```



