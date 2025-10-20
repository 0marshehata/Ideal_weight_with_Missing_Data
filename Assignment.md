# شرح كود الملف `Assignment.ipynb` (تفصيلي بالعربية)

---

## الخلية 1 — نوع: `markdown`

**محتوى (Markdown):**


# 🧠 Handling Missing Values (Google Colab Version)

This notebook demonstrates how to handle missing values in a dataset using **pandas** in Google Colab.
We'll:
1. Upload a CSV file
2. Inspect missing values
3. Apply three methods: Dropna, Mean Fill, and Forward Fill
4. Compare results.


**شرح مختصر:** هذه خلية وصف/ملاحظات في النوتبوك، تُستخدم لشرح أو توثيق الكود.

---

## الخلية 2 — نوع: `code`

**الكود:**

```python
# --- 📦 Import Libraries ---
import pandas as pd
import numpy as np
from google.colab import files
```

**شرح سطر بسطر:**

- سطر 1: `# --- 📦 Import Libraries ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `import pandas as pd`
  - استيراد مكتبة أو حزم — يستخدم لجلب وظائف جاهزة (مثل numpy, pandas, matplotlib).

- سطر 3: `import numpy as np`
  - استيراد مكتبة أو حزم — يستخدم لجلب وظائف جاهزة (مثل numpy, pandas, matplotlib).

- سطر 4: `from google.colab import files`
  - استيراد مكتبة أو حزم — يستخدم لجلب وظائف جاهزة (مثل numpy, pandas, matplotlib).

---

## الخلية 3 — نوع: `code`

**الكود:**

```python
# --- 📂 Upload CSV File ---
print("📁 Please upload your dataset file (e.g., ideal_weight_dataset_with_missing.csv):")
uploaded = files.upload()

# Get uploaded file name
file_name = list(uploaded.keys())[0]
print(f"\n✅ File uploaded successfully: {file_name}")
```

**شرح سطر بسطر:**

- سطر 1: `# --- 📂 Upload CSV File ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `print("📁 Please upload your dataset file (e.g., ideal_weight_dataset_with_missing.csv):")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 3: `uploaded = files.upload()`
  - تعيين قيمة لمتغير (تخزين بيانات في اسم لاستخدام لاحق).

- سطر 4: ``
  - سطر فارغ (فاصل بصري).

- سطر 5: `# Get uploaded file name`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 6: `file_name = list(uploaded.keys())[0]`
  - تعيين قيمة لمتغير (تخزين بيانات في اسم لاستخدام لاحق).

- سطر 7: `print(f"\n✅ File uploaded successfully: {file_name}")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

---

## الخلية 4 — نوع: `code`

**الكود:**

```python
# --- Read the Data ---
df = pd.read_csv(file_name)

# --- 🔍 Show the First 5 Rows ---
print("\n👀 First 5 rows of the dataset:")
print(df.head())

# --- 🔎 Show Missing Values Before Handling ---
print("\n❌ Number of missing values before handling:")
print(df.isnull().sum())
```

**شرح سطر بسطر:**

- سطر 1: `# --- Read the Data ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `df = pd.read_csv(file_name)`
  - تعامل مع بيانات عبر مكتبة pandas — جداول، قراءات csv، عمليات تنظيف وتحليل.

- سطر 3: ``
  - سطر فارغ (فاصل بصري).

- سطر 4: `# --- 🔍 Show the First 5 Rows ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 5: `print("\n👀 First 5 rows of the dataset:")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 6: `print(df.head())`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 7: ``
  - سطر فارغ (فاصل بصري).

- سطر 8: `# --- 🔎 Show Missing Values Before Handling ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 9: `print("\n❌ Number of missing values before handling:")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 10: `print(df.isnull().sum())`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

---

## الخلية 5 — نوع: `code`

**الكود:**

