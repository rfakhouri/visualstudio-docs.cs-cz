---
title: "Error – objekt (JavaScript) | Microsoft Docs"
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
- Error
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Error object
ms.assetid: 0b27d6ec-3997-4e91-a6c0-5afbaf494db7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efc03f13a501a1a13a2e7f3eea000b406559f30b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="error-object-javascript"></a>Error – objekt (JavaScript)
Obsahuje informace o chybách.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      errorObj = new Error()  
errorObj = new Error([number])  
errorObj = new Error([number[, description]])  
```  
  
## <a name="parameters"></a>Parametry  
 `errorObj`  
 Požadováno. Název proměnné, do kterého `Error` objekt je přiřazen. Přiřazení proměnné je vynechán, když vytvoříte pomocí chyba `throw` příkaz.  
  
 `number`  
 Volitelné. Číselná hodnota přiřazená k chybě. Nula, pokud se vynechá.  
  
 `description`  
 Volitelné. Krátký řetězec popisující chybu. Prázdný řetězec, pokud se vynechá.  
  
## <a name="remarks"></a>Poznámky  
 Vždy, když dojde k chybě spuštění, instance `Error` je vytvořen objekt k popisu chyby. Tato instance nemá dvě vnitřní vlastnosti, které obsahují popis chyby (`description` vlastnosti) a číslo chyby (`number` vlastnost). Další informace najdete v tématu [JavaScript – chyby za běhu](../../javascript/reference/javascript-run-time-errors.md).  
  
 Číslo chyby je 32bitová hodnota. Horní 16bitové slovo je kód služby, zatímco dolní slovo je aktuální chybový kód.  
  
 `Error`také možné explicitně vytvářet objekty, pomocí syntaxe uvedené výše nebo vyvolána pomocí `throw` příkaz. V obou případech můžete přidat všechny vlastnosti, které jste se rozhodli rozbalte schopnosti produktu `Error` objektu.  
  
 Většinou vytvořené v místní proměnné **try... catch** příkaz odkazuje na implicitně vytvořených `Error` objektu. Výsledkem je, že můžete použít číslo chyby a její popis jakýmkoli způsobem.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Error` objektu.  
  
```  
function checkInput(x) {  
    try  
    {  
        if (isNaN(parseInt(x))) {  
            throw new Error("Input is not a number.");  
        }  
    }  
    catch(e)  
    {  
        document.write(e.description);  
    }  
}  
  
checkInput("not a number");  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití implicitně vytvořených `Error` objektu.  
  
```JavaScript  
try  
   {  
   // Cause an error.  
   x = y;  
   }  
catch(e)  
   {  
      document.write(e);  
      document.write ("<br />");  
  
      document.write ("Number: ");  
      document.write (e.number & 0xFFFF);  
      document.write ("<br />");  
  
      document.write ("Facility Code: ");  
      document.write(e.number>>16 & 0x1FFF);  
      document.write ("<br />");  
  
      document.write ("Description: ");  
      document.write (e.description);  
   }  
  
// Output:  
// ReferenceError: 'y' is undefined  
// Number: 5009  
// Facility Code: 10  
// Description: 'y' is undefined  
  
```  
  
## <a name="methods"></a>Metody  
 [toString – metoda (Error)](../../javascript/reference/tostring-method-error.md) &#124; [valueOf – metoda (Date)](../../javascript/reference/valueof-method-date.md)  
  
## <a name="properties"></a>Vlastnosti  
 [constructor – vlastnost (chyba)](../../javascript/reference/constructor-property-error.md) &#124; [popis vlastnost](../../javascript/reference/description-property-error-javascript.md) &#124; [message – vlastnost](../../javascript/reference/message-property-error-javascript.md) &#124; [name – vlastnost](../../javascript/reference/name-property-error-javascript.md) &#124; [číslo vlastnost](../../javascript/reference/number-property-error-javascript.md) &#124; [prototype – vlastnost (chyba)](../../javascript/reference/prototype-property-error.md) &#124; [stack – vlastnost (chyba)](../../javascript/reference/stack-property-error-javascript.md) &#124; [stacktracelimit – vlastnost (chyba)](../../javascript/reference/stacktracelimit-property-error-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [throw – příkaz](../../javascript/reference/throw-statement-javascript.md)   
 [Try... catch... finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [var – příkaz](../../javascript/reference/var-statement-javascript.md)   
 [Hilo JavaScript ukázkovou aplikaci (pro Windows Store)](http://hilojs.codeplex.com/SourceControl/latest)