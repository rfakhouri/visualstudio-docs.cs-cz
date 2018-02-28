---
title: "VBArray – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VBArray
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- VBArray object constant
ms.assetid: f0b767f1-ea8a-4726-962b-2708d4742518
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b86e261a0cef445f1e0e0ecd651d5eb283cffce1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="vbarray-object-javascript"></a>VBArray – objekt (JavaScript)
Poskytuje přístup k polím bezpečné jazyka Visual Basic.  
  
> [!WARNING]
>  Tento objekt je podporováno v aplikaci Internet Explorer, není ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
varName = new VBArray(safeArray)   
```  
  
## <a name="parameters"></a>Parametry  
 `varName`  
 Požadováno. Název proměnné, ke kterému je přiřazena VBArray.  
  
 *safeArray*  
 Požadováno. VBArray – hodnota.  
  
## <a name="remarks"></a>Poznámky  
 VBArrays jsou jen pro čtení a nelze vytvořit přímo. *SafeArray* argument musí získat hodnotu VBArray před předáním VBArray konstruktoru. To můžete provést pouze načtením hodnoty z existující ActiveX nebo jiného objektu.  
  
 VBArrays může mít více dimenzí. Indexy Každá dimenze se může lišit. **Dimenze** metoda načte počet dimenzí v poli; `lbound` a `ubound` metody načtení rozsahu indexy, které používá každá dimenze.  
  
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
      document.writeln("<br />")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vbarray){  
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
  
## <a name="properties"></a>Vlastnosti  
 `VBArray` Objekt nemá žádné vlastnosti.  
  
## <a name="methods"></a>Metody  
 [Dimensions – metoda](../../javascript/reference/dimensions-method-vbarray-javascript.md) &#124; [getItem – metoda](../../javascript/reference/getitem-method-vbarray-javascript.md) &#124; [lbound – metoda](../../javascript/reference/lbound-method-vbarray-javascript.md) &#124; [toArray – metoda](../../javascript/reference/toarray-method-vbarray-javascript.md) &#124; [ubound – metoda](../../javascript/reference/ubound-method-vbarray-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9 a standardy aplikace Internet Explorer 10. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="see-also"></a>Viz také  
 [Array – objekt](../../javascript/reference/array-object-javascript.md)