```python
# --- 1️⃣ Remove Missing Values Completely ---
df_drop = df.dropna()
print("\n✅ After using dropna():")
print(df_drop.isnull().sum())
```

**شرح سطر بسطر:**

- سطر 1: `# --- 1️⃣ Remove Missing Values Completely ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `df_drop = df.dropna()`
  - تعيين قيمة لمتغير (تخزين بيانات في اسم لاستخدام لاحق).

- سطر 3: `print("\n✅ After using dropna():")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 4: `print(df_drop.isnull().sum())`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

---

## الخلية 6 — نوع: `code`

**الكود:**

```python
# --- 2️⃣ Fill Missing Values with Mean ---
df_mean = df.fillna(df.mean(numeric_only=True))
print("\n✅ After using mean fill:")
print(df_mean.isnull().sum())
```

**شرح سطر بسطر:**

- سطر 1: `# --- 2️⃣ Fill Missing Values with Mean ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `df_mean = df.fillna(df.mean(numeric_only=True))`
  - تعيين قيمة لمتغير (تخزين بيانات في اسم لاستخدام لاحق).

- سطر 3: `print("\n✅ After using mean fill:")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 4: `print(df_mean.isnull().sum())`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

---

## الخلية 7 — نوع: `code`

**الكود:**

```python
# --- 3️⃣ Forward Fill (Previous Value) ---
df_ffill = df.ffill()
print("\n✅ After using forward fill:")
print(df_ffill.isnull().sum())
```

**شرح سطر بسطر:**

- سطر 1: `# --- 3️⃣ Forward Fill (Previous Value) ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `df_ffill = df.ffill()`
  - تعيين قيمة لمتغير (تخزين بيانات في اسم لاستخدام لاحق).

- سطر 3: `print("\n✅ After using forward fill:")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 4: `print(df_ffill.isnull().sum())`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

---

## الخلية 8 — نوع: `code`

**الكود:**

```python
# --- 📊 Compare All Three Methods ---
comparison = pd.DataFrame({
    'Original Missing': df.isnull().sum(),
    'After Dropna': df_drop.isnull().sum(),
    'After Mean Fill': df_mean.isnull().sum(),
    'After Forward Fill': df_ffill.isnull().sum()
})

print("\n📊 Comparison of All Three Methods:")
print(comparison)
```

**شرح سطر بسطر:**

- سطر 1: `# --- 📊 Compare All Three Methods ---`
  - تعليق يشرح السطر أو مجموعة الأسطر، ولا يُنفّذ ككود.

- سطر 2: `comparison = pd.DataFrame({`
  - تعامل مع بيانات عبر مكتبة pandas — جداول، قراءات csv، عمليات تنظيف وتحليل.

- سطر 3: `    'Original Missing': df.isnull().sum(),`
  - سطر برمجي عام — ينفّذ عملية محددة ضمن البرنامج (تفصيل يعتمد على السياق).

- سطر 4: `    'After Dropna': df_drop.isnull().sum(),`
  - سطر برمجي عام — ينفّذ عملية محددة ضمن البرنامج (تفصيل يعتمد على السياق).

- سطر 5: `    'After Mean Fill': df_mean.isnull().sum(),`
  - سطر برمجي عام — ينفّذ عملية محددة ضمن البرنامج (تفصيل يعتمد على السياق).

- سطر 6: `    'After Forward Fill': df_ffill.isnull().sum()`
  - سطر برمجي عام — ينفّذ عملية محددة ضمن البرنامج (تفصيل يعتمد على السياق).

- سطر 7: `})`
  - سطر برمجي عام — ينفّذ عملية محددة ضمن البرنامج (تفصيل يعتمد على السياق).

- سطر 8: ``
  - سطر فارغ (فاصل بصري).

- سطر 9: `print("\n📊 Comparison of All Three Methods:")`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.

- سطر 10: `print(comparison)`
  - طباعة قيمة إلى المخرج (الشاشة) لملاحظة النتائج أو التصحيح.
