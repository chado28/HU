기본행동 개선하기  
=======================
![lecture3-1-B-1](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-B/3-1-B-1.PNG)
* 저렇게 코드를 짜면 큰 문제가 발생하는데 player와 ground tag가 접촉하면 무조건 isground가 되어서 점프가 가능해진다.  
즉 원하지 않는 벽점프등등의 잡기술이 생긴다.  
--------------------------
![lecture3-1-B-2](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-B/3-1-B-2.jpg)  
* 어떻게 해야 저 문제를 해결할 수 있을까?  
발표해보자.  
 ---------------------------------  
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Unity.Mathematics;

public class test : MonoBehaviour
{
    public float moveSpeed = 5.0f; //플레이어 이동 속도
    public float jumpPower = 5.0f; //플레이어 점프 힘

    public Rigidbody2D rigid;

    float horizontal; //왼쪽, 오른쪽 방향값을 받는 변수

    public bool isground;

    private void Start()
    {
        rigid = GetComponent<Rigidbody2D>();
    }

    private void FixedUpdate()
    {
        Move(); //플레이어 이동
        Jump(); //점프   
    }

    private void OnCollisionEnter2D(Collision2D collision)
    {
        if (collision.gameObject.CompareTag("ground"))
        {
            isground = true;//ground에 접촉하면 isground를 true로
        }
    }


    void Jump()
    {
        if (Input.GetButton("Jump")) //점프 키가 눌렸을 때//ground이면서 스페이스바 누르면 
        {
            if (isground == true) //점프 중이지 않을 때
            {
                rigid.AddForce(Vector2.up * jumpPower, ForceMode2D.Impulse); //위쪽으로 힘을 준다.
                isground = false;
            }
            else return; //점프 중일 때는 실행하지 않고 바로 return.
        }
    }






    void Move()
    {
        horizontal = Input.GetAxis("Horizontal");

        if (horizontal != 0)
        {
            
            if (horizontal >= 0) this.transform.eulerAngles = new Vector3(0, 0, 0);

            else this.transform.eulerAngles = new Vector3(0, 180, 0);

        }
        
           
        

        Vector3 dir = math.abs(horizontal) * Vector3.right; //변수의 자료형을 맞추기 위해 생성한 새로운 Vector3 변수

        this.transform.Translate(dir * moveSpeed * Time.deltaTime); //오브젝트 이동 함수
    }
}
```

* 좌우 방향키로 움직이고, 점프키(스페이스바)를 누르면 점프해주는 기본적인 코드를 짜준다.
 ---------------------------------  
![lecture3-1-4](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-4.png)  
* 플레이어에게 rigidbody2D를 넣어주고 z축 회전을 막은다음  
 ---------------------------------  
![lecture3-1-5](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-5.png)  
* 캡슐 콜라이더를 넣고 크기를 조절해준다.  
 ---------------------------------  
![lecture3-1-6](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-6.png)
![lecture3-1-7](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-7.PNG)  
* 아까 추가한 타일맵에 ground 태그를 추가해준다.    
 ---------------------------------  
    
![lecture3-1-8](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-8.png)  
* 타일맵에도 rigidbody2d를 추가해주고 xy위치 고정, z축 고정을 해준다.   
 ---------------------------------  
 ![lecture3-1-9](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-9.PNG)  
* tilemap collider 2D도 추가해준다.     
 ---------------------------------  
 ![lecture3-1-10](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-10.PNG)  
* 실행해서 작동하나 확인해보자.    
 ---------------------------------  
        
    
