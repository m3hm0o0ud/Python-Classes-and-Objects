# Python-Classes-and-Objects

### شرح الكلاس (Class) والكائن (Object) خطوة بخطوة

**البرمجة كائنية التوجه (OOP)** تعتمد بشكل أساسي على الكلاسات (Classes) والكائنات (Objects). في هذا الشرح، سنتعرف على هذه المفاهيم خطوة بخطوة لفهم كيفية إنشائها واستخدامها في البرمجة.

---

### 1. ما هو **الكلاس (Class)**؟

**الكلاس** هو عبارة عن **قالب (blueprint)** أو تصميم يستخدم لإنشاء كائنات (Objects). الكلاس يحتوي على **الخصائص (Attributes)** و**الطرق (Methods)** التي تصف وتحدد سلوك الكائنات التي يتم إنشاؤها من هذا الكلاس.

#### تشبيه بالحياة الواقعية:
فكر في الكلاس كقالب تصميم لمنزل. يمكن استخدام هذا القالب لإنشاء منازل متعددة، ولكن كل منزل قد يختلف في الألوان أو الأثاث، ولكنه يتبع نفس التصميم الأساسي.

---

### 2. ما هو **الكائن (Object)**؟

**الكائن (Object)** هو **نسخة (Instance)** من الكلاس. عندما تقوم بإنشاء كائن من كلاس معين، فهذا يعني أنك قمت بإنشاء شيء يستخدم ذلك الكلاس كقالب له.

#### تشبيه:
إذا كان الكلاس هو تصميم المنزل، فإن الكائن هو المنزل الفعلي الذي تم بناؤه بناءً على ذلك التصميم.

---

### 3. إنشاء **الكلاس** في بايثون

لإنشاء كلاس في بايثون، نستخدم الكلمة المفتاحية `class` متبوعة باسم الكلاس.

#### مثال بسيط:
```python
class Car:
    brand = "Toyota"
    model = "Corolla"
    color = "Red"
```

هنا، قمنا بإنشاء كلاس باسم `Car` يحتوي على ثلاث خصائص: `brand` (العلامة التجارية)، و`model` (الموديل)، و`color` (اللون).

---

### 4. إنشاء **الكائن** من الكلاس

بعد إنشاء الكلاس، يمكننا استخدامه لإنشاء كائن. يتم إنشاء الكائن عن طريق استدعاء اسم الكلاس كأنه دالة.

#### مثال على إنشاء كائن:
```python
my_car = Car()
```

هنا، `my_car` هو كائن تم إنشاؤه باستخدام الكلاس `Car`.

#### الوصول إلى الخصائص:
يمكننا الوصول إلى خصائص الكائن باستخدام النقطة (`.`).

```python
print(my_car.brand)  # الناتج: Toyota
print(my_car.model)  # الناتج: Corolla
print(my_car.color)  # الناتج: Red
```

---

### 5. استخدام **`__init__`** لتخصيص الكائن

الدالة **`__init__`** هي دالة مدمجة خاصة في بايثون يتم استدعاؤها تلقائيًا عند إنشاء كائن جديد من الكلاس. تستخدم هذه الدالة لتهيئة الخصائص عند إنشاء الكائن.

#### مثال:

```python
class Car:
    def __init__(self, brand, model, color):
        self.brand = brand
        self.model = model
        self.color = color
```

هنا، الدالة `__init__` تأخذ المعطيات `brand`، و`model`، و`color` وتقوم بتعيينها للخصائص الخاصة بالكائن باستخدام `self`.

#### إنشاء كائن باستخدام `__init__`:

```python
my_car = Car("Toyota", "Corolla", "Red")
```

#### الوصول إلى الخصائص:
```python
print(my_car.brand)  # الناتج: Toyota
print(my_car.model)  # الناتج: Corolla
print(my_car.color)  # الناتج: Red
```

---

### 6. إضافة **طرق (Methods)** للكائنات

**الطرق (Methods)** هي دوال (Functions) يتم تعريفها داخل الكلاس وتعمل على الكائنات. يمكن استخدامها لتنفيذ وظائف معينة على الكائن.

#### مثال:
```python
class Car:
    def __init__(self, brand, model, color):
        self.brand = brand
        self.model = model
        self.color = color

    def start(self):
        print(f"The {self.brand} {self.model} is starting.")
```

هنا، قمنا بإضافة طريقة `start()` التي تطبع رسالة توضح أن السيارة بدأت.

#### استخدام الطريقة:
```python
my_car = Car("Toyota", "Corolla", "Red")
my_car.start()  # الناتج: The Toyota Corolla is starting.
```

---

### 7. المعامل **`self`** في الكلاس

المعامل **`self`** في بايثون يشير إلى الكائن الحالي. يجب تمرير `self` كمعامل أول لكل دالة داخل الكلاس ليتمكن الكلاس من الوصول إلى خصائص وطرق الكائن.

#### ملاحظة:
- `self` ليس إلزاميًا أن يكون بهذا الاسم، ولكن يجب أن يكون المعامل الأول في جميع الطرق داخل الكلاس.

#### مثال:
```python
class Car:
    def __init__(this_object, brand, model, color):
        this_object.brand = brand
        this_object.model = model
        this_object.color = color

    def start(this_object):
        print(f"The {this_object.brand} {this_object.model} is starting.")
```

هنا، استخدمنا `this_object` بدلاً من `self`، والكود يعمل بنفس الطريقة.

---

### 8. تعديل خصائص الكائنات

يمكنك تعديل خصائص الكائن بعد إنشائه.

#### مثال:
```python
my_car = Car("Toyota", "Corolla", "Red")
my_car.color = "Blue"  # تغيير لون السيارة
print(my_car.color)  # الناتج: Blue
```

---

### 9. حذف خصائص أو كائنات

يمكنك حذف خاصية أو كائن بالكامل باستخدام الكلمة المفتاحية `del`.

#### حذف خاصية:
```python
del my_car.color
```

#### حذف الكائن بالكامل:
```python
del my_car
```

---

### 10. استخدام الجملة **`pass`**

إذا كنت تريد تعريف كلاس بدون محتوى بشكل مؤقت، يمكنك استخدام الجملة `pass` لتجنب حدوث خطأ.

#### مثال:
```python
class Car:
    pass
```

---

### الخلاصة:
- **الكلاس (Class):** هو قالب أو تصميم لإنشاء كائنات، يحتوي على خصائص وطرق.
- **الكائن (Object):** هو نسخة من الكلاس، يمكن أن يحتوي على بيانات مخصصة له.
- **الدالة `__init__`:** هي دالة مخصصة لتهيئة خصائص الكائن عند إنشائه.
- **الطرق (Methods):** هي دوال تعمل على الكائنات وتنفذ وظائف معينة.
- **`self`:** يشير إلى الكائن الحالي داخل الكلاس.

الآن بعد فهم الأساسيات، يمكنك بناء برامج معقدة باستخدام الكلاسات والكائنات لتنظيم الكود بطريقة أفضل وأكثر احترافية.
