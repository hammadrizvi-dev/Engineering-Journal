# OOPS Unit 3 - Exception Handling and Multithreading

---

## 1. Exception Handling

An exception is an abnormal condition that occurs at runtime and disrupts the normal flow of a program.

Exception handling is a mechanism used to handle runtime errors so that the normal flow of the application can be maintained.

---

## Benefits of Exception Handling

* Separates error handling code from normal code
* Maintains normal program flow
* Allows error propagation through call stack
* Helps in grouping and handling different error types

---

## 2. Types of Exceptions

### Checked Exception

* Checked at compile time
* Must be handled by programmer
* Example: IOException, SQLException

---

### Unchecked Exception

* Not checked at compile time
* Occurs at runtime
* Example: ArithmeticException, NullPointerException

---

## 3. Keywords in Exception Handling

---

### try Block

* Used to enclose code that may generate exception

---

### catch Block

* Handles exception thrown by try block

---

### finally Block

* Always executes whether exception occurs or not
* Used for cleanup (closing files, database connections)

---

### throw Keyword

* Used to explicitly throw an exception

---

### throws Keyword

* Used to declare exceptions in method signature

---

## 4. throw vs throws

| Feature  | throw                      | throws              |
| -------- | -------------------------- | ------------------- |
| Purpose  | Explicitly throw exception | Declare exception   |
| Location | Inside method              | Method signature    |
| Usage    | Single exception           | Multiple exceptions |
| Type     | Mostly unchecked           | Mostly checked      |

---

## 5. Example (Exception Handling)

```java id="8lq2a9"
public class ExceptionDemo {
    static void checkAge(int age) {
        if (age < 18) {
            throw new ArithmeticException("Access denied");
        } else {
            System.out.println("Access granted");
        }
    }

    public static void main(String[] args) {
        try {
            int a = 10;
            int b = 0;
            int c = a / b;
        } catch (ArithmeticException e) {
            System.out.println("Error: Divide by zero");
        } finally {
            System.out.println("Finally block executed");
        }
    }
}
```

---

## 6. Multithreading

Multithreading is a process of executing multiple threads simultaneously to achieve maximum CPU utilization.

---

## 7. Thread

A thread is a lightweight sub-process and the smallest unit of execution.

---

## 8. Process vs Thread

| Feature       | Process         | Thread        |
| ------------- | --------------- | ------------- |
| Nature        | Heavyweight     | Lightweight   |
| Memory        | Separate memory | Shared memory |
| Creation Time | More            | Less          |
| Switching     | Slow            | Fast          |
| Dependency    | Independent     | Dependent     |

---

## 9. Thread Life Cycle

1. New – Thread created
2. Runnable – Ready to run
3. Running – Executing
4. Blocked/Waiting – Waiting for resource
5. Terminated – Execution finished

---

## 10. Creating Threads in Java

---

### Method 1: Extending Thread Class

```java id="j4g9u1"
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread running");
    }
}
```

---

### Method 2: Implementing Runnable Interface

```java id="7s0l3k"
class MyWorker implements Runnable {
    public void run() {
        System.out.println("Child thread running");
    }
}
```

---

## 11. Thread Example

```java id="4gk2pf"
public class ThreadDemo {
    public static void main(String[] args) {
        MyWorker worker = new MyWorker();
        Thread t1 = new Thread(worker);

        t1.start();

        System.out.println("Main thread running");
    }
}
```

---

## 12. Thread Priority

* Each thread has priority (1 to 10)

### Constants:

* Thread.MIN_PRIORITY = 1
* Thread.NORM_PRIORITY = 5
* Thread.MAX_PRIORITY = 10

---

## 13. Synchronization

Synchronization is used to control access of multiple threads to shared resources.

---

### Key Points:

* Prevents data inconsistency
* Uses lock mechanism
* Only one thread can access synchronized method at a time

---

### Example:

```java id="x1c9dw"
class Table {
    synchronized void printTable(int n) {
        for (int i = 1; i <= 5; i++) {
            System.out.println(n * i);
            try {
                Thread.sleep(500);
            } catch (Exception e) {
                System.out.println(e);
            }
        }
    }
}
```

---

## Summary

* Exception handling manages runtime errors
* try-catch-finally is core mechanism
* throw and throws are important keywords
* Multithreading improves performance
* Threads share memory and execute concurrently
* Synchronization prevents conflicts

---
