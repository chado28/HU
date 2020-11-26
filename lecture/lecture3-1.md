플레이어 기본행동 만들기(움직이기 점프)  
=======================
![lecture3-1-2](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-2.png)
* 다운 받은 패키지에서 플레이어로 쓸 asset을 드래그 드롭해서 올려놓는다.  
--------------------------
![lecture3-1-3](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-3.PNG)  
* 드래그한 이미지의 xyz값은 모두 0으로 해준다.  
+ main camera의 z값만 -1로 해주면 Game tab에 이미지가 보일것이다.
 ---------------------------------  
```
using System.Collections;
using System.Collections.Generic;
using Unity.Mathematics;
using UnityEditor;
using UnityEngine;
using UnityEngine.SceneManagement;

public class player : MonoBehaviour

{
    public float moveSpeed = 5.0f; //플레이어 이동 속도
    public float jumpPower = 5.0f; //플레이어 점프 힘
    public Animator animator;
    public AudioSource audio;
    public AudioClip jump;


    Rigidbody2D rigid;


    float horizontal; //왼쪽, 오른쪽 방향값을 받는 변수

    public bool isground;
    public Transform groundCheck;
    public float groundRadius = 0.2f;
    public LayerMask whatIsGround;

    void oncollisionstay() { 
    }

    private void Start()
    {
        isground = false;
        rigid = GetComponent<Rigidbody2D>();
        animator = GetComponent<Animator>();
    }

    private void FixedUpdate()
    {
        

    }

    private void OnCollisionEnter2D(Collision2D col)
    {
       if (col.gameObject.tag=="spike" )
        {
            SceneManager.LoadScene("Scene1");
        }
    }

    private void OnCollsionExit2D(Collision2D col) 
    {
        
    }
    void OnTriggerEnter2D(Collider2D col)
    {
        if (col.gameObject.tag == "spike")
        {
            SceneManager.LoadScene("Scene1");
        }
        if (col.gameObject.tag == "goal")
        {
            SceneManager.LoadScene("clear");
        }
    }

    void Jump()
    {
        if (Input.GetButton("Jump")) //점프 키가 눌렸을 때
        {
            if (isground == true) //점프 중이지 않을 때
            {
                audio.PlayDelayed(0.1f);
                audio.Play();
                animator.SetBool("jump", true);
                rigid.AddForce(Vector2.up * jumpPower, ForceMode2D.Impulse); //위쪽으로 힘을 준다.
                isground = false;
                
                
            }
            else return; //점프 중일 때는 실행하지 않고 바로 return.
        }
       
    }



    void start() 
    {

    }

    void Update() 
    {
        isground = Physics2D.OverlapCircle(groundCheck.position, groundRadius, whatIsGround);
        if (isground == true)
        {
            animator.SetBool("jump", false);
        }
        Move(); //플레이어 이동
        Jump(); //점프
    }


    void Move()
    {
        horizontal = Input.GetAxis("Horizontal");

        if (horizontal != 0)
        {
            animator.SetBool("walk", true);

            if (horizontal >= 0) 
            { 
                this.transform.eulerAngles = new Vector3(0, 0, 0); 
            }

            else this.transform.eulerAngles = new Vector3(0, 180, 0);

        }
        else
        {
            animator.SetBool("walk", false);
        }

        Vector3 dir = math.abs(horizontal) * Vector3.right; //변수의 자료형을 맞추기 위해 생성한 새로운 Vector3 변수

        this.transform.Translate(dir * moveSpeed * Time.deltaTime); //오브젝트 이동 함수
    }
}
```

* 좌우 방향키로 움직이고, 점프키(스페이스바)를 누르면 점프해주는 기본적인 코드를 짜준다.
 ---------------------------------  
![lecture3-1-5](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-5.png)  
* 각각 player와 ground tag를 추가해준다.
 ---------------------------------  
![lecture3-1-6](https://github.com/isp829/HU/blob/master/images/lecture3/3-1-6.png)  
* 우리 눈에는 2D로 보이지만 사실 3D이므로 2d rigidbody말고 그냥 rigidbody를 추가해준후,  
ground의 x y z 좌표를 고정시켜준다.
 ---------------------------------  
    
