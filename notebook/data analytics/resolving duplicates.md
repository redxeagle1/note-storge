1. **تحديد الصفوف المكررة**:  
   ```python
   duplicates = data.duplicated()
   print(duplicates)
	   ```  
	- الدالة `duplicated()` تعيد `True` للصفوف المكررة بعد الأولى 
.  
2. **عرض الصفوف المكررة**:  
   ```python
   duplicate_rows = data[data.duplicated()]
   print(duplicate_rows)
   ```  


3. **إزالة القيم المكررة**:  
   ```python
   data = data.drop_duplicates()
	   ```  
   - يمكن تعديل السلوك عبر معلمات الدالة:  
	 - `keep='first'`: يحتفظ بالظهور الأول (الافتراضي).  
	 - `keep='last'`: يحتفظ بالظهور الأخير.  
	 - `keep=False`: يحذف جميع الظهورات .  