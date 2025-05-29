
---

#### **الهدف الرئيسي**
- بناء نموذج انحدار خطي لتنبؤ أسعار المنازل باستخدام مكتبة Scikit-Learn.
- تقييم أداء النموذج باستخدام مؤشرات مثل الخطأ التربيعي المتوسط (MSE) ومعامل تحديد (R-squared).

---

#### **المكونات الأساسية**

1. **تحضير البيانات مع Pandas**:
   - استيراد المكتبات: `pandas`, `NumPy`, `Scikit-Learn`.
   - تحميل البيانات إلى هيكل `DataFrame` لتحليلها.
   - فحص الهيكل العام للبيانات (`data.head()`, `data.describe()`).
   - معالجة القيم المفقودة (`data.isnull().sum()`, `data.dropna()`).
   - إنشاء ميزات جديدة (مثال: حساب عمر العقار من عام البناء).

2. **بناء النموذج**:
   - تقسيم البيانات إلى مجموعة تدريب (`X_train`, `y_train`) ومجموعة اختبار (`X_test`, `y_test`).
   - تدريب النموذج باستخدام `LinearRegression()` من Scikit-Learn.
   - إجراء التنبؤات على مجموعة الاختبار (`model.predict(X_test)`).

3. **التقييم والتحليل**:
   - رسم مخطط تشتت (`scatter plot`) للمقارنة بين القيم الحقيقية والمتوقعة.
   - حساب MSE و R-squared لتقييم الدقة.
   - مثال على النتائج:  
     ```python
     Mean Squared Error: 65152879.8356798
     R-squared: 0.963632284751827
     ```

4. **شرح مفهوم Perceptron**:
   - شرح مبسط لآلية عمل الشبكات العصبية البسيطة، بما في ذلك:
     - دمج المدخلات مع الأوزان (`weighted sum`).
     - تطبيق دالة التفعيل (`activation function`).
     - حساب دالة التكلفة (`cost function`) لقياس الخطأ.

---

#### **الخطوات الرئيسية في الكود**:

```python
# استيراد المكتبات
import pandas as pd
from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error, r2_score

# تحميل البيانات
data = pd.read_csv("housing_data.csv")
print(data.head())

# معالجة البيانات
data['age'] = 2023 - data['year_built']

# تقسيم البيانات
X = data[['bedrooms', 'bathrooms', 'sqft_living', 'age']]
y = data['price']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)

# تدريب النموذج
model = LinearRegression()
model.fit(X_train, y_train)
y_pred = model.predict(X_test)

# تقييم النموذج
mse = mean_squared_error(y_test, y_pred)
r2 = r2_score(y_test, y_pred)
print(f"Mean Squared Error: {mse}")
print(f"R-squared: {r2}")

# رسم النتائج
plt.scatter(y_pred, y_test, c='r', label='Prediction')
plt.scatter(y_test, y_test, c='b', label='Actual')
plt.legend()
plt.show()
```

---

#### **الاستنتاج**
- نجاح النموذج في تحقيق دقة عالية (R-squared ≈ 0.96)، مما يشير إلى علاقة خطية قوية بين الميزات المستخدمة وسعر العقار.
- أهمية تنظيف البيانات وفهمها قبل التطبيق العملي للخوارزميات.

--- 

**ملاحظة**: تم الحفاظ على المصطلحات التقنية الإنجليزية دون ترجمة، مع التركيز على الخطوات الرئيسية والكود المرفق.