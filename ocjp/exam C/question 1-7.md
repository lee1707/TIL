# Today I learned
OCJP-Exam C, question 1-7


# QUESTION 1
``` 
Given: import java.util.Date; 
import java.text.DateFormat; 
21. DateFormat df; 
22. Date date = new Date(); 
23.//input code here
24. String s = df.format(date); 
```
=> `df = DateFormat.getInstance(); `

# QUESTION 3
```
import java.io.*; 
public class Forest implements Serializable {    
  private Tree tree = new Tree();    
  public static void main(String [] args) {        
    Forest f = new Forest();       
      try {            
        FileOutputStream fs = new FileOutputStream("Forest.ser");            
        ObjectOutputStream os = new ObjectOutputStream(fs);            
        os.writeObject(f); os.close();        
      } catch (Exception ex) { ex.printStackTrace(); }    
  } 
} 
class Tree { } 
```
=>An exception is thrown at runtime.<br><br>

* `serializable`자체는 아무것도 구현을 안해줘도 됨
serialize는 메모리에 있는 객체를 string으로 뺄 수 있게 됨<br>
forest는 serializable, tree는 serializable이 아님. java 8: stream은 그냥 stream<br>
여기나오는 스트림은 inputstream, outputstream임.
file에 출력하고 입력하기 위한 stream.

* **`strem`** 데이터가 왔다갔다하기 위한 흐름, 기본단위는 byte.
이걸 감싸서 문자 단위로 할수도 있음<br>
writer나 reader로 할수 있음
objectoutputstream은 그 위에 더 감싼것(decorator)

* `objectoutputstream`은 객체를 출력하는 역할을 여기서 하게 되는데
여기서 **읽고 쓰기 위해서는 그 객체가 serializable을 implements해야.**
객체 안에 있는 것도 다 출력하는데 **tree가 serializable을 구현하지 않기에 안됨**

* **제대로 되면** 이 파일에 이 객체의 내용이 저장되어 있음<br>
json도 serialize(직렬화)<br>
순서를 맞추는게 serialize<br>
읽어들이는게 deserialize

->컴파일때는 모르고 실행해봐야 알수 있음
<br><br>

4. console은 System.console()로 가져와야함

5. \\.은 .이라는 문자 그대로 나누겠다
space가 하나일수도 있고 여러개일수도 있다 => s*

6. type casting을 해도 자기거의 원래 super를 호출함

7. public class MultiCalc extends SImpleCalc에
 calculate()는 value의 기본값이 0이니까 그냥 -3이됨

