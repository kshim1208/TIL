## get_next_line    
    
get_next_line은 open 함수를 통해 읽어온 file descripter의 데이터를 읽어 개행을 기준으로 한 줄 씩 출력하는 함수이다.    
    
해당 함수를 구현하기 위해 이하 개념을 공부했다.   
    
    
1. [정적 변수][staticvarilink]

[staticvarilink]:https://github.com/kshim1208/TIL/blob/main/42Courses/get_next_line/static%20variable/README.md
2. 유닉스의 파일 체계
  * [파일 디스크립터][FD]

[FD]:https://github.com/kshim1208/TIL/tree/main/42Courses/Unix%20File%20System/File%20Descriptor
  * [커널 스페이스와 유저 스페이스][KUSPACE]

[KUSPACE]:https://github.com/kshim1208/TIL/tree/main/42Courses/%EB%B6%84%EB%A5%98%20%EC%95%88%EB%90%A8/Kernel%20&%20User%20Space
3. [stack, heap overflow][SHOF]

[SHOF]:https://github.com/kshim1208/TIL/tree/main/42Courses/%EB%B6%84%EB%A5%98%20%EC%95%88%EB%90%A8/Stack%20&%20Heap%20Overflow
    
-----
</br>
#### 과제 수행 중 발생한 의문  

  
### read 함수를 실행하면 커널에서 무슨 일이 생기는가?  
  
  우선 open 함수를 실행하면 kernel에서 입력된 파일을 읽어 File Descriptor를 부여하고, 관련된 메타 데이터를 저장하는 File Descriptor Table을 만든다.  
    
  이 File Descriptor Table에는 해당 FD의 현재 상태에 관한 정보가 저장된다.  
      
  read 함수를 실행하면 주어진 버퍼 크기만큼 FD가 가리키는 파일을 읽는데, 지금 어디까지 읽었는지를 나타내는 offset 값이 FD Table의 메타 데이터에 저장된다.

  이로 인해 read 함수를 도중까지만 읽다가 해당 read 함수를 나중에 다시 호출해도 현재 FD에서 파일을 어디까지 읽었는지 알 수 있는 것이다.  
    
  또한 이 사실을 바탕으로 read 함수가 kernel의 데이터에 접근하는 systemcall이라는 사실을 알 수 있다.  
  </br>
  </br>
