

## Implementing Queue Using Array

Reference: [http://www.geeksforgeeks.org/queue-set-1introduction-and-array-implementation/](http://www.geeksforgeeks.org/queue-set-1introduction-and-array-implementation/)

```java

/*
 * [,0,]
    | 
 */

class Queue {
  int front;
  int end;
  int size;
  T[] queue;
  public Queue(int size){
    this.size = size;
    front = -1;
    end = -1;
    queue = new Object[size];

  }

  public boolean isempty(){
    return front == end;
  }

  public int increment(int index){
    return (index + 1)%size;
  }
  public boolean isFull(){
    return (front - end == 1) || (end - front == size);
  }
  public void enQueue(T value){
    if(isFull())
      throw new Exception;
    else{
      increment(end);
      queue[end] = value;
    } 
  }

  public T deQueue(){
    T value = null;
    if(isempty())
      throw new Exception
    else{
      value = queue[front];
      increment(front);
    }
    return value;

  }

  public static void main(String[] args) {
    ArrayList<String> strings = new ArrayList<String>();
    strings.add("Hello, World!");
    strings.add("Welcome to CoderPad.");
    strings.add("This pad is running Java 8.");

    for (String string : strings) {
      System.out.println(string);
    }
  }
}
```



