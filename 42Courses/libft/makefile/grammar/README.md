### 자동 변수

* $@ Target의 이름   
* $* Target의 이름에서 확장자 제외
* $^ 현재 Target이 의존하는 대상들 목록
* $? 현재 Target이 의존하는 대상 중 수정된 것들의 목록
* $< 첫 번째 전제 조건의 파일 이름
* $? Target 파일보다 최근에 수정된 파일 이름
  
</br>
  
### 쓸 만한 문법
  
* $(addprefix 접두사, 텍스트)
    
    $(addprefix old_, main test)
    => old_main old_test
    
  
* $(addsuffix 접미사, 텍스트)
    
    $(addsuffix .c, ft_split ft_strtrim) 
     => ft_split.c ft_strtrim.c
  
*
