---
tags: code_snipits
description: a good code snipits to keep
---
### التعامل مع القيم المفقودة (**Missing Data**)  
1. **تحديد القيم المفقودة**:  
	- استخدام `isnull()` و`notnull()` لإنشاء أقنعة منطقية تُظهر مواقع القيم المفقودة.  
	- مثال:  
 ```python
 import pandas as pd
 data = {
			'Name': ['Alice', 'Bob', None, 'David'],
			'Age': [25, 30, None, 35]
		}

 df = pd.DataFrame(data)
 print(df.isnull().sum())  # عد القيم المفقودة في كل عمود
 
 df.isna().sum(axis=1).plot() # ده بيرسم بقى القيم المفقوده نفسها
 ```  
2. **حذف القيم المفقودة**:  
	- استخدام `dropna()` لحذف الصفوف أو الأعمدة ذات القيم المفقودة (مناسب إذا كانت النسبة صغيرة وعشوائية).  
	- مثال:  
 ```python
 df_cleaned = df.dropna()  # حذف الصفوف ذات القيم المفقودة
 ```  
3. **ملء القيم المفقودة (**Imputation**)**:  
	 - استخدام `fillna()` لملء القيم المفقودة بمتوسط (`mean`) أو متوسط (`median`) العمود، أو قيمة مخصصة.  
	- مثال:  
 ```python
 df['Age'] = df['Age'].fillna(df['Age'].median())  # ملء القيم المفقودة بالمتوسط
 ```  
---
### إدارة القيم الشاذة (**Outliers**)  
1. **كشف القيم الشاذة**:  
	 - استخدام `describe()` لعرض إحصائيات وتحديد القيم التي تختلف بشكل كبير عن المتوسط أو النطاق الطبيعي.  
	- استخدام `quantile()` لحساب النسب المئوية وتحديد الحدود الدنيا والعليا.  
	- مثال:  
 ```python
 Q1 = df['Age'].quantile(0.25)
 Q3 = df['Age'].quantile(0.75)
 IQR = Q3 - Q1
 lower_bound = Q1 - 1.5 * IQR
 upper_bound = Q3 + 1.5 * IQR
 ```  
2. **معالجة القيم الشاذة**:  
	 - استخدام `clip()` لتحديد حدود للقيم وتجنب التأثير السلبي للقيم الشاذة.  
	- مثال:  
 ```python
 df['Age_capped'] = df['Age'].clip(upper=40)  # تحديد الحد الأعلى للعمر بـ 40
 ```  
---
### تحويل أنواع البيانات (**Data Type Conversions**)  
1. **تحويل البيانات إلى أنواع محددة**:  
	- استخدام `astype()` لتغيير نوع البيانات (مثل تحويل سلسلة نصية إلى عدد).  
	- مثال:  
 ```python
 df['Age'] = df['Age'].astype(int)  # تحويل العمر إلى عدد صحيح
 ```  
2. **تحويل لأنواع محدده**:  
	- استخدام `to_datetime()` لتحويل السلاسل النصية إلى تواريخ قابلة للتحليل.
	- وأيضا  `to_numeric()`,  `to_categorical()`
	- مثال:  
 ```python
 df['Date'] = pd.to_datetime(df['Date'])  # تحويل العمود إلى تواريخ
 ```  
---
### التحليل الاستكشافي (**Exploratory Data Analysis - EDA**)  
1. **عرض البيانات**:  
	- استخدام `head()` و`tail()` لعرض أول وأخر صفوف البيانات.  
2. **الإحصائيات الوصفية**:  
	- استخدام `describe()` لحساب المتوسط، الانحراف المعياري، النسب المئوية، وغيرها.  
3. **التجميع والتحليل**:  
	- استخدام `groupby()` لتحليل البيانات عبر مجموعات (مثل حساب المتوسط حسب المدينة).  
	- مثال:  
	 ```python
	 df.groupby('City')['Age'].mean()  # حساب العمر المتوسط حسب المدينة
	 ```  
4. **التصورات البيانية**:  
	- استخدام `plot()` مع مكتبات مثل **Matplotlib** لرسم الرسوم البيانية (مثل المدرج التكراري أو مخطط التبعثر).  
	```python
	# YOU MUST IMPORT MATPLOTLIP TO PERFORM THIS FEATURE
	unemp_state.plot(
						kind='barh',
						figsize=(8,12),
						title='unemployment by state, april 2020',
						width=1,
						edgecolor = 'black'
					) 
	```