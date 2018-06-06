---
title: Format – vlastnost (Intl.NumberFormat) | Microsoft Docs
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
ms.assetid: 68c3223a-023c-4fa0-aa99-d049a7a0e26a
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7528c79852c4836dfd967322b876d738f9781107
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34572472"
---
# <a name="format-property-intlnumberformat"></a>format – vlastnost (Intl.NumberFormat)
Vrátí funkci, která formátuje číslo specifická pro národní prostředí pomocí zadané číslo nastavení formátování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
numberFormatObj.format  
```  
  
#### <a name="parameters"></a>Parametry  
 `numberFormatObj`  
 Požadováno. Název `NumberFormat` objekt, který chcete použít jako formátování.  
  
## <a name="remarks"></a>Poznámky  
 Funkce vrácený `format` vlastnost přijímá jeden argument, `value`a vrátí řetězec, který představuje číslo lokalizované pomocí možností v `NumberFormat` objektu. Pokud `value` není k dispozici, funkce vrátí hodnotu `NaN` (není číslo).  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `NumberFormat` objekt k vytvoření lokalizované číslo.  
  
```JavaScript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigits: 1  
})  
  
if (console && console.log) {  
    console.log(nf.format(100)); // "¥100.00"  
}  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Intl.NumberFormat – objekt](../../javascript/reference/intl-numberformat-object-javascript.md)