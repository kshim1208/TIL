# malloc()       
동적 할당을 하는 함수    
    
## malloc과 chunk    
    
     
## free와 bin    
     
     
## Linux에서의 동적 할당    
      
Linux에서 구현된 동적 할당을 통해 heap 영역에 메모리를 할당할 때는 커널에 system call을 한다.     
    
이 때 사용되는 system call에는    
     
1. mmap(), munmap()    
2. brk(), sbrk()    
    
가 있다.     


-------------      
#### 참고한 글
1. https://rninche01.tistory.com/entry/heap1-Dynamic-Memory-Allocation?category=838537
