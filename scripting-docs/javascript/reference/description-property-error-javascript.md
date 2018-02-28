---
title: "Description – vlastnost (chyba) (JavaScript) | Microsoft Docs"
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
- Description
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- error handling, error description
- Description property
- errors, description
ms.assetid: ea727f1e-2041-4400-965c-67e6d47a1ff0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6135951fdf65698ed48b9bbacdcc55c1aac22d41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="description-property-error-javascript"></a>description – vlastnost (Chyba) (JavaScript)
Vrací nebo nastavuje popisný řetězec přidružený k určité chybě.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object  
.description [= stringExpression]  
```  
  
## <a name="parameters"></a>Parametry  
 *objekt*  
 Požadováno. Všechny instance `Error` objektu.  
  
 `stringExpression`  
 Volitelné. Řetězcového výrazu obsahujícího popis chyby.  
  
## <a name="remarks"></a>Poznámky  
 **Popis** vlastnost obsahuje řetězec chybové zprávy, které jsou přidružené k určité chybě. Použijte hodnotu obsažené v této vlastnosti upozorní uživatele, aby k chybě.  
  
 **Popis** a **zpráva** vlastnosti poskytují stejnou funkcionalitu; **popis** vlastnost poskytuje zpětnou kompatibilitu;  **zpráva** vlastnost v souladu se standardem ECMA.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **popis** vlastnost.  
  
```JavaScript  
try  
{  
// Cause an error:  
    x = y     
}  
catch(e)  
{  
// Prints "[object Error]":  
    document.write(e)  
    document.write (" ");  
// Prints 5009:  
    document.write((e.number & 0xFFFF))    
    document.write (" ");  
// Prints "'y' is undefined":  
    document.write(e.description);  
    document.write (" ");  
// Prints "'y' is undefined":  
    document.write(e.message)  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **Platí pro**: [Error – objekt](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Number – vlastnost (chyba)](../../javascript/reference/number-property-error-javascript.md)   
 [Message – vlastnost (chyba)](../../javascript/reference/message-property-error-javascript.md)   
 [name – vlastnost (chyba)](../../javascript/reference/name-property-error-javascript.md)