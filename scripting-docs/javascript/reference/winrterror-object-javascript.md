---
title: Winrterror – objekt (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- WinRTError object [JavaScript]
- JavaScript, WinRTError object
ms.assetid: d75ab8e5-e729-4d86-90fd-ea228c30dd66
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 11b339b4fc3c4bd4f34416ffd98b8f9c3f288f98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791778"
---
# <a name="winrterror-object-javascript"></a>WinRTError – objekt (JavaScript)
Po návratu HRESULT určující selhání volání prostředí Windows Runtime jazyka JavaScript převede na zvláštní Chyba prostředí Windows Runtime. Je k dispozici pouze v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, pokud je k dispozici, prostředí Windows Runtime v rámci globálního oboru názvů jazyka JavaScript.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
errorObj = new WinRTError();  
  
```  
  
## <a name="remarks"></a>Poznámky  
 Winrterror – chyba typ se používá pouze pro chyby, které pocházejí z rozhraní API systému Windows Runtime.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak je winrterror – vyvolána a zachycení.  
  
```JavaScript  
try {  
            Windows.Storage.ApplicationData.localFolder.createFileAsync("sample.txt");  
        } catch (err) {  
            var n = err;  
        }  
  
```  
  
## <a name="methods"></a>Metody  
 Winrterror – objekt nemá žádné metody.  
  
## <a name="properties"></a>Vlastnosti  
 Winrterror – objekt má stejné vlastnosti, jako [chyba objektu](../../javascript/reference/error-object-javascript.md) objektu.  
  
## <a name="requirements"></a>Požadavky  
 Winrterror – objekt je podporována pouze v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace není v aplikaci Internet Explorer.  
  
## <a name="see-also"></a>Viz také  
 [Error – objekt](../../javascript/reference/error-object-javascript.md)