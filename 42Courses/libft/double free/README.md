## double free란?    
     
한 번 free를 통해 해제한 메모리를 다시 한 번 free로 해제하였을 때 발생하는 시스템, 보안 위협을 말한다.     
     
이를 이해하기 위해서는 [malloc](https://github.com/kshim1208/TIL/blob/main/42Courses/malloc/README.md) 의 기능, 그 중에서도 bin의 개념을 알아야할 필요가 있다.    
    
      
우리가 free를 할 때, free된 메모리에 대한 chunk가 bins 리스트에 더해지게 된다.     
그리고 우리가 동일한 크기의 메모리를 다시 할당 받을 경우, systemcall을 요청하기 전에 우선 bins에 저장된 할당 이력을 확인하게 된다.     
    
     
여기서 우리가 c라는 주소를 지닌 15바이트 크기의 메모리를 2번 할당 해제했다고 가정해보자.    
     bins list의 요소 : 5a - 10b - 15c - 15c    
     
그러면 bins의 구성이 이런 형태가 될 것이다.
