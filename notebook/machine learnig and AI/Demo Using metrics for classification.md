### تلخيص النص حول **مقاييس التصنيف في تعلم الآلة باستخدام Python**

#### **مقدمة**  
يُقدم النص شرحًا عمليًا لاستخدام **مقاييس التصنيف (Classification Metrics)** في تقييم نماذج تعلم الآلة باستخدام لغة Python، مع التركيز على اختيار النموذج المناسب لحل مشكلة معينة. تُستخدم هذه المقاييس لتحديد فعالية النماذج في مهام مثل:  
- تصنيف البريد الإلكتروني (Spam Detection).  
- اكتشاف الاحتيال (Fraud Detection).  
- التشخيص الطبي (Medical Diagnosis) .  

---

#### **1. استيراد المكتبات الضرورية**  
- **المكتبات المستخدمة**:  
  - **Pandas**: تنظيم البيانات في جداول.  
  - **train_test_split**: تقسيم البيانات إلى مجموعات تدريب واختبار.  
  - **Logistic Regression** و**Decision Tree Classifier**: نماذج للتنبؤ بناءً على الأنماط.  
  - **Accuracy Score** و**Precision Score**: مقاييس لتقييم دقة النموذج.  
  - **Matplotlib**: رسم البيانات بصريًا لتحليل النتائج .  

---

#### **2. تحميل وعرض مجموعة البيانات**  
- **مجموعة البيانات**:  
  - يتم استخدام مجموعة **Iris Dataset** من مكتبة Scikit-Learn، تحتوي على قياسات أزهار Iris وتصنيفها إلى أنواع.  
  - البيانات تُقسم إلى:  
    - **X**: القياسات (Features).  
    - **Y**: الأنواع (Labels).  
  - تنظيم البيانات في جدول قابل للقراءة باستخدام Pandas .  

---

#### **3. تقسيم البيانات إلى مجموعات تدريب واختبار**  
- **الآلية**:  
  - استخدام `train_test_split` لتقسيم البيانات إلى:  
    - **X_train** و**Y_train**: بيانات التدريب.  
    - **X_test** و**Y_test**: بيانات الاختبار.  
  - **النسبة**: 30% من البيانات تُخصص للاختبار (`test_size=0.3`).  
  - **الثبات**: `random_state=42` لضمان تكرار النتائج .  

---

#### **4. تدريب نموذجين: Logistic Regression وDecision Tree**  
- **النموذج الأول (Logistic Regression)**:  
  - يبحث عن حد فاصل خطي بين الفئات.  
- **النموذج الثاني (Decision Tree)**:  
  - يُنشئ هيكل قرارات عبر فرعيات لتصنيف البيانات.  
- **التقييم**:  
  - يتم إجراء التنبؤات على بيانات الاختبار (`Y_pred_log_reg` و`Y_pred_DT`).  
  - مقارنة التنبؤات مع القيم الفعلية (`Y_test`) لحساب الدقة .  

---

#### **5. مقاييس التقييم الأساسية**  
1. **الدقة (Accuracy)**:  
   - تقيس نسبة التنبؤات الصحيحة (الإيجابية والسلبية) إلى إجمالي البيانات.  
   - **القيود**: قد تكون مضللة في البيانات غير المتوازنة (مثل 99% بيانات سلبية) .  

2. **الدقة (Precision)**:  
   - تقيس نسبة التنبؤات الإيجابية الصحيحة (TP) إلى إجمالي التنبؤات الإيجابية (TP + FP).  
   - تُقلل الأخطاء الإيجابية الكاذبة (FP)، مثل تصنيف بريد غير مفيد كبريد عشوائي خاطئ .  

3. **ال召回 (Recall)**:  
   - تقيس نسبة الحالات الإيجابية الفعلية المكتشفة (TP) إلى إجمالي الحالات الإيجابية الفعلية (TP + FN).  
   - تُقلل الأخطاء السلبية الكاذبة (FN)، مثل عدم اكتشاف مرض حقيقي في التشخيص الطبي .  

4. **متوسط F1 (F1-Score)**:  
   - متوسط وزني بين الدقة والاستدعاء، يُفضل عندما تكون كلا المعيارين مهمين.  
   - يُعاقب القيم المنخفضة في أي من المعيارين، مما يُجبر النموذج على تحسين كليهما .  

---

#### **6. رسم مصفوفة الارتباك (Confusion Matrix)**  
- **الهدف**:  
  - توضيح عدد التنبؤات الصحيحة (TP, TN) والأخطاء (FP, FN) بصريًا.  
  - تساعد في فهم أداء النموذج بشكل شامل .  

---

#### **7. مقاييس متقدمة: ROC-AUC**  
- **التعريف**:  
  - يُقيّم أداء النموذج عبر حدود تصنيف مختلفة، مما يُظهر قدرة النموذج على التمييز بين الفئات.  
- **التطبيق**:  
  - يُستخدم في المهام التي تتطلب توازنًا بين الدقة والاستدعاء، مثل الكشف عن الاحتيال أو التشخيص الطبي .  

---

#### **8. اختيار المقاييس المناسبة حسب التطبيق**  
- **التشخيص الطبي**:  
  - التركيز على **ال召回** لتقليل الأخطاء السلبية الكاذبة (FN).  
- **اكتشاف الاحتيال**:  
  - التركيز على **الدقة** لتقليل الأخطاء الإيجابية الكاذبة (FP).  
- **التنبؤ بهروب العملاء (Churn Prediction)**:  
  - استخدام **متوسط F1** لضمان توازن بين الدقة والاستدعاء .  

---

