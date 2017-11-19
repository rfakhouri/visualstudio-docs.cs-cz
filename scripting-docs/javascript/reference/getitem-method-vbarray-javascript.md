---
title: "getItem – metoda (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getItem
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getItem method
- Item property
ms.assetid: f62964ad-8b2f-4596-95d0-b20e587ecea5
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e6457435d047f2780a19fa8ce26fc2bb86f7ae0e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getitem-method-vbarray-javascript"></a>getItem – metoda (VBArray) (JavaScript)
Vrátí položku do zadaného umístění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
safeArray.getItem(dimension1[, dimension2, ...], dimensionN)   
```  
  
## <a name="parameters"></a>Parametry  
 *safeArray*  
 Požadováno. Objekt VBArray.  
  
 *dimension1,..., dimensionN*  
 Určuje přesné umístění na požadovaný prvek VBArray. *n*se rovná počet dimenzí v VBArray.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu se skládá ze tří částí. První část je kód v jazyce VBScript k vytvoření bezpečným polím jazyka Visual Basic. Druhá část je [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kód, který iteruje bezpečným polím jazyka Visual Basic a vytiskne obsah jednotlivých prvků. Obě tyto části přejděte do \<HEAD > části na stránce HTML. Je třetí součást [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] kód, který je třeba do \<textu > části spouštět další dvě části.  
  
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
         a(i, j) = k  
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
function GetItemTest(vbarray)  
{  
   var i, j;  
   var a = new VBArray(vbarray);  
   for (i = 0; i <= 2; i++)  
   {  
      for (j =0; j <= 2; j++)  
      {  
         document.writeln(a.getItem(i, j));  
      }  
   }  
}  
-->  
</script>  
</head>  
<body>  
<script type="text/javascript">  
<!--  
   GetItemTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9 a standardy aplikace Internet Explorer 10. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
 **Platí pro**: [objekt VBArray](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Dimensions – metoda (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [LBound – metoda (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [toArray – metoda (VBArray)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [UBound – metoda (VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)