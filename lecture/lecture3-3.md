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
![A-4](https://github.com/isp829/HU/blob/master/images/lectureA/A-4.png)   
* Package Manager에서 고른 asset을 import클릭.(Package Manager가 창으로 없으면 window->Package Manager에서 불러온다.)  
------------------  
![A-5](https://github.com/isp829/HU/blob/master/images/lectureA/A-5.png)   
* 원하는 목록들을 체크해주고 import해준다.  
-------------------------------------------------------------   

[목차로](https://github.com/isp829/HU/blob/master/README.md)  
[다음](https://github.com/isp829/HU/blob/master/lecture/lecture3-1.md)  
-----------------------------
    
