---
title: "RE4B: Introduction_02"
date: 2025-10-01
categories: [Reverse, Books]
tags: [Reverse, RE4B, Basics]
image: /assets/img/posts/ch1/optimized.jpeg
---

### Source code can be compiled by different compilers with various optimization levels.

## الفكرة العامة
نفس كود الـ C  
ممكن يطلع Assembly مختلف حسب:

1. نوع الـ compiler  
2. مستوى الـ optimization  
3. هل فيه debug info ولا لا  

---

## يعني ايه Optimization
الـ compiler مش بس بيترجم  
دا كمان ممكن:

- يعدل الكود  
- يشيل حاجات  
- يغير الترتيب  

وده علشان:
- يخليه أسرع  
- أو أقل حجما  

---

## مستويات الـ Optimization
غالبا فيه 3 مستويات مشهورة  

### Optimization = 0
- مفيش تعديل على الكود  
- الكود طويل وواضح وسهل الفهم  
- كل سطر C تقريبا ليه Assembly مقابل  

وده النوع اللي بيكون مفيد في:
- التعليم  
- Debugging  
- Reverse Engineering  

---

## الأنواع التانية من Optimization (O1 / O2 / O3)
الـ compiler بيحاول:

- يسرع البرنامج  
- يشيل أي كود ملوش لازمة  

النتيجة:
- كود Assembly أقصر  
- بس أصعب في الفهم  
- سطور C ممكن تختفي تماما  

---

## Example C Code
```c
int x = 5;
```
![Gald](/assets/img/posts/ch1/gald.jpeg)
