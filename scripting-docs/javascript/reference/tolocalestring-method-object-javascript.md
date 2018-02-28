---
title: "toLocaleString – metoda (Object) (JavaScript) | Microsoft Docs"
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
- toLocaleString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleString method
ms.assetid: 0901afcb-126b-4ed7-bd6a-2301d50e2326
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f88e1c702cd8a7d702630ae90ef840c4af88f30
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tolocalestring-method-object-javascript"></a>toLocaleString – metoda (Object) (JavaScript)
Vrátí datum převedeno na řetězec pomocí aktuální národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.toLocaleString()   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `dateObj` libovolnou `Date` objektu.  
  
 `toLocaleString` Metoda vrátí `String` objekt, který obsahuje data zapsána ve formátu dlouho výchozí aktuální národní prostředí.  
  
-   Pro kalendářní data mezi 1601 a roku. 1999 je datum formátovaného podle uživatele ovládacího panelu Místní nastavení.  
  
-   Pro data mimo tento rozsah výchozí formát **toString** metoda se používá.  
  
 Například ve Spojených státech amerických `toLocaleString` vrátí "01/05/96 00:00:00" pro leden 5. V Evropě, vrátí hodnotu "05/01/96 00:00:00" pro stejné datum, jako Evropského konvence vloží den předcházející měsíci.  
  
> [!NOTE]
>  `toLocaleString`lze používat pouze zobrazíte výsledky pro uživatele; ho by nikdy použít jako základ pro výpočty v rámci skriptu vrácených výsledků je specifický pro počítač.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `toLocaleString` metoda.  
  
```JavaScript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [objekt Array](../../javascript/reference/array-object-javascript.md)&#124; [Datum objektu](../../javascript/reference/date-object-javascript.md)&#124; [Číslo objekt](../../javascript/reference/number-object-javascript.md)&#124; [Objekt objektu](../../javascript/reference/object-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toLocaleDateString – metoda (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)