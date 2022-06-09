## File Descriptor    
  
Unix에서는 모든 것이 파일을 통해 표현되고, 다루어진다.   
  
이는 프로세스에서 사용하는 모든 데이터에도 적용된다.
  
유저가 프로그램을 실행하면, user space에 프로세스가 생성되며 kernel space에 process table을 만든다. 
    
     User Space         | Kernel Space
                        |
                        | Process Table
     Process 01         |  Process 01 
                        |   
                        |
  
기본적으로 0, 1, 2는 각각 표준입력, 표준출력, 표준에러에 할당된다.  
process01에서 open 함수를 사용하여 파일을 열 경우, 3이상의 새로운 fd가 부여된다.  
    
       User Space       | Kernel Space
                        |
                        | Process Table         FD Table
     Process 01         |  Process 01 
      open(hi.txt,RO)   |     FD3         ->      FD3
                        |                        offset
                        |                        read_only
                        |

새로운 FD가 부여될 때, 해당 FD의 메타 데이터를 저장하는 메모리 영역이 생기고, 이를 FD Table의 형식으로 묶는다.  
  
FD Table에는 현재 파일을 어디까지 읽었는지, 파일의 읽기, 쓰기 권한 등이 저장된다.  
  
