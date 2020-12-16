특수 발판들 만들기  
=======================
![4-1-1](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-1.PNG)  
* 맵도 만들었고 플레이어도 만들었고 적도 만들었으면 이제 발판들을 만들자.
* 지금까지 했던 게임들의 발판을 참고해도 좋고 자기만의 아이디어가 있으면 구현해 보자.      
------------------------------------ 
![4-1-2](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-2.png)
* 첫번째로 밟고있으면 점프력이 벽하는 발판들과 이동속도가 변하는 발판들을 구상해보자.  
---------------------------  
![4-1-3](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-3.png)  
* 코드에서 바닥을 밟고 있으면 이니까 OnCollisionStay2D를 사용해서 조건들을 달아주자.  
---------------------------  
![4-1-4](https://github.com/isp829/HU/blob/master/images/lecture4/4-1/4-1-4.png)  
* 이런 종류의 게임에서 항상 나오는 한번 밟으면 사라지는 바닥도  
Destroy(Object,time)을 사용하여 몇초후에 사라지게 만들어보자.  
-----------------------  
![4-1-5](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-4.PNG)  
* 두 지점을 순찰하는 코드를 짜보자.  
* 두개의 gameObject를 만들고 collider2D에 트리거를 넣어 OnTriggerEnter함수를 써서 지점에 도착하면 반대지점으로 가는 코드를 만들어보자.  
-------------------------------------------------  
![5-1-5](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-5.PNG)
![5-1-6](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-6.PNG)
![5-1-7](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-7.PNG)
* Vector2.MoveTowards를 사용하면 물체를 특정 지점으로 특정속도로 향하게 만들 수 있다.   
--------------------------------
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class enemy : MonoBehaviour
{
    public float enemySpeed;//걸어가는 속도     
    public Transform target;//현재 타겟 
    public Transform[] waypoint;// 순찰지점들  
    public int wayNumber;//현재 순찰 지점  
   
    void Update()
    {
        Vector2 targetV = new Vector2(target.position.x, target.position.y);
        transform.position = Vector2.MoveTowards(transform.position, targetV, enemySpeed * Time.deltaTime);
        if (target.position.x <= transform.position.x)//얼굴뒤집기
        {
            this.transform.eulerAngles = new Vector3(0, 180, 0);//향하는 방향따라 뒤집어 주기  
        }
        else
        {
            this.transform.eulerAngles = new Vector3(0, 0, 0); 
        }
    }

    void OnTriggerEnter2D(Collider2D col) 
    {
        if (col.gameObject.tag == "turnpoint") 
        {
            if (target = waypoint[wayNumber])//turnpoint도착하면 다음 위치로.
            {
                wayNumber++;
                wayNumber = wayNumber % 2;//1 2 1 2 반복
                target = waypoint[wayNumber];
            }
        }
       
    }
}

```
* 코드 전문이다. 그냥 지 말고 이걸 왜쓰는지 생각해보자.  
-------------------  
![5-1-8](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-8.PNG)
![5-1-9](https://github.com/isp829/HU/blob/master/images/lecture5/5-1/5-1-9.PNG)
* 이제 player가 일정 수준 가까워지면 target을 player로 정하는 코드를 짜보자.  
* Vector2.Distance를 쓰면 두 지점 사이의 거리를 계산할 수 있다.  
--------------------------------
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class enemy : MonoBehaviour
{
    public float enemySpeed;
    public Transform target;
    public Transform[] waypoint;
    public int wayNumber;
    public Transform player;
    public float dist;
    public float checkDist;
    
    void Update()
    {
        dist = Vector2.Distance(transform.position, player.position);
        if (dist > checkDist)
        {
            target = waypoint[wayNumber]; 
        }
        else 
        {
            target = player;
        }
        Vector2 targetV = new Vector2(target.position.x, target.position.y);
        transform.position = Vector2.MoveTowards(transform.position, targetV, enemySpeed * Time.deltaTime);
        if (target.position.x <= transform.position.x)//얼굴뒤집기
        {
            this.transform.eulerAngles = new Vector3(0, 180, 0);
        }
        else
        {
            this.transform.eulerAngles = new Vector3(0, 0, 0); 
        }
    }

    void OnTriggerEnter2D(Collider2D col) 
    {
        if (col.gameObject.tag == "turnpoint") 
        {
            Debug.Log("!!");
            if (target = waypoint[wayNumber])
            {
                wayNumber++;
                wayNumber = wayNumber % 2;
                target = waypoint[wayNumber];
            }
        }
    }
}

```
* 코드 전문이다. 
-----------------------  
[목차로](https://github.com/isp829/HU/blob/master/README.md)  
[다음](https://github.com/isp829/HU/blob/master/lecture/lecture5-1-1.md)  
-----------------------------

    
