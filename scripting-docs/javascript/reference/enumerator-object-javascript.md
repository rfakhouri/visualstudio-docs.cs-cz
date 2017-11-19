---
title: "Enumerator – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Enumerator
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Enumerator object
ms.assetid: 63f03c21-d58c-47db-a728-4d8d88b0a422
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50b1ebfb6e24ed734f008b3c05f10a1687c4aff5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="enumerator-object-javascript"></a>Enumerator – objekt (JavaScript)
Umožňuje výčet položky v kolekci.  
  
> [!WARNING]
>  Tento objekt je podporováno v aplikaci Internet Explorer, není ve [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
enumObj = new Enumerator([collection])   
```  
  
## <a name="parameters"></a>Parametry  
 `enumObj`  
 Požadováno. Název proměnné, do kterého `Enumerator` objekt je přiřazen.  
  
 `collection`  
 Volitelné. Objekt žádné kolekce.  
  
## <a name="remarks"></a>Poznámky  
 Kolekce se liší od pole, že členové kolekce nejsou přímo přístupné. Místo použití indexy, stejně jako s poli, můžete přesunout ukazatel aktuální položky jenom na první nebo další prvek kolekce.  
  
 `Enumerator` Objekt poskytuje přístup k kteréhokoli člena kolekce a se chová podobně jako `For...Each` příkaz v jazyce VBScript.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje použití `Enumerator` objektu:  
  
```JavaScript  
var bytesPerGB = 1024 * 1024 * 1024;  
  
var fso = new ActiveXObject("Scripting.FileSystemObject");  
  
document.write(fso.Drives);  
var e = new Enumerator(fso.Drives);  
  
var driveString = "";  
  
e.moveFirst();  
while (e.atEnd() == false)  
{  
    var drv = e.item();  
  
    driveString += drv.Path + " - ";  
  
    if (drv.IsReady){  
        var freeGB = drv.FreeSpace / bytesPerGB;  
        var totalGB = drv.TotalSize / bytesPerGB;  
  
        driveString += freeGB.toFixed(3) + " GB free of ";  
        driveString += totalGB.toFixed(3) + " GB";  
    }  
    else{  
        driveString += "Not Ready";  
    }  
  
    driveString += "<br />";;  
  
    e.moveNext();  
}  
document.write(driveString);  
  
// Output: <drive information  
  
```  
  
## <a name="properties"></a>Vlastnosti  
 `Enumerator` Objekt nemá žádné vlastnosti.  
  
## <a name="methods"></a>Metody  
 [atEnd – metoda](../../javascript/reference/atend-method-enumerator-javascript.md) &#124; [položky Metoda](../../javascript/reference/item-method-enumerator-javascript.md) &#124; [moveFirst – metoda](../../javascript/reference/movefirst-method-enumerator-javascript.md) &#124; [moveNext – metoda](../../javascript/reference/movenext-method-enumerator-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 Podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9 a standardy aplikace Internet Explorer 10. Není podporováno v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Viz [Informace o verzi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="see-also"></a>Viz také  
 [Boolean – objekt](../../javascript/reference/boolean-object-javascript.md)