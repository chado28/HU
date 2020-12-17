player개선하기  
=======================
점프 버퍼 점프 행어 시스템 추가 왼쪽으로 향하면 왼쪽으로 카메라 땡기기 발먼지 착지 먼지
------------------------------------
![6-1-1](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-1.PNG)
* 지금 상태에서는 스페이스바를 짧게 누르건 길게 누르건 똑같은 높이를 점프를한다.  
* 점프키를 누른 시간에 비례해 점프하게는 못만들까?
--------------------------------------------------------
![6-1-2](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-2.PNG)
![6-1-3](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-3.PNG)
* 지금 쓰고있는 rigid.AddForc말고 rigid.velocity를 사용하여 스페이스바를 누르면 위쪽으로 힘을 밭고,  
스페이스바를 띈 순간 속도가 절반이 되도록 코드를 짜보자.  
--------------------------------------------------------
![6-1-4](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-4.PNG)
* 실행해보면 점프를 살짝 누르면 아주 낮게 점프를 하는걸 볼 수 있다.
--------------------------------------------------------
![6-1-5](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-5.PNG)
* 다음은 점프 판정을 좀 넉넉하게 만들어주자.  
* 게임할때도 난 분명히 스킬을 눌렀는데 스킬이 안나가서 죽는경우가 있었을 것이다.
* 바닥에서 떨어진지 0.2초 까지는 공중에서 점프 할 수 있게 해주자.   
--------------------------------------------------------
![6-1-6](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-6.PNG)  
![6-1-7](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-7.PNG)
* jumpTime과 jumpCounter를 만들어서 점프 판정을 좀 넉넉하게 만들어주자.   
--------------------------------------------------------
![6-1-8](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-8.PNG)
* 실행해 보면 바닥에서 떨어지고 나서 빠르게 점프하면 점프가 먹힌다.  
-----------------------   
![6-1-9](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-9.PNG)
* 점프를 늦게 눌러도 작동하게 만들었으니까 점프를 좀 일찍 눌러놔서 선입력을 받게 해주자.  
* 선입력이란 게임에서 내가 스킬을 시전하고 있는 와중에 다른기술 키를 누르면  
지금 쓰고 있는 기술이 끝나자마자 다른기술이 나가는 시스템이다.
* 롤에서도 CC기 맞기 전에 스킬을 미리 선입력 해놓으면 내 캐릭터는 CC기에 맞은 상태지만 스킬이 나간다.
-----------------------   
![6-1-10](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-10.PNG)  
![6-1-11](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-11.PNG)  
![6-1-12](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-12.PNG)  
* jumBufferCount와 jumpBufferLength를 사용하여 코드를 수정해주자.  
* 이제 버튼 누른다고 점프 조건이 아니므로 코드들을 수정해주자.  
-----------------------   
![6-1-11](https://github.com/isp829/HU/blob/master/images/lecutre6/6-1/6-1-11.PNG)
* 실행해 보면 바닥에서 떨어지고 나서 빠르게 점프하면 점프가 먹힌다.  
-----------------------   


