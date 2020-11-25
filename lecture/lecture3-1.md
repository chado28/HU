플레이어 기본행동 만들기(움직이기 점프)  
=======================
![lecture3-1-2](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-2.png)
* 다운 받은 패키지에서 플레이어로 쓸 asset을 드래그 드롭해서 올려놓는다.  
--------------------------
![lecture3-1-3](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-3.PNG)  
* 드래그한 이미지의 xyz값은 모두 0으로 해준다.  
+ main camera의 z값만 -1로 해주면 Game tab에 이미지가 보일것이다.
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
    
