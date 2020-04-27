# 자바 스트림

> 스트림이란 **자료의 입출력을 도와주는 중간매개체**

데이터를 받고 출력하는 작업을 도와주는 중간 역할을 스트림이라고 한다.
하지만 스트림은 **단방향** 이라서 입출력 두가지를 모두 하기위해서는 2개의 스트림(입/출력 스트림)이 필요하다.

* **입력스트림** : 데이터를 먼저 스트림으로 읽어드린다. 그리고 스트림에 존재하는 데이터를 하나씩 읽어 들일 수 있다.

* **출력스트림** : 출력스트림으로 데이터를 보낸다. 출력스트림에 보낸 데이터를 비워버린다. 그렇게 되면 출력


## 겪었던 이슈
> src 가 사라지면 받아올 데이터가 없는 스트림만 남을 뿐이다. 스트림을 빨대와 같이 생각하면 편리하다. 그저 빈빨대와 같다.
 
 어플리케이션에서 서버에 있는 파일을 다운로드 받기위해 
~~~
InputStream in = channelSftp.get("받아올 서버의 파일 경로");
~~~
인풋스트림으로 서버에 존재하는 파일을 받아왔다. 그리고 나서는 해당 인풋스트림을 다운로드를 진행하는 액티비티로 반환하였다. 하지만 **반환되어진 인풋스트림에는 아무런 데이터가 존재하지 않았다**.

반환이 되어진 해당 액티비티의 메서드는 sftp 통신이 불가능하며 서버와 연결하던 세션이 끊어져 인풋스트림은 그저 source를 잃어버린 통로였다.

그래서 인풋스트림을 반환하지않고 인풋스트림을 통해 받아온 데이터를 byte arraylist에 저장한뒤 그 Array List를 반환하여 해당데이터를 아웃풋스트림으로 받아오니 데이터가 정상적으로 출력되었다. 

Sftp를 통해 다운로드 받은 파일을 ArrayList로 반환하는 코드는 다음과 같다. 
~~~java
public ArrayList<Byte> download(final String dir, final String downloadFileName, final String path) {
        try{
            Thread downloadThread = new Thread() {
                public void run() {
                    try {
                        channelSftp.cd(dir);
                        // Download file
                        Log.d("download log","ls : "+channelSftp.ls(dir));
                        in = channelSftp.get(dir+"/"+downloadFileName); //인풋스트림으로 데이터 받아옴
                        Log.d("download log","in : "+in);

                        byteArray = new ArrayList<Byte>();

                        int len;
                        //인풋스트림의 데이터를 byteArray에 저장.
                        try {
                            while ((len = in.read(buffer)) > 0) {
                                for(int i = 0; i < len; i++)
                                    byteArray.add(buffer[i]);
                            }
                        }
                        catch (IOException ie) {
                            ie.printStackTrace();
                        }

                    } catch (SftpException e) {
                       
                        e.printStackTrace();
                    }

                }
            };
           
            try {
                downloadThread.start();
                downloadThread.join();
                Log.d("download log","리턴전 in : "+in);
                return byteArray; //반환
            } catch (InterruptedException ie) {
                ie.printStackTrace();
                Log.d("download test","에러 출력  : "+ie);
            }
        }catch (Exception e){
            e.printStackTrace();
        }
        return null;
    }
~~~

## 참고하였습니다
> [참고링크](https://elena90.tistory.com/entry/Java-%ED%8C%8C%EC%9D%BC-%EC%9E%85%EC%B6%9C%EB%A0%A5%EC%8A%A4%ED%8A%B8%EB%A6%BCInputStreamOutputStreamReaderWriter)