# Virtual-button-in-Unity

C# Script of Virtual Btn

using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using Vuforia;

public class vb_animation : MonoBehaviour, IVirtualButtonEventHandler
{

    public GameObject vbBtnObj;
    public Animator cubeAni;
    
    // Start is called before the first frame update
    void Start()
    {
        vbBtnObj = GameObject.Find("anibtn");
        vbBtnObj.GetComponent<VirtualButtonBehaviour>().RegisterEventHandler(this);
        cubeAni.GetComponent<Animator>();
    }

    public void OnButtonPressed(VirtualButtonBehaviour vb)
    {
        cubeAni.Play("cube_animation");
        Debug.Log("BIN Pressed");
    }

    public void OnButtonReleased(VirtualButtonBehaviour vb)
    {
        cubeAni.Play("none");
        Debug.Log("BIN Released");
    }

    // Update is called once per frame
    void Update()
    {
        
    }
}
