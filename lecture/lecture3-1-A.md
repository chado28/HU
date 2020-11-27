플레이어 애니메이션 만들기  
=======================
![lecture3-1-A-1](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-1.png)
* player에 animator asset을 추가해준다.  
--------------------------  
![lecture3-1-A-2](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-2.png)
* Project tab에서 Animator Controller도 하나 만들어준다.  
--------------------------  
![lecture3-1-A-3](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-3.PNG)
![lecture3-1-A-4](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-4.PNG)
* 애니메이션에 쓸 모션들을 드래그해서 Scene이나 Hierarchy에 올려놓는다.   
* 올려놓으면 Project에 새로운 애니메이션들과 애니메이션 컨트롤러 들이 생긴다.  
--------------------------   
![lecture3-1-A-5](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-5.png)
* Animator tab을 열어준다.   
--------------------------  
![lecture3-1-A-6](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-6.png)
* 가만히 있을때 모션을 위해서 빈 상태를 하나 만들고  
아까 만든 걷는 애니메이션과 점프 애니메이션을 넣어준다.  
--------------------------  
![lecture3-1-A-7](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-7.png)
* player가 할 수 있는 행동이 3가지 밖에 없다면 그림과 같이 될것이다.  
각각 어떤 조건을 가져야 저렇게 움직일지 생각해보자.  
--------------------------  
![lecture3-1-A-8](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-8.png)
* animator에서 상태조절을 위한 bool parameter "walk"와 "jump"를 만들어준다.  
--------------------------  
![lecture3-1-A-9](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-9.png)
* 다운 받은 패키지에서 플레이어로 쓸 asset을 드래그 드롭해서 올려놓는다.  
--------------------------  
![lecture3-1-A-10](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-10.PNG)
* 다운 받은 패키지에서 플레이어로 쓸 asset을 드래그 드롭해서 올려놓는다.  
--------------------------  
![lecture3-1-A-11](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-A/3-1-A-11.PNG)
* 다운 받은 패키지에서 플레이어로 쓸 asset을 드래그 드롭해서 올려놓는다.  
--------------------------  

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
    public bool isground;//값을 받을 bool값
    public Transform groundCheck;//player발위치
    public float groundRadius = 0.2f;//측정할 범위
    public LayerMask whatIsGround;//어떤 layer를 측정할지
    public Animator animator;//애니메이터 추가
    private void Start()
    {
        rigid = GetComponent<Rigidbody2D>();
    }
    private void FixedUpdate()
    {
        isground = Physics2D.OverlapCircle(groundCheck.position, groundRadius, whatIsGround);
        if (isground == true)
        {
            animator.SetBool("jump", false);
        }
        Move(); //플레이어 이동
        Jump(); //점프   
    }
    void Jump()
    {
        if (Input.GetButton("Jump")) //점프 키가 눌렸을 때//ground이면서 스페이스바 누르면 
        {
            if (isground == true) //점프 중이지 않을 때
            {
                animator.SetBool("jump", true);//점프하면 애니메이터 설정 jump true.
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
            animator.SetBool("walk", true);//애니메이터 설정 walk를 true.
            if (horizontal >= 0) this.transform.eulerAngles = new Vector3(0, 0, 0);
            else this.transform.eulerAngles = new Vector3(0, 180, 0);
        }
        else 
        {
            animator.SetBool("walk", false);//좌우로 안움직이면 애니메이터 설정 walk false.
        }
        Vector3 dir = math.abs(horizontal) * Vector3.right; //변수의 자료형을 맞추기 위해 생성한 새로운 Vector3 변수
        this.transform.Translate(dir * moveSpeed * Time.deltaTime); //오브젝트 이동 함수
    }
}
```