#### **الخاتمة**  
- **الأهمية**:  
  - المقاييس هي "بوصلة" في عالم تقييم نماذج التصنيف، حيث تساعد في اختيار النموذج الأمثل بناءً على طبيعة المشكلة والأهداف.  
- **التوصية**:  
  - استخدام مجموعة من المقاييس (مثل الدقة، الاستدعاء، F1-Score، ROC-AUC) لضمان تقييم شامل، خاصة في التطبيقات الحساسة مثل الطب أو المالية .  

> **ملاحظة**: النص الأصلي لم يتضمن كودًا تقنيًا، لذا لم يتم تضمين أي كود في الملخص

### تلخيص الفيديو حول **مقاييس التصنيف في Python**  

#### **المقدمة**  
- **الهدف**: تعليم كيفية استخدام مقاييس التصنيف (Classification Metrics) لتقييم نماذج تعلم الآلة، مثل **الدقة (Accuracy)**، **الدقة (Precision)**، **الاستدعاء (Recall)**، و**متوسط F1 (F1-Score)**، مع تطبيق عملي على مجموعة بيانات الأزهار (Iris Dataset).  

---

#### **1. استيراد المكتبات الأساسية**  
```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, precision_score, recall_score, f1_score, confusion_matrix
import matplotlib.pyplot as plt
import seaborn as sns
```

---

#### **2. تحميل وعرض مجموعة البيانات**  
- **مجموعة البيانات**: Iris Dataset من Scikit-Learn، تحتوي على قياسات أزهار (طول/عرض الأوراق) وتصنيفها إلى 3 أنواع.  
- **التنظيم**:  
  ```python
  iris = load_iris()
  X = iris.data
  y = iris.target
  data = pd.DataFrame(data=iris.data, columns=iris.feature_names)
  data['target'] = y
  data['target_name'] = data['target'].map({i: name for i, name in enumerate(iris.target_names)})
  print(data.head())
  ```

---

#### **3. تقسيم البيانات إلى تدريب واختبار**  
```python
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.3, random_state=42)
```
- **النسبة**: 70% للتدريب و30% للاختبار.  
- **الثبات**: `random_state=42` لضمان تكرار النتائج .  

---

#### **4. تدريب النماذج**  
1. **نموذج الانحدار اللوجستي (Logistic Regression)**:  
   ```python
   log_reg = LogisticRegression()
   log_reg.fit(X_train, y_train)
   ```  
2. **نموذج شجرة القرار (Decision Tree Classifier)**:  
   ```python
   decision_tree = DecisionTreeClassifier()
   decision_tree.fit(X_train, y_train)
   ```  

---

#### **5. تقييم النماذج**  
- **التنبؤات**:  
  ```python
  y_pred_log_reg = log_reg.predict(X_test)
  y_pred_dt = decision_tree.predict(X_test)
  ```  
- **حساب المقاييس**:  
  ```python
  # الدقة (Accuracy)
  accuracy_log_reg = accuracy_score(y_test, y_pred_log_reg)
  accuracy_dt = accuracy_score(y_test, y_pred_dt)

  # الدقة (Precision)
  precision_log_reg = precision_score(y_test, y_pred_log_reg, average='weighted')
  precision_dt = precision_score(y_test, y_pred_dt, average='weighted')

  # الاستدعاء (Recall)
  recall_log_reg = recall_score(y_test, y_pred_log_reg, average='weighted')
  recall_dt = recall_score(y_test, y_pred_dt, average='weighted')

  # متوسط F1
  f1_log_reg = f1_score(y_test, y_pred_log_reg, average='weighted')
  f1_dt = f1_score(y_test, y_pred_dt, average='weighted')
  ```  

---

#### **6. رسم مصفوفة الارتباك**  
```python
cm_log_reg = confusion_matrix(y_test, y_pred_log_reg)
cm_decision_tree = confusion_matrix(y_test, y_pred_dt)

fig, axes = plt.subplots(1, 2, figsize=(12, 6))
sns.heatmap(cm_log_reg, annot=True, fmt='d', cmap='Blues', ax=axes[0])
axes[0].set_xlabel('Predicted')
axes[0].set_ylabel('Actual')
axes[0].set_title('Confusion Matrix - Logistic Regression')

sns.heatmap(cm_decision_tree, annot=True, fmt='d', cmap='Blues', ax=axes[1])
axes[1].set_xlabel('Predicted')
axes[1].set_ylabel('Actual')
axes[1].set_title('Confusion Matrix - Decision Tree')
plt.tight_layout()
plt.show()
```

---

#### **7. تفسير النتائج**  
- **النتائج**:  
  - **الانحدار اللوجستي**:  
    - دقة (Accuracy): 1.0  
    - دقة (Precision): 1.0  
    - استدعاء (Recall): 1.0  
    - متوسط F1: 1.0  
  - **شجرة القرار**:  
    - دقة (Accuracy): 1.0  
    - دقة (Precision): 1.0  
    - استدعاء (Recall): 1.0  
    - متوسط F1: 1.0  

- **الخلاصة**:  
  - كلا النموذجين حققا أداءً ممتازًا على البيانات المستخدمة، لكن قد تختلف النتائج مع بيانات غير متوازنة أو أكثر تعقيدًا.  

---

#### **8. الاستنتاج**  
- **أهمية المقاييس**:  
  - اختيار المقياس المناسب يعتمد على التطبيق (مثل التركيز على الاستدعاء في التشخيص الطبي أو الدقة في اكتشاف البريد العشوائي).  
  - مصفوفة الارتباك تُظهر الأخطاء النوعية (مثل FP وFN) بشكل بصري.  

> **ملاحظة**: الكود الكامل متاح في الفيديو، ويُنصح باختباره على بيئات تطوير مثل Jupyter Notebook.