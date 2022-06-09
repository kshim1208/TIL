# malloc()       
동적 할당을 하는 함수    
    
> ## malloc과 chunk    
>    
> 10바이트 malloc 명령을 내렸을 때 heap manager가 하는 작업 
>    
> 1. user가 수정할 수 있는 10바이트 메모리 영역을 찾는다.    
> 2. 해당 할당 메모리에 대한 메타 데이터를 생성하고, 할당 메모리 옆에 저장한다. 
> 3. 사용하는 시스템이 32비트인지 64비트인지에 따라 적절한 크기의 padding을 통해 memory alignment를 수행한다.
> (32비트에는 8바이트, 64비트에는 16바이트)     
> 4. 이렇게 할당된 메모리 영역을 하나로 묶어 chunk라는 단위로 사용한다.    
>    
> 이렇게 할당된 chunk의 메타 데이터에는 할당된 메모리의 크기, 이전, 이후 chunk를 가리키는 포인터가 저장되어있다.    
>     
> ## free와 bin    
>          
> free 함수를 통해 할당된 메모리를 해제할 경우, malloc으로 생성된 chunk의 메타 데이터를 가지고 free bins를 생성하게 된다.    
> free bins는 연결 리스트로, 할당된 메모리가 free될 때마다 리스트에 요소가 추가되도록 구성되어 있다.     
>     
> free bins의 chunk는 연결 리스트의 요소이므로 이전, 이후 요소의 포인터에 대한 데이터를 가지고 있고, 이에 더해 할당되었던 메모리의 크기, mmap 할당인지 여부(heap alloc이 아니라고 함/추가 필요/) 등의 정보도 포함한다.
>     
>    
> free chunk의 정보를 토대로, user가 다시 할당을 시도할 때 kernel에 대한 systemcall 없이도 메모리를 신속하게 할당 받을 수 있다.    
>         
> 우선 malloc으로 요청된 메모리의 크기와 동일한 크기를 지닌 요소 있는지 bins 리스트를 순회하며 확인한다.     
> 만약, bins 리스트에 해당하는 요소가 존재한다면 heap manager는 해당 chunk를 우선적으로 할당하게 된다.    
> 이 경우, systemcall 없이도 heap 메모리 할당이 이루어진다.    
>
> 그리고 해당하는 chunk가 없는 경우에는 kernel에 systemcall을 요청하게 된다.     
>    
>     
## Linux에서의 동적 할당  /작성 중/  
      
Linux에서 구현된 동적 할당을 통해 heap 영역에 메모리를 할당할 때는 커널에 system call을 한다.     
    
이 때 사용되는 system call에는    
     
1. mmap(), munmap()    
2. brk(), sbrk()    
    
가 있다.     


-------------      
#### 참고한 글
1. https://azeria-labs.com/heap-exploitation-part-1-understanding-the-glibc-heap-implementation/
