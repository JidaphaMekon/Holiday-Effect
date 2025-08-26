# Holiday-Effect

1. ดึงข้อมูลแบบ Trading Days (วันเปิดตลาดเท่านั้น)
2. สร้างข้อมูลแบบ Calendar Days (รวมวันหยุดและเสาร์-อาทิตย์)
🎯 จุดประสงค์ของการใช้ชุดข้อมูลนี้
เพื่อเปรียบเทียบว่าโมเดล ML/DL ที่เรียนรู้จากข้อมูลแบบ calendar days (ที่มีวันหยุดและเติมข้อมูล) สามารถพยากรณ์ราคาหุ้นได้แม่นยำกว่าข้อมูลแบบ trading days หรือไม่
ทดสอบสมมุติฐานว่า feature เช่น is_weekend, days_since_last_trade มีผลต่อความแม่นยำของโมเดล


Model	RMSE	MAE	MAPE	R2 Score
Random Forest	48.68068449	45.06663471	25.48193361	-9.816175774
XGBoost	44.99505349	41.57038755	23.54897109	-8.240382075
Tuned XGBoost	44.30969012	40.83406127	23.12220078	-7.961027494

	is_weekend	days_since_last_trade	error_rf	error_xgb	error_tuned_xgb
is_weekend	1	0.831219527	-0.046633907	-0.020963045	-0.014258015
days_since_last_trade	0.831219527	1	-0.013654351	0.028230585	0.033040241
error_rf	-0.046633907	-0.013654351	1	0.865983562	0.868132312
error_xgb	-0.020963045	0.028230585	0.865983562	1	0.962452179
error_tuned_xgb	-0.014258015	0.033040241	0.868132312	0.962452179	1
<img width="662" height="121" alt="image" src="https://github.com/user-attachments/assets/c2118ec6-cb58-40b2-a9df-a3b61cfc2579" />

<img width="358" height="81" alt="image" src="https://github.com/user-attachments/assets/dbef8de4-18cd-47ef-8864-b43a9f7f339e" />
<img width="1400" height="600" alt="image" src="https://github.com/user-attachments/assets/d64980a6-7348-42cd-8886-a092331493d6" />


<img width="1200" height="600" alt="image" src="https://github.com/user-attachments/assets/645e7c5d-30ba-43b0-8ec6-8d70731001bd" />

<img width="1200" height="500" alt="feature_importance" src="https://github.com/user-attachments/assets/0b62496c-5974-4fa5-af47-defebbda46ed" />


<img width="1400" height="600" alt="image" src="https://github.com/user-attachments/assets/b51099f0-7a6c-4269-acd0-30f4094e086a" />

<img width="1400" height="600" alt="image" src="https://github.com/user-attachments/assets/ef51418d-0256-4cd9-9f03-3984c9eabda6" />

<img width="1000" height="600" alt="image" src="https://github.com/user-attachments/assets/e137231f-35d7-49db-b62c-729894f93ca7" />

<img width="800" height="500" alt="image" src="https://github.com/user-attachments/assets/6f7366a9-00b4-4627-b40b-5ff97bf98b6f" />
วันจันทร์ (0) และวันศุกร์ (4) มีค่า RMSE สูงกว่าวันอื่น ๆ โดยเฉพาะในโมเดล RF และ XGB
วันพุธ (2) มี RMSE ต่ำที่สุดในทุกโมเดล


<img width="640" height="480" alt="image" src="https://github.com/user-attachments/assets/36431677-41aa-42f9-9acc-9ec9782f0ce7" />
 RMSE ระหว่างวันหยุดสุดสัปดาห์ vs วันธรรมดา
RMSE ในวันหยุดสุดสัปดาห์ (is_weekend = True) สูงกว่าวันธรรมดาในทุกโมเดล
บ่งชี้ว่าโมเดลมีความไม่แม่นยำในช่วงวันหยุดหรือวันใกล้วันหยุด

<img width="912" height="476" alt="image" src="https://github.com/user-attachments/assets/bac1076d-5e7d-4e69-8bdc-2bdb5bc6f6f2" />



