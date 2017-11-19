---
title: "stacktracelimit – vlastnost (chyba) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Error.stackTraceLimit
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- error stack track limit [JavaScript]
- JavaScript error stack
- error stack [JavaScript]
- JavaScript stack trace limit
ms.assetid: 127ef8e8-892e-4263-9ebc-03364af01212
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9af736ee8b385f93b761f1dfa021c23ee5376292
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="stacktracelimit-property-error-javascript"></a>stackTraceLimit – vlastnost (Chyba) (JavaScript)
Získá nebo nastaví limit pro trasování zásobníku, která je ekvivalentní počet snímků chyba k zobrazení. Výchozí limit je 10.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Error  
.stackTraceLimit   
```  
  
## <a name="remarks"></a>Poznámky  
 Můžete nastavit `stackTraceLimit` vlastnosti tak, aby všechny kladnou hodnotu mezi 0 a `Infinity`. Pokud `stackTraceLimit` je nastavena na hodnotu 0 v době, je vržena chyba se zobrazí žádné trasování zásobníku. Pokud je vlastnost nastavena na zápornou hodnotu, nebo jiné než číselné hodnoty, hodnotu převést na hodnotu 0. Pokud stacktracelimit – je nastaven na `Infinity`, se zobrazí celý zásobník. V opačném `ToUint32` se používá k hodnotu převést.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit a potom získat limit pro trasování zásobníku.  
  
```JavaScript  
try  
    {  
    var err = new Error("my error");  
    Error.stackTraceLimit = 7;  
    throw err;  
    }  
catch(e)  
    {  
    document.write ("Error stack trace limit: ")  
    document.write (Error.stackTraceLimit);  
    }  
```  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v aplikaci Internet Explorer 10 a [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
 **Platí pro**: [Error – objekt](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Description – vlastnost (chyba)](../../javascript/reference/description-property-error-javascript.md)   
 [Message – vlastnost (chyba)](../../javascript/reference/message-property-error-javascript.md)   
 [name – vlastnost (chyba)](../../javascript/reference/name-property-error-javascript.md)   
 [Stack – vlastnost (chyba)](../../javascript/reference/stack-property-error-javascript.md)