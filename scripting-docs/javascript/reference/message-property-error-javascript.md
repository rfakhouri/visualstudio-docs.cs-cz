---
title: "Message – vlastnost (chyba) (JavaScript) | Microsoft Docs"
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
- message
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Message property
ms.assetid: 8cab0392-e0db-4714-827c-47ab04e8b4f2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9dbd2db6c6d31dc48d90c3b07d2388eacf73ae7a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="message-property-error-javascript"></a>message – vlastnost (Chyba) (JavaScript)
Vrátí řetězec chybové zprávy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
errorObj.message  
```  
  
## <a name="parameters"></a>Parametry  
 `errorObj`  
 Požadováno. Instance `Error` objektu.  
  
## <a name="remarks"></a>Poznámky  
 `message` Vlastnost vrátí řetězec, který obsahuje chybovou zprávu přidružené k určité chybě.  
  
 `description` a `message` vlastnosti poskytují stejnou funkcionalitu. `description` Vlastnost poskytuje zpětné kompatibility; `message` vlastnost v souladu se standardem ECMA.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu způsobí výjimku TypeError vyvolání a zobrazí název chyba a jeho zprávu.  
  
```JavaScript  
try  
{  
    // Cause an error.  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## <a name="example"></a>Příklad  
 Výstup tohoto kódu je následující.  
  
```JavaScript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **Platí pro**: [Error – objekt](../../javascript/reference/error-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Description – vlastnost (chyba)](../../javascript/reference/description-property-error-javascript.md)   
 [name – vlastnost (chyba)](../../javascript/reference/name-property-error-javascript.md)