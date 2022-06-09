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
3. stack, heap overflow
    
    
#### 과제 수행 중 발생한 의문

read 함수, 지금 어디까지 읽었는지는 어떻게 알 수 있는거지?    
