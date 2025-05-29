---
tags: code_cheat_sheet
description: fast peek sheet
---
### إنشاء DataFrame:
- من قاموس:
	```python
	data = {
				'Name': ['Alice', 'Bob', 'Charlie'],
				'Age': [25, 30, 28]
			}
	df = pd.DataFrame()
	```
- من قائمة قوائم:
	```python
	data = [
			['Alice', 25], 
			['Bob', 30],
			['Charlie', 28]
		   ]
	df = pd.DataFrame(data, columns=['Name', 'Age'])
	```
- من ملف CSV: استخدم `df = pd.read_csv('data.csv')`
### فحص DataFrame:
- عرض أول بضع صفوف: `()df.head`
- عرض آخر بضع صفوف: (`)df.tail`
- الحصول على أبعاد DataFrame:
   استخدم `df.shape()`
- الحصول على معلومات حول DataFrame:
 استخدم `df.info()`
- الحصول على إحصائيات وصفية: `()df.describe`
### اختيار وتصفية البيانات
- اختيار الأعمدة:
	- اختيار عمود واحد:` df['Age']`
	- اختيار أعمدة متعددة:` df[['Name', 'Age']]`
- اختيار الصفوف:
	- باستخدام `loc: df.loc[0]`
	- باستخدام `iloc: df.iloc[0]`
- تصفية البيانات:
	- باستخدام الفهرسة البوليانية: `df[df['Age'] > 25]`
	- باستخدام query: `df.query('Age > 25 and Name == "Bob"')`
### التعامل مع القيم المفقودة
-  تحديد القيم المفقودة:
	- استخدم `df.isnull()`
	- استخدم `df['Age'].isnull()`
- التعامل مع القيم المفقودة:
	- إزالة الصفوف التي تحتوي على قيم مفقودة: `df.dropna()`
	- استبدال القيم المفقودة بقيمة محددة: `df.fillna(0)`
	- استبدال القيم المفقودة بالمتوسط: `df['Age'].fillna(df['Age'].mean(), inplace=True)`
### تطبيق الوظائف المخصصة
- تعريف وظيفة مخصصة وتطبيقها على عمود معين: 
   استخدم`df['discounted_sales'] = df['sales'].apply(lambda x: x * 0.9)`
### تحويل البيانات
- تحويل البيانات باستخدام pivot_table: 
  استخدم `df.pivot_table(index='region', columns='product', values='sales')`
