특수 발판들 만들기  
=======================
![4-1-1](https://github.com/isp829/HU/blob/master/images/lecture4/4-1-1.jpg)  
* 맵도 만들었고 플레이어도 만들었고 적도 만들었으면 이제 발판들을 만들자.
* 지금까지 했던 게임들의 발판을 참고해도 좋고 자기만의 아이디어가 있으면 구현해 보자.    
* 밟고있으면 점프력이 벽하는 발판들과 이동속도가 변하는 발판들을 구상해보자.  
------------------------------------ 
![4-1-2](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-2.png)
* 코드에서 바닥을 밟고 있으면 이니까 OnCollisionStay2D를 사용해서 조건들을 달아주자.  
---------------------------  
![4-1-3](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-3.png)  
* 이런 종류의 게임에서 항상 나오는 한번 밟으면 사라지는 바닥도  
Destroy(Object,time)을 사용하여 몇초후에 사라지게 만들어보자.  
---------------------------  
![4-1-4](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-4.png)  
* 적당히 애니메이션도 적용하여 사라지는게 눈에 보이게 하자.  
-----------------------  
```
```
------------------------------------------
```
```
* 각각 player에 들어가는 코드 수정본과 새로만든 부서지는 발판의 코드들이다.
--------------------------------
![4-1-5](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-5.PNG)   
* 이 외에도 다양하게 만들어보자.  
--------------------------------
[목차로](https://github.com/isp829/HU/blob/master/README.md)  
[다음](https://github.com/isp829/HU/blob/master/lecture/lecture6-1.md)  
-----------------------------

    
