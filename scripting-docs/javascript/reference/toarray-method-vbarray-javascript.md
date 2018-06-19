---
title: toArray – metoda (VBArray) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- toArray
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toArray method
ms.assetid: 664de44c-2039-4289-82f6-948e9d744d80
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeee8acad04125eb942089b4d8dacef6f0f5e6fb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792057"
---
# <a name="toarray-method-vbarray-javascript"></a>toArray – metoda (VBArray) (JavaScript)
Vrátí standardní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] pole převést z VBArray.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
safeArray.toArray( )   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované *safeArray* odkaz je objekt VBArray.  
  
 Převod překládá multidimenzionální VBArray do jednoho dimenzí [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] pole. Každá následných dimenze je připojen na konec předchozí. Například VBArray se tři rozměry a tři prvky v Každá dimenze je převeden na [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] pole následujícím způsobem:  
  
 Předpokládejme, že VBArray obsahuje: (1, 2, 3), (4, 5, 6), (7, 8, 9). Po překlad [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] obsahuje pole: 1, 2, 3, 4, 5, 6, 7, 8, 9.  
  
 Aktuálně neexistuje žádný způsob, jak převést [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] pole do VBArray.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu se skládá ze tří částí. První část je kód v jazyce VBScript k vytvoření bezpečným polím jazyka Visual Basic. Druhá část je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kód, který převede pole bezpečné jazyka Visual Basic pro [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] pole. Obě tyto části přejděte do \<HEAD > části na stránce HTML. Je třetí součást [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kód, který je třeba do \<textu > části spouštět další dvě části.  
  
```JavaScript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(j, i) = k  
         document.writeln(k)  
         k = k + 1  
      Next  
      document.writeln("<BR>")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vbarray)  
{  
   var a = new VBArray(vbarray);  
   var b = a.toArray();  
   var i;  
   for (i = 0; i < 9; i++)   
   {  
      document.writeln(b[i]);  
   }  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
<!--  
   VBArrayTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9 a standardy aplikace Internet Explorer 10. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
 **Platí pro**: [objekt VBArray](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Dimensions – metoda (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [getItem – metoda (VBArray)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [LBound – metoda (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [UBound – metoda (VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)