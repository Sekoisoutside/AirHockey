using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.EventSystems;

public class GoalArea : MonoBehaviour
{
    public EventTrigger.TriggerEvent scoreTrigger;
    // Start is called before the first frame update
    void Start()
    {

    }
    public void OnCollisionEnter2D(Collision2D collision)
    {
        bouncy puck = collision.gameObject.GetComponent<bouncy>();
        if (puck != null)
        {
            BaseEventData eventData = new BaseEventData(EventSystem.current);
            this.scoreTrigger.Invoke(eventData);
        }
        
        
    }
}