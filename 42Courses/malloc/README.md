# 운영체제에 따른 malloc의 구현 및 동작       
라이브러리마다 malloc의 구현이 다를 수 있음에 유의할 것.      
     
## Linux      
      
Linux에서 구현된 malloc을 수행할 때는 하드웨어의 메모리를 할당 받기 위해 커널에 system call을 한다.     
    
이 때 사용되는 system call에는    
     
1. mmap(), munmap()    
2. brk(), sbrk()    
    
가 있다.     
