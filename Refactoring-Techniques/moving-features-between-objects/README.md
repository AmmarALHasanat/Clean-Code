# Moving Features between Objects

> how to safely move functionality between classes, create new classes, and hide implementation details from public access.

* Move Field
* Move Method
* Extract Class
* Inline Class
* Hide Delegate
* Remove Middle Man
* Introduce Foreign Method
* Introduce Local ExtensionExtract MethodInline Method

## Move Field and Move Method

يتم استخدام Method and Field

في فئة أخرى أكثر من فئتها الخاصة.

الحل نقل هذه الوظيفة او المتغير  الى الفئة المستخدمة فيها اكثر

```
class A
    int fieldA;
    methodA()
class B
  
```

```
class A 
class B
   int fieldA;
   methodA()
```

## Extract Class

One class have more faculty for workflow

الحل اسخراج الفئة منها

```
Class A
    int a  
    int b
    methodA()
    methodB()
```

```
Class A
    int a  
    methodA()
Class B
    int b
    methodB()
```

## Inline Class

في حالة عدم قيام الفئة بأداء مهمة معينة ولا يتولى أي مسؤوليات إضافية،

الحل دمج هذه الفئة مع فئة اخرا عكس اسخراج الفئة تماما

```
Class A
    int a  
    methodA()
Class B
    int b
    methodB()
```

```
Class A
    int a  
    int b
    methodA()
    methodB()
```

## Hide Delegate

باختصار عندما نريد إخفاء فئة عن فئة العميل

when we want to hide a class from the client class 

متى تستخدم هذه الحالة عندما نريد منع الوصول المباشر الى فئة معية

مثلا

Controller access repository and repository access model


## Remove Middle Man

هو عبارة عن فئة وسيطة بين اكثر من فئة ولا تحمل اي معنى في وجودها بين الفئات او وظيفة من فئة اخرا  بحيث هذه الفئة تحمل الكثير من الوظائف حيث نقوم بازالة الفئة الوسيطة او الخاصية و نقوم بالاستدعاء المباشر لهذه الفئة عكس اخفاء الفئة

A class has too many methods that simply delegate to other objects.

Delete these methods and force the client to call the end methods directly.

حلات الاستخدام

1. The *server-class* doesn’t do anything itself and simply creates needless complexity. In this case, give thought to whether this class is needed at all.
2. Every time a new feature is added to the *delegate*, you need to create a delegating method for it in the *server-class*. If a lot of changes are made, this will be rather tiresome.

## Introduce Foreign Method

لا تحتوي فئة الأداة المساعدة على وظيفة التي تحتاجها ولا يمكنك إضافة الوطيفة إلى الفئة.

الحل هو اضافة هذه الوظيفة في الفئة التي تستخدم هذه الفئة المساعدة

الفئة المساعدة مثل مكتبة خارجية او حزمة


## Introduce Local Extension

لا تحتوي فئة الأداة المساعدة على وظيفة التي تحتاجها ولا يمكنك إضافة الوطيفة إلى الفئة. 

قم بإنشاء فئة جديدة تحتوي على الأساليب واجعلها إما تابعة أو مجمعة لفئة الأداة المساعدة.



الفرق هنا بين Introduce Foreign Method و Introduce Local Extension



* Introduce Foreign Method لتحسين اداء وطيفة معيتة بدل من كتاية نفس الكود اكثر من مرة
* Introduce Local Extension الفئة المساعدة لا تحتوي على الوظيفة التي تحتاجها و الاسوء من ذلك لا يمكن اضافة هذه الوضيفية كل مرة في اكثر من فئة



باختصار يتم تحديد الحل حسب الحالة
