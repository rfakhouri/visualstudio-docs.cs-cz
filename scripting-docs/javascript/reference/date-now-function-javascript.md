---
title: "Date.Now – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- now method
ms.assetid: 41beda89-1a40-4fb1-88b0-38c090af739b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41a098c55b8ced3c630d3724615835301b6f00c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="datenow-function-javascript"></a>Date.now – funkce (JavaScript)
Získá aktuální datum a čas.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Date.now()  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Počet milisekund mezi půlnoc, 1. ledna 1970 a aktuální datum a čas.  
  
## <a name="remarks"></a>Poznámky  
 [GetTime – metoda](../../javascript/reference/gettime-method-date-javascript.md) vrátí počet milisekund, po mezi 1. ledna 1970 a zadané datum.  
  
 Informace o tom, jak vypočítat uplynulý čas a porovnání kalendářních dat najdete v tématu [výpočet dat a časů (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `now` metoda.  
  
```JavaScript  
var start = Date.now();  
var response = prompt("What is your name?", "");  
var end = Date.now();  
var elapsed = (end - start) / 1000;  
document.write("You took " + elapsed + " seconds" + " to type: " + response);  
  
// Output:  
// You took <seconds> seconds to type: <name>  
```  
  
## <a name="requirements"></a>Požadavky  
 Není podporováno v nainstalovaných verzí starších než aplikace Internet Explorer 9. Však není podporováno v následujících režimech dokumentů: Quirks, standardy aplikace Internet Explorer 6, standardy aplikace Internet Explorer 7, standardy aplikace Internet Explorer 8, standardy aplikace Internet Explorer 9, standardy aplikace Internet Explorer 10. Podporováno také v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
## <a name="see-also"></a>Viz také  
 [getTime – metoda (Date)](../../javascript/reference/gettime-method-date-javascript.md)   
 [Date – objekt](../../javascript/reference/date-object-javascript.md)   
 [Výpočet dat a časů (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)   
 [Metody jazyka JavaScript](../../javascript/reference/javascript-methods.md)