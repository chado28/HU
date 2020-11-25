플레이어 기본행동 만들기(움직이기 점프)  
=======================
![lecture3-1-2](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-2.png)
* player로 쓸 구체와 ground로 쓸 정육면체를 하나씩 만들어준다.  
--------------------------
![lecture3-1-3](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-3.PNG)  
* 적당한 크기로 늘리고 적당한 위치에 배정한다.  
+ 물체들의 z축 값을 같게 조절한다.
 ---------------------------------  
![lecture3-1-4](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-4.png)  
* 구체 이름은 player, 정육면체 이름은 ground로 해주고,   
 ---------------------------------  
![lecture3-1-5](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-5.png)  
* 각각 player와 ground tag를 추가해준다.
 ---------------------------------  
![lecture3-1-6](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-6.png)  
* 우리 눈에는 2D로 보이지만 사실 3D이므로 2d rigidbody말고 그냥 rigidbody를 추가해준후,  
ground의 x y z 좌표를 고정시켜준다.
 ---------------------------------  
    
