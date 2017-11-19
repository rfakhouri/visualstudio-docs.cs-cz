---
title: "Stack – vlastnost (chyba) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Error.stack
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript error stack
- error stack [JavaScript]
ms.assetid: 1dc21fdd-853c-4664-bf1c-24eb1f6f2daf
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 14e4a2537b1543b7e8d9727afdeb8ea5dee61bbc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="stack-property-error-javascript"></a>stack – vlastnost (Chyba) (JavaScript)
Získá nebo nastaví zásobník chyb jako řetězec, který obsahuje rámce trasování zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object  
.stack   
```  
  
## <a name="remarks"></a>Poznámky  
 `stack` Je nastavena na `undefined` když chyba je vytvořený a získá informace o trasování po vyvolání k chybě. Pokud je vyvolána chyba vícekrát, `stack` vlastnosti pokaždé, když se vyvolá chybu.  
  
 Rámce zásobníku se zobrazují v následujícím formátu: **v %{FunctionName/ (\<plně kvalifikovaný název nebo adresa URL >:\<číslo řádku >:\<číslo sloupce >)**  
  
 Pokud vytvoříte vlastní objekt chyba a nastavit na hodnotu trasování zásobníku, hodnota nepřepíše, pokud se chyba.  
  
 `stack` Vlastnost nezobrazuje vložené funkce v jeho snímků. Zobrazuje jenom fyzické zásobníku.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat zásobníku, když jste zachytávání k chybě.  
  
```JavaScript  
try  
    {  
        var x = y.name;  
    }  
catch(e)  
    {  
        document.write ("Error stack: ")  
        document.write (e.stack);  
    }  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit a potom získat zásobníku.  
  
```JavaScript  
try  
    {  
        var err = Error("my error");  
        err.stack = "my stack trace";  
        throw err;  
    }  
catch(e)  
    {  
        document.write ("Error stack: ")  
        document.write (e.stack);  
    }  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]  
  
 **Platí pro**: [Error – objekt](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Description – vlastnost (chyba)](../../javascript/reference/description-property-error-javascript.md)   
 [Message – vlastnost (chyba)](../../javascript/reference/message-property-error-javascript.md)   
 [name – vlastnost (chyba)](../../javascript/reference/name-property-error-javascript.md)   
 [stacktracelimit – vlastnost (chyba)](../../javascript/reference/stacktracelimit-property-error-javascript.md)