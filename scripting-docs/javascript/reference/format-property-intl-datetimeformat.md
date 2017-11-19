---
title: "Format – vlastnost (Intl.DateTimeFormat) | Microsoft Docs"
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
ms.assetid: 487930fe-a948-446f-902d-06bb0d7685d5
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e94fcd797a63944d0162dceadf773cf9b15f943
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="format-property-intldatetimeformat"></a>format – vlastnost (Intl.DateTimeFormat)
Vrátí funkci, která formátů data specifická pro národní prostředí pomocí nastavení formátování zadané datum a čas.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
dateTimeFormatObj.format  
```  
  
#### <a name="parameters"></a>Parametry  
 `dateTimeFormatObj`  
 Požadováno. Název `DateTimeFormat` objekt, který chcete použít jako formátování.  
  
## <a name="remarks"></a>Poznámky  
 Funkce vrácený `format` vlastnost přijímá jeden argument, `date`a vrátí řetězec, který představuje lokalizované datum pomocí možností v `DateTimeFormat` objektu. `date` Parametr vrácený funkce musí být číslo, datum řetězec, nebo `Date` objektu. Pokud `date` není uvedeno, funkce, která používá [Date.now](../../javascript/reference/date-now-function-javascript.md) jako výchozí vstupní hodnota.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `DateTimeFormat` objekt k lokalizaci datum "1 Dec 2007" do němčina a změňte jeho formátování.  
  
```JavaScript  
var dtFormat = new Intl.DateTimeFormat(["de"], {  
    year: "numeric",  
    month: "long",  
    day: "2-digit",  
    hour: "numeric"  
});  
  
if (console && console.log) {  
    console.log(dtFormat.format(new Date("Dec 1, 2007")));  
    // Returns 01. Dezember 2007 00:00  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Intl.DateTimeFormat – objekt](../../javascript/reference/intl-datetimeformat-object-javascript.md)