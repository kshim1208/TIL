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
