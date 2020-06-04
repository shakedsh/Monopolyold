<p dir="rtl">כדי לזהות מתי נעצרה הקוביה אחרי שהסתיימה ההטלה, ניסינו בתחילה להתשמש ב ה OnCollisionEnter, אך עד מהרה גילינו שזה לא יעיל, מפני שהקוביה ממשיכה להתגלגל גם לאחר שפגעה באדמה<p>
  
<p dir="rtl">ניסינו באמצעות מהירות הקוביה, אך היות והיא לא נעצרת גם לאחר הנפילה, השתמשנו בנוסחה הבאה, כלומר מספיק שהמהירות תהיה קטנה מ 0.1<p>

```csharp
void Update()
{
    if (isCubeMoving && GetComponent<Rigidbody>().velocity.magnitude <= 0.1)
    {
        Debug.Log("stop"); // הקוביה הפסיקה לזוז
        isCubeMoving = false;
        regularDiceCount();
    }
}
```
