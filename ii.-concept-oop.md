# II. ทำความเข้าใจส่วนประกอบของโค้ดเปรียบเทียบกับ concept ของ OOP ต่อไปนี้ โดยยกตัวอย่างส่วนประกอบของโค้ดประกอบการอธิบาย

**1. Class (คลาส)**

* **คำอธิบาย**: คลาสคือแม่แบบที่ใช้ในการสร้างออบเจ็กต์ ซึ่งกำหนดคุณสมบัติและพฤติกรรม
* **ตัวอย่างโค้ด**:

{% code title="Java" %}
```java
class Animal {
    Animal() {
        System.out.println("create animal");
    }
    
    void sound() {
        System.out.println("animal makes a sound");
    }
}
```
{% endcode %}

{% code title="Python" %}
```python
class Animal:
    def __init__(self):
        print("create animal")
    
    def sound(self):
        print("animal makes a sound")
```
{% endcode %}

{% code title="C++" %}
```cpp
class Animal {
public:
    Animal() {
        cout << "create animal" << endl;
    }

    void sound() {
        cout << "animal makes a sound" << endl;
    }
};
```
{% endcode %}

**2. Object / Instance (ออบเจ็กต์ / อินสแตนซ์)**

* **คำอธิบาย**: Object หรือ อินสแตนซ์ คือสิ่งที่ถูกสร้างจากคลาส (class) ซึ่งคลาสทำหน้าที่เป็นแม่แบบ (template) ในการกำหนดคุณสมบัติ (properties) และพฤติกรรม (methods) ที่ออบเจ็กต์จะมี เมื่อเราเรียกใช้คลาสเพื่อสร้างออบเจ็กต์ขึ้นมา เรากำลังสร้าง "อินสแตนซ์" หนึ่งของคลาสนั้น ออบเจ็กต์แต่ละตัวมีคุณสมบัติเฉพาะตัวที่อาจจะแตกต่างกันได้ ขึ้นอยู่กับค่าที่ถูกกำหนดขณะสร้าง
* **ตัวอย่างโค้ด**:

```java
Animal a = new Animal();
```

```python
a = Animal()
```

```cpp
Animal* a = new Animal();
```

* ตัวอย่างเหล่านี้ ออบเจ็กต์ `a` คืออินสแตนซ์ของคลาส `Animal` ที่ถูกสร้างขึ้น เราสามารถเรียกใช้คุณสมบัติและพฤติกรรมของ `Animal` ผ่านออบเจ็กต์นี้ได้

**3. Subclass / Derived Class (ซับคลาส / คลาสอนุพันธ์)**

* **คำอธิบาย**: Subclass (ซับคลาส) หรือ Derived Class (คลาสอนุพันธ์) คือคลาสที่ถูกสร้างขึ้นโดยสืบทอดคุณสมบัติและพฤติกรรมจากคลาสแม่ (Superclass หรือ Base Class) ซับคลาสสามารถใช้งาน method และ properties ของคลาสแม่ได้ และสามารถเพิ่มฟังก์ชันหรือคุณสมบัติใหม่ๆ ที่ซับคลาสนี้ต้องการ
* **ตัวอย่างโค้ด**

```java
class Dog extends Animal {
    Dog() {
        System.out.println("dog");
    }
}
```

```python
class Dog(Animal):
    def __init__(self):
        super().__init__()
        print("dog")
```

```cpp
class Dog : public Animal {
public:
    Dog() {
        cout << "dog" << endl;
    }
};
```

* ในตัวอย่างนี้ คลาส `Dog` เป็นซับคลาสของ `Animal` ซึ่งมันสามารถสืบทอดคุณสมบัติและพฤติกรรมจาก `Animal` ได้ และเพิ่มการทำงานใหม่ผ่านคอนสตรัคเตอร์ของมันเอง

**4. Message (ข้อความ)**

* **คำอธิบาย**: Message หรือ ข้อความ ใน OOP หมายถึงการสื่อสารกับออบเจ็กต์ผ่านการเรียกใช้ method การส่งข้อความไปยังออบเจ็กต์นั้นเป็นการส่งคำสั่งให้มันดำเนินการบางอย่างตามที่กำหนดไว้ใน method เช่น การเรียกใช้งาน method `sound()` จะส่ง "ข้อความ" ไปยังออบเจ็กต์ให้มันทำงานตามที่กำหนดไว้ใน method นั้น
* **ตัวอย่างโค้ด**:

```java
a.sound();
```

```python
a.sound()
```

```cpp
a->sound();
```

* &#x20;การเรียกใช้ method `sound()` บน object `a` จะส่งข้อความให้ object นั้นแสดงพฤติกรรมที่ถูกกำหนดใน method `sound()` ของมัน

**5. Inheritance (การสืบทอด)**

* **คำอธิบาย**: Inheritance (การสืบทอด) เป็นแนวคิดที่สำคัญใน OOP ที่ช่วยให้ซับคลาสสามารถสืบทอดคุณสมบัติและพฤติกรรมจากซูเปอร์คลาส (Superclass) ทำให้ไม่ต้องเขียนโค้ดซ้ำ การสืบทอดทำให้โค้ดสามารถนำไปใช้งานซ้ำและสามารถขยายขีดความสามารถของคลาสแม่ได้โดยการเพิ่มหรือเปลี่ยนแปลงพฤติกรรมในซับคลาส
* **ตัวอย่างโค้ด**:

```java
class Cat extends Animal {
    Cat() {
        System.out.println("cat");
    }
}
```

```python
class Cat(Animal):
    def __init__(self):
        super().__init__()
        print("cat")
```

```cpp
class Cat : public Animal {
public:
    Cat() {
        cout << "cat" << endl;
    }
};
```

* ในตัวอย่างนี้ คลาส `Cat` สืบทอดจาก `Animal` และสามารถเพิ่มพฤติกรรมของตนเองได้ เช่น ในคอนสตรัคเตอร์ที่พิมพ์ "cat"

**6. Polymorphism (พหุลักษณ์)**

* **คำอธิบาย**: Polymorphism (พหุลักษณ์) หมายถึงความสามารถในการที่ออบเจ็กต์หลายประเภทสามารถใช้งาน method ที่มีชื่อเดียวกันได้ แต่ทำงานแตกต่างกันตามประเภทของออบเจ็กต์นั้น Polymorphism ทำงานได้เนื่องจากการสืบทอดและการเขียนทับ (override) method ของคลาสแม่โดยคลาสลูก
* **ตัวอย่างโค้ด**:

```java
Animal a = new Dog();
a.sound();
```

```python
a = Dog() 
a.sound() 
```

```cpp
Animal* a = new Dog(); 
a->sound(); 
```

* &#x20;เราสามารถใช้ออบเจ็กต์ที่เป็นประเภทต่างๆ (เช่น `Dog` หรือ `Cat`) แต่เรียกใช้ method เดียวกันคือ `sound()` ซึ่งผลลัพธ์ที่ได้จะขึ้นอยู่กับประเภทของออบเจ็กต์