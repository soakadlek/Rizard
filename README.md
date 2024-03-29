본 디렉토리의 파일들은 21년 06월 08일 (화) 진행되었던 컴퓨터공학 창의 설계 수업에서 기말과제로써 제작된 파일들입니다.
------
본 파일에서는 다음의 파일들의 사용방법에 관해 설명하기 위해 쓰였습니다.
------
-Incoding.c     
-Decoding.c     
-adversary.out     

**파일 내용 설명**     
    
◎Incoding.c: test_sample1.txt 등의 약속된 형식이 갖춰진 txt 파일을 압축하고 변조로부터 복원하기 위해 규칙에 따라 bin 파일로 변환하는 코드가 포함된 파일입니다.

◎adversary.out: Incoding.c로 변환 및 압축된 bin 파일의 지정한 개수만큼 무작위 위치의 문자아스키코드값을 무작위 값으로 변환한다.

◎Decoding.c: adversary.out을 통해 변조된 파일에서 변조된 값들을 본래 Incoding.c 파일로 압축할 당시의 원본 파일과 같이 복원함과 동시에 압축된 내용 또한 원본 파일과 같이 압축 해제한다.

**사용 방법**     
* encoder.out 프로그램을 만들어 다음과 같이 실행

→ ./encoder.out test1.txt encoded_data1

→ 실행결과 자체 프로토콜로 인코딩 된 데이터파일 encoded_data1 가 생성

* adversary.out 프로그램으로 encoded_data1 파일 조작

→ ./adversary.out encoded_data1 4

→ 마지막의 숫자 4는 4군데를 수정 한다는 의미

* decoder.out 프로그램을 만들어 다음과 같이 실행

→ ./decoder.out encoded_data1.modified result1.txt

→ 최종 결과파일: result1.txt

* vimdiff를 이용하여 바이트 비교

→ vimdiff test1.txt result1.txt
