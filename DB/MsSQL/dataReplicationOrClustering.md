DBMS에서 데이터를 공유하는 방법(확장을 위해서는 DBMS 설정 파일을 미리 빼놔야함)<br>
replication: Master와 Slave를 지정한다. slave는 마스터에게 가서 계속 replication를 한다. 리플리케이션은 한명이 노트정리하고 나머지가 복사하는 것.<br>
cluster : 클러스터는 다같이 노트정리를 같이 하고 빠진부분만 채워넣는 것. DBMS앞단에서 클러스터가 DB에 각각 분배를 해줌. DBMS끼리는 계속 너도 그거 받았어?하고 확인함.
