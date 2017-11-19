---
title: "Compare – vlastnost (Intl.Collator) | Microsoft Docs"
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
ms.assetid: 59f274dc-6e52-4344-8d5c-b9f0000b66e0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bfd222ac8d2c94efe279177e7f4d8ffdf850f44
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="compare-property-intlcollator"></a>compare – vlastnost (Intl.Collator)
Vrátí funkci, který porovnává dva řetězce pomocí kompletování pořadí řazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
collatorObj.compare  
```  
  
#### <a name="parameters"></a>Parametry  
 `collatorObj`  
 Požadováno. Název `Collator` objekt, který chcete použít pro porovnání.  
  
## <a name="remarks"></a>Poznámky  
 Funkce vrácený `compare` vlastnost má dva argumenty, `x` a `y`a vrátí výsledek porovnání specifická pro národní prostředí `x` a `y` pomocí možností v `Collator` objekt.  
  
 Výsledek porovnání bude:  
  
-   -1 v případě `x` před `y` v pořadí řazení.  
  
-   0 (nula) v případě `x` rovná `y` v pořadí řazení.  
  
-   v případě 1 `x` po `y` v pořadí řazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří `Collator` objektu a provede porovnání.  
  
```JavaScript  
var co = new Intl.Collator(["de-DE-u-co-phonebk"]);  
  
if (console && console.log) {  
    console.log(co.compare("a", "b")); // Returns -1  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Collator` objekty, které chcete řazení pole. Tento příklad ukazuje rozdíly specifická pro národní prostředí.  
  
```JavaScript  
var co1 = new Intl.Collator(["de-DE-u-co-phonebk"]);  
var co2 = new Intl.Collator(["de-DE"]);  
var co3 = new Intl.Collator(["en-US"]);  
  
var arr = ["ä", "ad", "af", "a"];  
  
if (console && console.log) {  
    console.log(arr.sort(co1.compare));  // Returns a,ad,ä,af  
    console.log(arr.sort(co2.compare));  // Returns a,ä,ad,af  
    console.log(arr.sort(co3.compare));  // Returns a,ä,ad,af  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `Collator` objekt, který chcete vyhledat řetězec.  
  
```JavaScript  
// String to search  
var arr = ["ä", "ad", "af", "a"];  
// String searched for  
var s = "af";  
  
var co = new Intl.Collator("de-DE", { usage: "search" });  
var matches = arr.filter(function (i) {  
    return co.compare(i, s) === 0;  
});  
  
if (console && console.log) {  
    console.log(matches);  // Returns af  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Intl.collator – objekt](../../javascript/reference/intl-collator-object-javascript.md)