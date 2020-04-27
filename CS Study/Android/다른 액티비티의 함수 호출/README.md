# 다른 액티비티의 함수 호출

다른 액티비티나 클래스에서 정의된 메서드를 호출하는 방법이다. 특정 프래그먼트 내에서 프래그먼트를 포함하는 액티비티의 메서드를 이용할 필요가 생겨 학습하게 되었다.



### 호출하고 싶은 메서드가 있는 Activity

호출하고 싶은 함수가 있는 Activity에 public static Context 변수 생성후, this 를 지정한다.

~~~java
public class MainActivity extends AppCompatActivity {
    public static Context mContext;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mContext = this;
    }
}
~~~



###  호출방법

```java
((MainActivity)MainActivity.mContext).move_music(lyricArrayList.get(position));
```



## Reference

*  https://inma.tistory.com/69 