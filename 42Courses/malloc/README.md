# malloc()       
동적 할당을 하는 함수    
    
> ## malloc과 chunk    
    
10바이트 malloc 명령을 내렸을 때 heap manager가 하는 작업 
    
1. user가 수정할 수 있는 10바이트 메모리 영역을 찾는다.    
2. 해당 할당 메모리에 대한 메타 데이터를 생성하고, 할당 메모리 옆에 저장한다. 
3. 사용하는 시스템이 32비트인지 64비트인지에 따라 적절한 크기의 padding을 통해 memory alignment를 수행한다.
(32비트에는 8바이트, 64비트에는 16바이트)     
4. 이렇게 할당된 메모리 영역을 하나로 묶어 chunk라는 단위로 사용한다.    
    
이렇게 할당된 chunk의 메타 데이터에는 할당된 메모리의 크기, 이전, 이후 chunk를 가리키는 포인터가 저장되어있다.
## free와 bin    
     
     
## Linux에서의 동적 할당    
      
Linux에서 구현된 동적 할당을 통해 heap 영역에 메모리를 할당할 때는 커널에 system call을 한다.     
    
이 때 사용되는 system call에는    
     
1. mmap(), munmap()    
2. brk(), sbrk()    
    
가 있다.     


-------------      
#### 참고한 글
1. https://azeria-labs.com/heap-exploitation-part-1-understanding-the-glibc-heap-implementation/
