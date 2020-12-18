enemy 개선하기
=======================
장애물 만나면 점프하기 플레이어 시야에서 사라지면 텔레포트 복귀하기   
---------------------------  
![6-2-1](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-1.PNG)  
* enemy를 개선해보자.  
* 지금 enemy는 날라다니던 상태에서 조정을해서 걸어다녀서 장애물이 있어도 넘어가지 못한다.
* player에게 썼던 코드들을 살짝 수정해서 enemy도 장애물들을 넘어다니게 만들어주자.  
---------------------------------------------------    
![6-2-2](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-2.PNG)  
* player에게 넣어 줬던 것처럼 enemy에게도 foot을 넣어주고  
enemy는 우리가 보고 조작하는게 아니므로 eye도 넣어주자.  
---------------------------------------------------   
![6-2-3](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-3.PNG)  
* 땅바닥 체크말고도 눈앞에 뭐있는지 체크할 요소들을 추가해준다.  
---------------------------------------------------    
![6-2-4](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-4.PNG)  
* 점프 코드를 짜준다. 발이 바닥에 닿아있고, 눈앞에 벽이있으면 점프한다.  
---------------------------------------------------    
![6-2-5](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-5.PNG)  
* 실행해보면 눈앞에 벽이 있으면 바로 점프해서 뛰어넘고 진행한다.  
---------------------------------------------------    
![6-2-6](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-6.PNG)  
* 지금 enemy의 target이 player랑 waypoint일때의 차이점이 없어서 enemy가 그냥 걸어가는건지 아니면 날 잡으러 오는지 알 방법이 없다.  
* target이 player일때 바로 알 수 있는 방법을 생각해보자.  
---------------------------------------------------    
![6-2-7](https://github.com/isp829/HU/blob/master/images/lecutre6/6-2/6-2-7.PNG)  
* enemy의 target이 player이면 머리위에 느낌표가 뜨도록 만들어보자.  
---------------------------------------------------    

    

    
