# malloc       
라이브러리마다 malloc의 세부적인 구현이 다를 수 있음에 유의해야 합니다.      
이 문서에서는 malloc의 일반적인 형태를 다룰 것입니다.    
     
## malloc과 chunk    
    
     
## Linux      
      
Linux에서 구현된 malloc을 수행할 때는 하드웨어의 메모리를 할당 받기 위해 커널에 system call을 한다.     
    
이 때 사용되는 system call에는    
     
1. mmap(), munmap()    
2. brk(), sbrk()    
    
가 있다.     
