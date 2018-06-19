---
title: toLocaleString (Number) | Microsoft Docs
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
ms.assetid: 42c05252-13c1-4943-b1a4-b33285aeab3e
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b5e6378ec94e032c908a3502c0324c2a5a91b26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791760"
---
# <a name="tolocalestring-number"></a>toLocaleString (Number)
Převádí číslo na řetězec pomocí zadané nebo aktuální národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
numberObj.toLocaleString([locales][, options])   
```  
  
#### <a name="parameters"></a>Parametry  
 `numberObj`  
 Požadováno. `Number` Objekt, který chcete převést.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti porovnání.  
  
## <a name="remarks"></a>Poznámky  
 Od verze aplikace Internet Explorer 11, `toLocaleString` používá `Intl.NumberFormat` interně k porovnání Ujistěte se, které doplní o podporu `locales` a `options` parametry. Další informace o těchto parametrů najdete v tématu [Intl.NumberFormat](../../javascript/reference/intl-numberformat-object-javascript.md).  
  
> [!IMPORTANT]
>  `locales` a `options` parametry nejsou podporovány ve všech režimech dokumentů a verze prohlížeče. Další informace najdete v části požadavky.  
  
> [!NOTE]
>  V případě vynechání `locales` parametr, použijte `toLocaleString` pouze zobrazíte výsledky pro uživatele; nikdy nepoužívejte k výpočtu hodnot v rámci skriptu, protože na vrácený výsledek je závislé na počítači (metoda vrátí aktuální národní prostředí).  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `toLocaleString` metoda bez parametrů.  
  
```JavaScript  
var n, s;  
n = new Number(100);  
s = "Current locale value is: ";  
s += n.toLocaleString();                 
document.write(s);  
  
// Output:  
// The value 100 as represented by the current locale.  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `toLocaleString` metoda s konkrétní možnosti porovnání a národní prostředí.  
  
```JavaScript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
document.write(number.toLocaleString("en-US"));  
// 123,456,789  
document.write(number.toLocaleString("ja-JP"));  
// 123,456,789  
document.write(number.toLocaleString("ar-SA", options1));  
// ١٢,٣٤٥,٦٧٨,٩٠٠ %  
document.write(number.toLocaleString("hi-IN", options2));  
// ₹ 12,34,56,789.00  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales`a `options` parametry:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toLocaleDateString – metoda (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)