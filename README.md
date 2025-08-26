# Holiday-Effect

1. ดึงข้อมูลแบบ Trading Days (วันเปิดตลาดเท่านั้น)
2. สร้างข้อมูลแบบ Calendar Days (รวมวันหยุดและเสาร์-อาทิตย์)
🎯 จุดประสงค์ของการใช้ชุดข้อมูลนี้
เพื่อเปรียบเทียบว่าโมเดล ML/DL ที่เรียนรู้จากข้อมูลแบบ calendar days (ที่มีวันหยุดและเติมข้อมูล) สามารถพยากรณ์ราคาหุ้นได้แม่นยำกว่าข้อมูลแบบ trading days หรือไม่
ทดสอบสมมุติฐานว่า feature เช่น is_weekend, days_since_last_trade มีผลต่อความแม่นยำของโมเดล

<img width="1200" height="500" alt="feature_importance" src="https://github.com/user-attachments/assets/0b62496c-5974-4fa5-af47-defebbda46ed" />

