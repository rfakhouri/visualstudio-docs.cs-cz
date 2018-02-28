---
title: "Item – metoda (enumerátor) (JavaScript) | Microsoft Docs"
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
- item
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Item method
ms.assetid: a88e93f2-42df-4578-a4f9-0760bd074185
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 94275b2c82f199c96ef2d6c7d667fd27fba2702d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="item-method-enumerator-javascript"></a>item – metoda (Enumerator) (JavaScript)
Vrátí aktuální položku v kolekci.  
  
> [!WARNING]
>  Tento objekt je podporovaná jenom v aplikaci Internet Explorer.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
enumObj.item()   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované *enumObj* odkaz je žádné `Enumerator` objektu.  
  
 **Položky** metoda vrátí s aktuální položkou. Pokud kolekce je prázdná nebo s aktuální položkou. není definován, vrátí **nedefinované**.  
  
## <a name="example"></a>Příklad  
 V následující kód **položky** metoda se používá k vrácení členem `Drives` kolekce.  
  
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
 [atEnd – metoda (enumerátor)](../../javascript/reference/atend-method-enumerator-javascript.md)   
 [moveFirst – metoda (enumerátor)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [moveNext – metoda (enumerátor)](../../javascript/reference/movenext-method-enumerator-javascript.md)