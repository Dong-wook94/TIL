# Cluster 모듈

- node.js에서 병렬처리를 위해 제공되는 모듈이다.
- 작업 하나의 단위를 worker 라고 부른다.
- cluster 모듈 생성 후 fork 메서드를 호출하면 worker 하나가 생성되며 필요한 만큼 worker를 생성해 병렬 처리를 하면된다
- 보통 cpu 코어의 개수 만큼 worker를 발생시켜 병렬처리를 한다.