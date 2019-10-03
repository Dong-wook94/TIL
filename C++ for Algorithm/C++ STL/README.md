# C++ STL


## MAP 

### Map container
* 노드기반으로 이루어져 있고 균형 이진트리 구조(레드블랙 트리로 구현되어 있다.)
* key와 value로 이루어져 있으며 이는 pair 객체로 저장
* Unique Key 
    - key는 고유한 값이므로 **중복이 불가능**하다.
    - 중복 key는 multimap에서 가능하다.
* Ordered 
    - map도 set과 마찬가지로 **삽입이 되면서 자동으로 정렬**이 된다.(default는 less/오름차순)
* 연관있는 두 값을 함께 묶어서 관리하되, 검색을 빠르게 하고싶은 경우에 사용한다.

### 기본적인 map 사용법
| 멤버함수 | 기능 | 
|--|--|
|map.size() | map 의 노드 개수를 리턴.|
|map.empty() | map의 사이즈가 0인지 아닌지를 확인. |
| map.begin() | map의 첫 번째 원소를 가리키는 iterator 리턴.|
| map.end() | map의 마지막 원소를 가리키는 iterator 리턴. |
| map[key] = value | map에 key가 key이고 value가 value인 노트 추가
| map.insert(make_pair(key,value)) | map에 key가 key이고 value가 value인 노트 추가|
| map.erase(key) | map에서 키가 key인 노드 삭제|
| map.find(key) | map에서 키가 key인 노드를 찾아, 해당 노드를 가리키는 iterator 리턴.|
| map.count(key) | map에서 키가 key인 노드의 개수를 리턴.|


### iterator 사용방법.
~~~c++
map<char,int>::iterator it;
//map전체를 순회하며 key와 value 출력
for(it = map.begin(); it != map.end(); it++)
    cout << it->first << ' ' << it->second << '\n';

//이렇게 해도 된다.
for(auto it = m.begin(); it != m.end(); it++){
		cout << "key : " << it->first << " " << "value : " << it->second << '\n';
	}

~~~

## Set

### Set Container
* key만 있는 map 혹은 정렬된 집합.(value가 없는 map이라고 생각하면 된다.)
* 특정 값에 대해 검색을 빠르게 하고싶은 경우 사용한다.

### 기본적인 Set 사용법
| 멤버함수 | 기능 | 
|--|--|
|s.size()|s의 노드 개수를 리턴|
|s.size()|s의 노드 개수를 리턴|
|s.empty()|s의 사이즈가 0인지 아닌지를 확인|
|s.begin()|s의 첫 번째 원소를 가리키는 iterator 리턴|
|s.end()|s의 마지막 원소를 가리키는 iterator 리턴|
|s.insert(k) | s에 값이 k인 노드 추가|
|s.erase(k) | s에서 값이 k인 노드 삭제
|s.find(k) | s에서 값이 k인 노드를 찾아, 해당 노드를 가리키는 iterator 리턴 (값이 k인 노드가 존재하지 않는 경우, s의 마지막 원소를 가리키는 iterator 리턴)
|s.count(k) | s에서 값이 k인 노드의 개수를 리턴

### 특정 key 삭제
~~~c++
int toErase;
scanf("%d", &toErase);
 
it = s.find(toErase);
 
//지울 원소가 존재하는 원소일 때만 지움
if(it != s.end())
    s.erase(it);
~~~
## vector

### 

### vector에서 iterator를 통한 반복 도중 요소 삭제.
~~~c++
for (vector<int>::iterator iter = v.begin(); iter == v.end();){ 
        if (iter->x==0/*조건 */){
            iter = v.erase(iter); 
        } else {
            iter++; 
        }
    }
~~~

## Reference
[C++/STL]map, set : https://sarah950716.tistory.com/6