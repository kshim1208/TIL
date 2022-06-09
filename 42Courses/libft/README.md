# libft, 나만의 정적 라이브러리  
la piscine 과정 동안 c언어를 사용하여 기존 c standard library에 정의된 함수, 혹은 c에는 없지만 다른 언어에는 존재하는 함수를 구현하는 과제를 수행했다.  

libft 과제는 이러한 함수들을 이용하여 정적 라이브러리를 만드는 과제이고, 이하 지식들을 필요로 했기에 공부했다.  
  
### 과제 해결을 위해 공부한 것들   
> 1. [library][librarylink]   
>    
> [librarylink]:https://github.com/kshim1208/TIL/blob/main/42Courses/libft/library/README.md   
>   
> 2. [makefile][makefilelink]   
>    
> [makefilelink]:https://github.com/kshim1208/TIL/tree/main/42Courses/libft/makefile/README.md    
>
>    
### 그 외 함수 작성 과정에서 알게 된 것들   
> 1. [dangling pointer][danglingpointerlink]   
>      
>[danglingpointerlink]:https://github.com/kshim1208/TIL/tree/main/42Courses/libft/dangling%20pointer/README.md    
>     
> 2. [double free][doublefreelink]    
>   
>[doublefreelink]:https://github.com/kshim1208/TIL/blob/main/42Courses/libft/double%20free/README.md    
>    
>    
#### libft 작성 중 발생했던 문제와 대응     
     
##### 이중 포인터를 사용하는 이유    
포인터는 데이터를 가리키는 주소를 저장하는 변수이고, Asterisk(* )를 붙여 포인터에 저장된 주소가 가리키는 값에 접근할 수 있다.     
그런데 우리가 포인터 변수를 사용하다보면, 포인터가 가리키는 값이 아닌 포인터 그 자체의 값을 변경해야하는 상황이 발생할 수 있다.    
    
내 경우, 일방향 연결 리스트를 구현하는 과정에서 이를 이해할 수 있었다.    

일방향 연결 리스트를 사용하려면 리스트의 첫 노드를 가리키는 변수를 잘 관리해야한다.    
첫 노드를 기점으로 순회를 통해 리스트 전체에 접근할 수 있기 때문이다.    
    
여기서 연결 리스트의 첫 노드가 바뀌었다고 가정해보자.    
    
    t_list *list;
     
    ft_lstaddfront(&list, ft_listnew()); 
    // ft_lstaddfront가 list라는 연결 리스트의 첫 노드를 가리키는 포인터의 '주소' 를 인자로 받음. 
    
    
이 경우, 첫 노드의 포인터를 바꾸어야 새로 만들어진 노드가 연결 리스트의 첫 노드가 될 수 있을 것이다.
따라서 포인터의 주소 값을 바꾸어야한다.    
    
그런데, 함수에 인자로 전해진 변수는 스택에서 새롭게 생성된 변수이므로 그냥 같은 포인터를 인자로 주어 변경해도 첫 노드를 변경할 수는 없다.    
  
    만약 ft_lstaddfront(list, ...); 였다면,
    
    t_list *list; // 접근하면 값은 A, 포인터 자체의 주소는 a.  
    ft_lstaddfront의 첫 번째 인자인 list; // 값은 A, 주소는 b
    
    
 
