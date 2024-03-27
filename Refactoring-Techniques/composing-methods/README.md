# Composing Methods

> Aِiming to avoid lengthy, opaque code by removing duplication and enhancing clarity and maintainability.

* Extract Method
* Inline Method
* Extract Variable
* Inline Temp
* Replace Temp with Query
* Split Temporary Variable
* Remove Assignments to Parameters
* Replace Method with Method Object
* Substitute Algorithm

## Extract Method

فصل الوضائف بشكل عام المشكلة لدنا وظفتين في نفس الوظيفة

```
function calculateCircleArea($radius) {
    return pi() * square($radius);
}

function square($num) {
    return $num * $num;
}

```

## Inline Method

عكس استخراج الوظائف لدينا كود لا يحتاج الى الفصل


```
function calculateCircleArea(\$radius) 
{   
    return  pi() \* \$radius \* \$radius; 
}
```


## Extract Variable

لدينا في هذه الحالة جملة معقدة يتم فصل الجملة في اكقر من منتعير 

```
$hasProparty = ....;
$isAdmin = ...;
$hasPermission = ....;
....

if ($hasProparty && $isAdmin && $hasPermission) {
    // do something
}

```


## Inline Temp

يتم حذف المتغير الزائد

```
$rate = $user->getRate();
return $rate > 5;
```

```
return $user->getRate()
```

## Replace Temp with Query

يتم تحويل المتغير الموقت الى وضيفية

```
$totalPrice = $quantity * $unitPrice;
```

```
function calculateTotalPrice($quantity, $unitPrice) {
    return $quantity * $unitPrice;
}
```

## Split Temporary Variable

عدم استخدام نفس المتغير لاكثر من نوع عمليات

```
$temp = $a * $b;
$result1 = $temp - $c;
....
....
$result2 = $temp + $d;
```

```
$temp1 = $a * $b;
$result1 = $temp1 - $c;
.....
.....
$temp2 = $a * $b;
$result2 = $temp2 + $d;
```

## Remove Assignments to Parameters

الهدف عدم تغير قيمة ال partamerts

Use a local variable instead of a parameter.

```
function discount($input, $quantity) {
  if ($quantity > 50) {
    $input -= 2;
  }
  return $input;
}
```

```
function discount($input, $quantity) {
  $result = $input;
  if ($quantity > 50) {
    $result -= 2;
  }
  return $result;
}
```


## Replace Method with Method Object

تعني استبدال طريقة داخلية كبيرة أو معقدة في كائن منفصل. هذا الكائن يقوم بتنفيذ الطريقة الكبيرة أو المعقدة، يصبح الكود أكثر نظافة وأكثر سهولة في الفهم.

تم استخدم هذه الطريقة في الويب هوك

## Substitute Algorithm

استبدال خوارزمية أو طريقة بديلة أكثر فعالية او اداء




خلاصة يتم تحديد الحل حسب المشكلة
