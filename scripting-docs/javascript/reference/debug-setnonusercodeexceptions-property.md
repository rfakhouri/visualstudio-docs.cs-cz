---
title: "Debug.setnonusercodeexceptions – vlastnost | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1dd2abee-a415-41bb-a359-017da62f9485
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f53084d5580bc7b6b6c6356268dc60f519b2bd6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="debugsetnonusercodeexceptions-property"></a>Debug.setNonUserCodeExceptions – vlastnost
Určuje, zda všechny bloky try-catch – v tomto rozsahu považován pomocí ladicího programu jako neošetřené uživatelem. Výjimky můžete klasifikován jako vyvolána, neošetřené uživatelem nebo neošetřená.  
  
 Pokud je tato vlastnost nastavena na `true` v daném oboru, ladicího programu můžete pak určit určitou akci (třeba rozdělení) na výjimky vydané uvnitř tohoto oboru, pokud vývojáře, které chcete rozdělit na výjimky neošetřené uživatelem. Pokud je tato vlastnost nastavena na `false` je stejný jako v případě, že byla nikdy nastavena vlastnost.  
  
 Další informace o ladění najdete v tématu [Přehled ladění aktivních skriptů](http://go.microsoft.com/fwlink/p/?LinkId=249469).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.setNonUserCodeExceptions [= bool];  
```  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak nastavit tuto vlastnost.  
  
```JavaScript  
(function () {  
    Debug.setNonUserCodeExceptions = true;  
    try{  
        var x = null;  
        x.y();  
    } catch (e) {  
    // Catch the exception.  
    }  
})();  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]