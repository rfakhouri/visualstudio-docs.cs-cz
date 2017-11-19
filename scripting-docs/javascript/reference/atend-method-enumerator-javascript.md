---
title: "atEnd – metoda (enumerátor) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: atEnd
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: atEnd method
ms.assetid: 326808fb-9a0f-428e-aff1-b11b237913f1
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b5097d00c11ffafc314264f134aedda3981c8e2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="atend-method-enumerator-javascript"></a>atEnd – metoda (enumerátor) (JavaScript)
Vrátí logickou hodnotu udávající, pokud je čítač na konec kolekce.  
  
> [!WARNING]
>  Tento objekt je podporovaná jenom v aplikaci Internet Explorer.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
myEnum.atEnd()  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované *myEnum* odkaz je žádné `Enumerator` objektu.  
  
 `atEnd` Metoda vrátí **true** s aktuální položkou je poslední v kolekci, kolekce je prázdná, nebo s aktuální položkou. není definován. Funkce **false**.  
  
## <a name="example"></a>Příklad  
 V následující kód `atEnd` metoda se používá k určení, pokud bylo dosaženo konce seznamu jednotky:  
  
```JavaScript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9 a standardy aplikace Internet Explorer 10. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
 **Platí pro**: [Enumerator – objekt](../../javascript/reference/enumerator-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Item – metoda (enumerátor)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [moveFirst – metoda (enumerátor)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [moveNext – metoda (enumerátor)](../../javascript/reference/movenext-method-enumerator-javascript.md)   
 [Enumerator – objekt](../../javascript/reference/enumerator-object-javascript.md)