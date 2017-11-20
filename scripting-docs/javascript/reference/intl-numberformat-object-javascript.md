---
title: "Intl.numberFormat – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: NumberFormat
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 820bc90f-f1e7-457a-b90d-487dfc3a736d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dcb02dbe0d7a7eef88750c440a4fbcdde3ea7ee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="intlnumberformat-object-javascript"></a>Intl.NumberFormat – objekt (JavaScript)
Poskytuje formátování čísel specifická pro národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
numberFormatObj = new Intl.NumberFormat([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametry  
 `numberFormatObj`  
 Požadováno. Název proměnné přiřadit `NumberFormat` do objektu.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript. Další informace naleznete v části Poznámky.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které určují možnosti formátování čísel. Najdete v části poznámky podrobnosti.  
  
## <a name="remarks"></a>Poznámky  
 `locales` Musí odpovídat parametr [BCP 47](http://tools.ietf.org/html/rfc5646) značky jazyk nebo národní prostředí, například "en US" a "zh-CN". Značky mohou zahrnovat jazyka, oblasti, země a typu variant. Příklady značky jazyka najdete v tématu [příloha A](http://tools.ietf.org/html/rfc5646#appendix-A) 47 BCP. Pro `NumberFormat`, můžete přidat **-u** podznačky následuje - nu k určení číslování rozšíření systému:  
  
 "*jazyk*-*oblast*-u – nu -*numberingsystem*"  
  
 kde *numberingsystem* může být jeden z následujících: Arabské, arabext, bali, beng, Devy, fullwide, gujr, guru, hanidec, khmr, knda, laoo, latn, končetiny, mylm, mong, mymr, orya, tamldec, telu, thajštině, tibt.  
  
 `options` Parametru může zahrnovat následující vlastnosti:  
  
|Vlastnost|Popis|Možné hodnoty|Výchozí hodnota|  
|--------------|-----------------|---------------------|-------------------|  
|`localeMatcher`|Určuje algoritmus porovnávání národního prostředí použít.|"vyhledávání", "nejvhodnější"|"nejvhodnější"|  
|`style`|Určuje styl číslo formátu.|Měna""decimal","procent,""|"decimal"|  
|`currency`|Určuje hodnotu měny ISO 4217 jako abecední kód. Pokud `style` je nastaven na "Měna", tato hodnota je vyžadována.|V tématu ISO [měny a fondů kódem seznamu](http://www.currency-iso.org/en/home/tables/table-a1.html).|Nedefinovaná|  
|`currencyDisplay`|Určuje, jestli se zobrazuje jako zadání kódu ISO 4217 abecedním měny, symbol lokalizovaný Měna nebo lokalizovaný měna název měny. Tato hodnota se používá pouze v případě `style` je nastaven na "Měna".|"kód", "symbol", "název"|"symbol"|  
|`useGrouping`|Určuje, zda má být použita oddělovač seskupení.|Hodnota TRUE, false|`true`.|  
|`minimumIntegerDigits`|Určuje minimální počet číslic integrální používat.|1 až 21.|21|  
|`minimumFractionDigits`|. Určuje minimální počet míst za desetinnou čárkou, který se má použít.|0 – 20.|0|  
|`maximumFractionDigits`|Určuje maximální počet míst za desetinnou čárkou, který se má použít.|Tato hodnota může být v rozsahu od `minimumFractionDigits` až 20 číslic.|20.|  
|`minimumSignificantDigits`|Určuje minimální počet míst za desetinnou čárkou, která se má zobrazit.|Tato hodnota musí být v rozsahu 1 až 21.|1|  
|`maximumSignificantDigits`|Určuje maximální počet míst za desetinnou čárkou, která se má zobrazit.|Tato hodnota může být v rozsahu od `minimumSignificantDigits` do 21.|21|  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `NumberFormat` objektu.  
  
|||  
|-|-|  
|Vlastnost|Popis|  
|[Konstruktor](../../javascript/reference/constructor-property-intl-numberformat.md)|Určuje funkce, která vytvoří objekt formátování čísel.|  
|[Formát](../../javascript/reference/format-property-intl-numberformat.md)|Vrátí funkci, která formátuje číslo pomocí nastavení formátování čísel.|  
|[prototyp](../../javascript/reference/prototype-property-intl-numberformat.md)|Vrátí odkaz na prototypu pro formátování čísel.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `NumberFormat` objektu.  
  
|||  
|-|-|  
|Metoda|Popis|  
|[resolvedoptions –](../../javascript/reference/resolvedoptions-method-intl-numberformat.md)|Vrátí objekt obsahující vlastnosti a hodnoty objektu formátování čísel.|  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří `NumberFormat` objekt pro národní prostředí cs cz pomocí zadané možnosti formátování.  
  
```JavaScript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigit: 1  
});  
  
if (console && console.log) {  
    console.log(nf.format(100)); // Returns ¥100.00  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklady ukazují výsledek pomocí několika různých národní prostředí a možnosti.  
  
```JavaScript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
if (console && console.log) {  
    console.log(new Intl.NumberFormat("en-US").format(number));  
    // Returns 123,456,789  
    console.log(new Intl.NumberFormat("ja-JP").format(number));  
    // Returns 123,456,789  
    console.log(new Intl.NumberFormat("ar-SA", options1).format(number));  
    // Returns ١٢,٣٤٥,٦٧٨,٩٠٠ %  
    console.log(new Intl.NumberFormat("hi-IN", options2).format(number));  
    // Returns ₹ 12,34,56,789.00  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toLocaleString (Number)](../../javascript/reference/tolocalestring-number.md)   
 [Intl.collator – objekt](../../javascript/reference/intl-collator-object-javascript.md)   
 [Intl.DateTimeFormat – objekt](../../javascript/reference/intl-datetimeformat-object-javascript.md)