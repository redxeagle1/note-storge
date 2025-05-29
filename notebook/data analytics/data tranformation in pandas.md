#data_analytics 
- باستخدام Pandas، بما في ذلك ***Merging*** و ***Concatenating*** و ***Sorting*** و ***Grouping*** و ***Aggregating***.
- Merging :
	- دمج البيانات: يمكنك دمج البيانات باستخدام دالة `()pd.merge`، التي تسمح لك بدمج DataFrames بناءً على أعمدة أو مؤشرات مشتركة.
	- أنواع الدمج: يمكنك تحديد نوع الدمج الذي تريده، مثل الدمج الداخلي (`inner`)، الخارجي (`outer`)، الأيسر (`left`)، أو الأيمن (`right`).
	- دمج البيانات باستخدام `()pd.merge`:
		```python
		import pandas as pd
		data_1 ={
					'key': ['A', 'B', 'C'],
					'value1': [1, 2, 3]
				}
				
		data_2 ={
					'key': ['A', 'B', 'D'],
					'value2': [4, 5, 6]
				}
		# دمج البيانات
		df1 = pd.DataFrame(data_1)
		df2 = pd.DataFrame(data_2)
		
		df_merged = pd.merge(df1, df2, on='key', how='inner')
		print(df_merged)
		```
- Concatenating
	* تسلسل البيانات: يمكنك تسلسل البيانات باستخدام دالة `()pd.concat`، التي تسمح لك بتسلسل DataFrames بشكل رأسي أو أفقي.
	- تحديد المحور: يمكنك تحديد المحور الذي تريد تسلسل البيانات عليه
	```python
	import pandas as pd

	# تسلسل البيانات
	df1 = pd.DataFrame({'A': [1, 2, 3]})
	df2 = pd.DataFrame({'A': [4, 5, 6]})
	
	df_concat = pd.concat([df1, df2], axis=0)
	print(df_concat)

	```
- Sorting
	- فرز البيانات: يمكنك فرز البيانات باستخدام دالة `()df.sort_values` ، التي تسمح لك بفرز DataFrame بناءً على عمود أو أكثر.
	- تحديد الترتيب: يمكنك تحديد ترتيب الفرز، سواء كان تصاعديًا أو تنازليًا
		```python
		import pandas as pd
		data = {
		'name': ['John', 'Anna', 'Peter', 'Linda'],
		'age': [28, 24, 35, 32]
		}
		
		# فرز البيانات
		df = pd.DataFrame(data)
		
		df_sorted = df.sort_values(by='age', ascending=False)
		print(df_sorted)
		```
-  Grouping
	- تجميع البيانات: يمكنك تجميع البيانات باستخدام دالة `df.groupby()`، التي تسمح لك بتجميع DataFrame بناءً على عمود أو أكثر.
	- تطبيق دوال التجميع: يمكنك تطبيق دوال التجميع، مثل `mean()، sum()، count()`، على المجموعات.
		```python
		import pandas as pd
		
		data = {
		'city': ['New York', 'New York', 'Los Angeles', 'Los Angeles'],
		'sales': [100, 200, 300, 400]
		}
		
		# تجميع البيانات
		df = pd.DataFrame(data)
		df_grouped = df.groupby('city')['sales'].sum()
		print(df_grouped)
		```
- Aggregating
	- حساب الإجماليات باستخدام df.agg():
	```python
	df.agg({'column_name': 'mean'})
	```
    يمكنك تطبيق وظائف Aggregating متعددة على البيانات أو مجموعة من البيانات.
- **أفضل الممارسات**
	*   ابدأ بهدف واضح قبل تحويل البيانات.
	*   وثق خطواتك لتحويل البيانات.
	*   تحقق من نتائجك بعد كل تحويل.
	*   جرب وتكرر لتحسين مهاراتك.
