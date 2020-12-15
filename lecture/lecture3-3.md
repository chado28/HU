다른 물체들과 상호작용 만들기
=======================
![collision](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-1.PNG)
![trigger](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-2.PNG)  
* unity에서 물체끼리 상호작용할때 제일 많이 쓰이는 OnCollision과 OnTrigger에 대해서 알아보자.  
---------------------------------------------------  
![collision](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-1.PNG)
* OnCollision은 상호작용할 두물체에 각각 rigidbody와 collider가 필요하다.
* 물체의 면끼리 접촉하는걸로 작동한다.  
* 상태에 따라 명령어를 Enter, Stay, Exit으로 표현할 수 있다.  
--------------------------------------------------------------------------------------    
![trigger](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-2.PNG)   
* OnTrigger는 상호작용한 두물체에 collider가 필요하지만, rigidbody는 하나만 있어도 된다.  
* 면끼리 접촉뿐만 아니라 서로 겹치는것도 된다.  
* 상태에 따라 명령어를 Enter, Stay, Exit으로 표현할 수 있다.  
------------------------------------------------------------- 
![stay](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-3.PNG)
![enter](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-4.PNG)
![exit](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-5.PNG) 
* 그림과 같이 stay는 접촉하고있을때, enter는 처음 접촉할때. exit는 접촉이 떨어질때 호출된다.  
-------------------------------------------------------------    
![최적화짤](https://github.com/isp829/HU/blob/master/images/lecture3/3-3/3-3-6.png) 
* OnCollison이 물체마다 rigidbody를 사용하므로 게임내 object들이 많아질수록 OnTrigger에 비해 최적화가 안좋다.   
-------------------------------------------------------------    
![3-3-7](https://github.com/isp829/HU/blob/master/images/lectureA/A-4.png)   
* 게임에 쓸 object들을 가져와준다.  
* 밟으면 죽는 장애물과 스테이지 클리어용 포탈을 가져왔다.  
------------------  
![3-3-8](https://github.com/isp829/HU/blob/master/images/lectureA/A-5.png)   
* 각각 object에 polygon collider 2D를 넣어준다.  
-------------------------------------------------------------   
![3-3-9](https://github.com/isp829/HU/blob/master/images/lectureA/A-5.png)   
* 장애물에는 spike tag를, 포탈에는 goal tag를 해준다.  
* 계속 쓸 object들이므로 prefab해주는게 좋다.  
-------------------------------------------------------------   
[목차로](https://github.com/isp829/HU/blob/master/README.md)  
[다음](https://github.com/isp829/HU/blob/master/lecture/lecture3-1.md)  
-----------------------------
    
