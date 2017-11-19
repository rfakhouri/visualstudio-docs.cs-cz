---
title: "číslo vlastnost (chyba) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Number
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Number property
ms.assetid: 8697e20b-a2b0-4e26-85c0-ab07ddfe8281
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bbc229e7d0572e1a3dbed056b344da7ff9ce7292
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="number-property-error-javascript"></a>number – vlastnost (Chyba) (JavaScript)
Vrací nebo nastavuje číselná hodnota, které jsou přidružené k určité chybě. `Error` Výchozí vlastností objektu je **číslo**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object  
.number [= errorNumber]  
```  
  
## <a name="parameters"></a>Parametry  
 *Objekt*  
 Jakoukoli instanci systému `Error` objektu.  
  
 *argument číslo chyby*  
 Celé číslo představující chybu.  
  
## <a name="remarks"></a>Poznámky  
 Číslo chyby je 32bitová hodnota. Horní slovo 16bitové je kód budovy a nižší slovo je kód chyby. Chcete-li zjistit, kód chyby, použijte `&` (bitové a) operátor kombinovat vlastnost číslo s hexadecimální číslo `0xFFFF`.  
  
## <a name="example"></a>Příklad  
 Následující příklad způsobí výjimku, která je vyvolána a zobrazí kód chyby, který je odvozený od číslo chyby.  
  
```JavaScript  
try  
    {  
    // Cause an error.  
    var x = y;  
    }  
catch(e)  
    {  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
  
    document.write ("Facility Code: ")  
    document.write(e.number>>16 & 0x1FFF)  
    document.write ("<br />");  
  
    document.write ("Error Message: ")  
    document.write (e.message)  
    }  
```  
  
## <a name="example"></a>Příklad  
 Výstup tohoto kódu je následující.  
  
```JavaScript  
Error Code: 5009  
Facility Code: 10  
Error Message: 'y' is undefined  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **Platí pro**: [Error – objekt](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Description – vlastnost (chyba)](../../javascript/reference/description-property-error-javascript.md)   
 [Message – vlastnost (chyba)](../../javascript/reference/message-property-error-javascript.md)   
 [name – vlastnost (chyba)](../../javascript/reference/name-property-error-javascript.md)