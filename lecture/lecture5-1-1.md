적 기본행동 만들어주기  
=======================
![5-1-10](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-10.PNG)  
* 실행해보면 enemy가 날라다니면서 아무것도 못하게 된다.   
* 어떻게 해야 enemy를 걸어다니게 할까?  
------------------------------------ 
![5-1-11](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-11.PNG)  
* x,y좌표 둘다 추적하는 Vector2 targetV 말고 x좌표만 추적하는 Vector2를 새로 만들어주자.  
---------------------------  
![5-1-12](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-12.PNG)  
* 실행해보면 enemy가 이제 날라다니지는 않는다.   
---------------------------  
![5-1-13](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-13.PNG)  
* 근데 실행하다보면 wayNumber 1일때 wayNumber 2에 해당되는곳으로 유인하고 거리가 멀어지면
  enemy가 wayNumber1로 가야하지만 이미 enemy 내부에 gameObject가 들어있어서 OnTriggerEnter가 발동을 안한다.  
* 어떻게 해야 이 문제를 해결 할 수 있을까?  
---------------------------  
![5-1-11](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-11.PNG)  
* 지금까지 해왔던 점프&런 게임들을 떠올려보면서 생각해보자.  
---------------------------  
![5-1-11](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-11.PNG)  
* 지금까지 해왔던 점프&런 게임들을 떠올려보면서 생각해보자.  
---------------------------  
