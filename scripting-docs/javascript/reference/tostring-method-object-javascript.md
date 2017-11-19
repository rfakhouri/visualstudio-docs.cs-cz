---
title: "toString – metoda (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: ToString method
ms.assetid: c4ae9da2-60c9-486f-b00a-9df03fda4a35
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 518f988486bb527220884052768e61d099dbd716
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-object-javascript"></a>toString – metoda (Object) (JavaScript)
Vrátí řetězcovou reprezentaci objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
objectname.toString([radix])  
```  
  
## <a name="parameters"></a>Parametry  
 `objectname`  
 Požadováno. Objekt, pro které je požadováno řetězcová reprezentace.  
  
 `radix`  
 Volitelné. Určuje základ – pro převod číselných hodnot do řetězce. Tato hodnota se používá pouze pro čísla.  
  
## <a name="remarks"></a>Poznámky  
 **ToString** metoda je členem všech předdefinovaných [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty. Jak se chová, závisí na typu objektu:  
  
|Objekt|Chování|  
|------------|--------------|  
|Pole|Prvky `Array` jsou převedeny na řetězce. Spojení výsledné řetězců oddělených čárkami.|  
|Boolean|Pokud je logická hodnota **true**, vrátí "`true`". Jinak vrátí "`false`".|  
|Datum|Vrátí textovou reprezentaci řetězce datum.|  
|Chyba|Vrací řetězec obsahující přidružené chybovou zprávu.|  
|Funkce|Vrací řetězec má následující formu, kde *%{FunctionName/* je název funkce jejichž **toString** byla volána metoda:<br /><br /> `function functionname( ) { [native code] }`|  
|Číslo|Vrátí textovou reprezentaci řetězce číslo.|  
|String|Vrátí hodnotu `String` objektu.|  
|Výchozí|Vrátí `"[object objectname]"`, kde `objectname` je název tohoto typu objektu.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **toString** metoda s argumentem základ –. Návratová hodnota funkce ukazuje následující obrázek je tabulka základ – převod.  
  
```JavaScript  
function CreateRadixTable (){  
   var s = "";  
  
   // Create table heading.  
   s += "Hex  Dec  Bin \n";  
  
   for (x = 0; x < 16; x++)  
   {  
      s += "   ";  
  
      // Convert to hexidecimal.  
      s += x.toString(16);  
      s += "     ";  
      if (x < 10) s += "  ";  
  
      // Convert to decimal.  
      s += x.toString(10);  
      s += "     ";  
  
      // Convert to binary.  
      s += x.toString(2);  
      s += "\n";  
   }  
  
   return(s);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **Platí pro**: [objekt Array](../../javascript/reference/array-object-javascript.md)&#124; [Boolean – objekt](../../javascript/reference/boolean-object-javascript.md)&#124; [Datum objektu](../../javascript/reference/date-object-javascript.md)&#124; [Chyba objektu](../../javascript/reference/error-object-javascript.md)&#124; [Funkce objekt](../../javascript/reference/function-object-javascript.md)&#124; [Číslo objekt](../../javascript/reference/number-object-javascript.md)&#124; [Objekt objektu](../../javascript/reference/object-object-javascript.md)&#124; [Řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)