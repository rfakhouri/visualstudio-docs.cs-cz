---
title: "Trim – metoda (String) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: trim method
ms.assetid: 03d38c7e-25cd-4ede-b58e-1a10b5249bab
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de358981cfbf569ef35be95b55b3e9856027df35
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="trim-method-string-javascript"></a>trim – metoda (String) (JavaScript)
Odstraňuje z řetězce počáteční a koncové prázdné znaky a znaky ukončení řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringObj.trim()  
```  
  
## <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. A `String` objekt nebo řetězcový literál. Tento řetězec není upraveném `trim` metoda.  
  
## <a name="return-value"></a>Návratová hodnota  
 Původní řetězec s odebraným počátečním a koncovým prázdným znakem a znakem ukončení řádku.  
  
## <a name="remarks"></a>Poznámky  
 Znaky, které jsou odebrány, zahrnují mezeru, tabulátor, posun stránky, návratový znak a přechod na nový řádek. V tématu [speciální znaky](../../javascript/advanced/special-characters-javascript.md) komplexní seznam mezer a řádku ukončovací znaky.  
  
 Příklad, který ukazuje, jak implementovat vlastní oříznutí metodu, najdete v části [prototypy a jejich dědičnost](../../javascript/advanced/prototypes-and-prototype-inheritance.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `trim` metoda.  
  
```JavaScript  
var message = "    abc def     \r\n  ";  
  
document.write("[" + message.trim() + "]");  
document.write("<br/>");  
document.write("length: " + message.trim().length);  
  
// Output:  
//  [abc def]  
//  length: 7  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Speciální znaky](../../javascript/advanced/special-characters-javascript.md)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)   
 [Posouvání, posouvání a přibližování ukázkové aplikace](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)