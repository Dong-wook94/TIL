# Sort 정리

## Bubble Sort

* stable sort

* 매번 연속된 두개의 인덱스를 비교하여 정한 기준의 값을 뒤로 넘겨 정렬하는 방법.
  오름차순일 경우 비교시 큰값이 뒤로 이동. 

* 시간복잡도 O(n^2)

* ~~~c
  void bubbleSort(vector<int> v){
      for(int i=0; i<v.size()-1;i++){
          if(v[j-1]>v[j])
              swap(v[j-1],v[j]);
      }
  }
  ~~~

## Selection Sort

* 시간복잡도 O(n^2)
* unstable sort

~~~c
void selectionSort(vector<int> v){
	for(int i=0; i<v.size();i++){
        int tmp = i;
        for(int j=i+1;j<v.size();j++){
            if(v[tmp]>=v[j]) tmp = j;
        }
        swap(v[i],v[tmp]);	
    }
}
~~~



## Insertion Sort

* stable sort

* 기본 아이디어 : 현재 위치에서, 그 이하의 배열드을 비교하여 자신이 들어갈 위치를찾아, 그 위치에 삽입하는 배열 알고리즘 이다.

* 시간복잡도 : O(n^2)

  ~~~ c
  void insertionSort(vector<int>v){
      for(int i=1; i<v.size();i++){//1씩 증가하며 비교할 숫자 
          int key = v[i], j= i-1; //i번째 숫자가 key 그 바로아래부터 비교시작
          while(j>=0 && key < v[j]){ //비교숫자가 key보다 크거나 같거나 0보다 작을때 까지 비교
              swap(v[j], v[j+1]);//key가 비교숫자보다 작거나 인덱스가 0보다 크거나같을때
              j--;//감소
          }
          v[j+1] = key;
      }
  }
  ~~~

  

## Heap Sort

* unstable sort
* min heap, max heap을 구성해 정렬하는 방법. 내림차순 정렬을 위해서는 max heap을 이용하고 오름차순 정렬을 위해서는 min heap을 이용하면 된다.



## Merge Sort

* stable sort

* ~~~c
  #include<iostream>
  
  using namespace std;
  
  int N,arr[1000001];
  int *arr2;
  
  void merge(int left, int right)
  {
  	int mid = (left + right) / 2;
  
  	int i = left;
  	int j = mid + 1;
  	int k = left;
  	while (i <= mid && j <= right)
  	{
  		if (arr[i] <= arr[j]) 
  			arr2[k++] = arr[i++]; 
  		else
  			arr2[k++] = arr[j++];
  	}
  
  	int tmp = i>mid ? j : i;
  	
  	while(k<=right) arr2[k++] = arr[tmp++];
  
  	for (int i=left;i<=right;i++) arr[i] = arr2[i];
  }
  
  void partition(int left,int right)
  {
  	int mid;
  	if (left < right)
  	{
  		mid = (left + right) / 2; 
  		partition(left, mid);
  		partition(mid + 1, right);
  		merge(left, right);
  	}
  }
  
  int main()
  {
  	scanf("%d",&N);
  	arr2 = new int[N];
  	for (int i=0;i<N;i++) scanf("%d",&arr[i]);
  
  	partition(0, N - 1);
  
  	for (int i=0;i<N;i++) printf("%d\n",arr[i]) ;
  }
  ~~~

## Quick Sort

* unstable sort

* ~~~c
  #include <stdio.h>
  #include <stdlib.h>
  #include <iostream>
  #include <time.h>
  
  using namespace std;
  
  void swap(int *a, int *b) {
  	int tmp = *a;
  	*a = *b;
  	*b = tmp;
  }
  
  int partition(int a[], int left, int right) {
  
  	srand(time(NULL));
  	// left ~ right 사이의 값을 랜덤으로 생성
  	int pivot_index = rand() % (right + 1 - left) + left;
  	int pivot_value = a[pivot_index];
  
  	swap(&a[pivot_index], &a[right]);
  
  	// store_index를 기준으로
  	// 왼쪽에 pivot_value보다 작은 값들 위치시킴
  	int store_index = left;
  	for (int i = left; i < right; i++) {
  		if (a[i] < pivot_value) {
  			swap(&a[i], &a[store_index]);
  			store_index += 1;
  		}
  	}
  
  	swap(&a[store_index], &a[right]);
  
  	return store_index;
  
  }
  
  void quick_sort(int a[], int left, int right) {
  
  	if (left < right) {
  		int p = partition(a, left, right);
  
  		quick_sort(a, left, p - 1);
  		quick_sort(a, p + 1, right);
  	}
  }
  
  int main() {
  
  	int a[5];
  	int len = sizeof(a) / sizeof(int); // 배열길이
  
  	// 랜덤함수를 위한 srand와 seed
  	srand(time(NULL));
  
  	// 배열 초기화
  	for (int i = 0; i < len; i++) {
  		// 1 ~ 50까지의 난수 생성
  		a[i] = rand() % 50 + 1;
  	}
  
  	// 정렬 전 출력
  	for (int i = 0; i < len; i++) {
  		cout << a[i] << ' ';
  	}
  	cout << '\n';
  
  	// 퀵정렬
  	quick_sort(a, 0, len - 1);
  
  	// 정렬 후 출력
  	for (int i = 0; i < len; i++) {
  		cout << a[i] << ' ';
  	}
  	cout << '\n';
  
  	return 0;
  }
  ~~~