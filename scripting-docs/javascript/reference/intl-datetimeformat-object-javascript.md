---
title: Intl.DateTimeFormat – objekt (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- DateTimeFormat
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: cc555ac2-f31c-4239-a612-b84c08e3a37f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c50d6d7d939ebe05ce3ff9b434111413803ea40
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792120"
---
# <a name="intldatetimeformat-object-javascript"></a>Intl.DateTimeFormat – objekt (JavaScript)
Poskytuje formátování místního data a času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
dateTimeFormatObj = new Intl.DateTimeFormat([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametry  
 `dateTimeFormatObj`  
 Požadováno. Název proměnné přiřadit `DateTimeFormat` do objektu.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript. Další informace naleznete v části Poznámky.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti formátování pro datum a čas. Najdete v části poznámky podrobnosti.  
  
## <a name="remarks"></a>Poznámky  
 `locales` Musí odpovídat parametr [BCP 47](http://tools.ietf.org/html/rfc5646) značky jazyk nebo národní prostředí, například "en US" a "zh-CN". Značky mohou zahrnovat jazyka, oblasti, země a typu variant. Příklady značky jazyka najdete v tématu [příloha A](http://tools.ietf.org/html/rfc5646#appendix-A) 47 BCP. Pro `DateTimeFormat`, můžete přidat **-u** podznačky v řetězci národního prostředí, která obsahuje jednu nebo obě z následujících přípon Unicode:  
  
-   -nu k určení číslování rozšíření systému: *jazyk*-*oblast*-u – nu -*numberingsystem*  
  
     kde *numberingsystem* může být jeden z následujících: Arabské, arabext, bali, beng, Devy, fullwide, gujr, guru, hanidec, khmr, knda, laoo, latn, končetiny, mylm, mong, mymr, orya, tamldec, telu, thajštině, tibt.  
  
-   certifikační autorita – k určení kalendáře: *jazyk*-*oblast*-u – certifikační autority -*kalendáře*  
  
     kde *kalendáře* může být jeden z následujících: buddhistický, čínština, Dan islámská, islamicc, japonština.  
  
 `options` Parametru může zahrnovat následující vlastnosti:  
  
|Vlastnost|Popis|Možné hodnoty|Výchozí hodnota|  
|--------------|-----------------|---------------------|-------------------|  
|`localeMatcher`|Určuje algoritmus porovnávání národního prostředí použít.|"vyhledávání", "nejvhodnější"|"nejvhodnější"|  
|`formatMatcher`|Určuje algoritmus odpovídající formát použitý.|"základní", "nejvhodnější"|"nejvhodnější"|  
|`hour12`|Určuje, jestli chcete použít formát, 12 hodin pro hodin.|`true`(pro formát 12 hodin) `false` (pro 24hodinovém formátu)||  
|`timeZone`|Určuje časové pásmo. Minimálně je vždy podporována "UTC".|Hodnota časového pásma, jako je například "UTC".|"UTC"|  
|`weekday`|Určuje formátování den v týdnu.|"zúžit", "krátkou", "dlouhé".|Nedefinovaná|  
|`era`|Určuje formátování národním prostředí.|"zúžit", "krátkou", "dlouhé"|Nedefinovaná|  
|`year`|Určuje formátování v roce.|"2číslice", "číselný"|Nedefinovaná nebo "číselné"|  
|`month`|Určuje formátování v měsíci.|"2číslice", "číselný", "úzké", "krátkodobých", "dlouho"|Nedefinovaná nebo "číselné"|  
|`day`|Určuje formátování dne.|"2číslice", "číselný"|Nedefinovaná nebo "číselné"|  
|`hour`|Určuje formátování hodiny.|"2číslice", "číselný"|Nedefinovaná|  
|`minute`|Určuje formátování minuty.|"2číslice", "číselný"|Nedefinovaná|  
|`second`|Určuje formátování druhý.|"2číslice", "číselný"|Nedefinovaná|  
|`timeZoneName`|Určuje formátování časového pásma. Tato vlastnost není aktuálně podporován.|"krátkou", "dlouhé".|Tato vlastnost není aktuálně podporován.|  
  
 Výchozí hodnoty pro `weekday`, `era`, `year`, `month`, `day`, `hour`, `minute`, a `second` jsou `undefined`. Pokud tyto vlastnosti nenastavíte, "číselné" formátování se používá pro `year`, `month`, a `day`.  
  
 Každé národní prostředí musí podporovat, minimálně, následujících formátů:  
  
-   den v týdnu, rok, měsíc, den, hodinu, minutu, sekundu  
  
-   den v týdnu, rok, měsíc, den  
  
-   rok, měsíc, den  
  
-   rok, měsíc  
  
-   měsíc, den  
  
-   hodinu, minutu, sekundu  
  
-   Hodina, minuta  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `DateTimeFormat` objektu.  
  
|||  
|-|-|  
|Vlastnost|Popis|  
|[Konstruktor](../../javascript/reference/constructor-property-intl-datetimeformat.md)|Určuje funkce, která vytvoří objekt formátování data a času.|  
|[Formát](../../javascript/reference/format-property-intl-datetimeformat.md)|Vrátí funkci, která zformátuje data specifická pro národní prostředí pomocí nastavení formátování data a času.|  
|[prototyp](../../javascript/reference/prototype-property-intl-datetimeformat.md)|Vrátí odkaz na prototypu pro formátování data a času.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `DateTimeFormat` objektu.  
  
|||  
|-|-|  
|Metoda|Popis|  
|[resolvedoptions –](../../javascript/reference/resolvedoptions-method-intl-datetimeformat.md)|Vrátí objekt obsahující vlastnosti a hodnoty objektu formátování data a času.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje výsledek předáním do objekt date `DateTimeFormat` pomocí různá národní prostředí.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
if (console && console.log) {  
    console.log(new Intl.DateTimeFormat("en-US").format(date));  
    // Returns ‎2‎/‎1‎/‎2013  
    console.log(new Intl.DateTimeFormat("ja-JP").format(date));  
    // Returns ‎2013‎年‎2‎月‎1‎日  
    console.log(new Intl.DateTimeFormat("ar-SA", options).format(date));  
    // Returns ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
    console.log(new Intl.DateTimeFormat("hi-IN", options).format(date));  
    // Returns ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří `DateTimeFormat` objekt, který určuje aktuální den v týdnu v dlouho formátu Arabština (Saúdská Arábie) národního prostředí, islámská kalendáře a Latin číslování systému.  
  
```JavaScript  
var dtf = new Intl.DateTimeFormat(["ar-SA-u-ca-islamic-nu-latn"], {  
    weekday: "long",  
    year: "numeric",  
    day: "numeric",  
    month: "long"  
});   
  
If (console && console.log) {  
    console.log(dtf.format(new Date()));  
    // Returns ‏الجمعة‏, ‏19‏ ‏رمضان‏, ‏1434  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toLocaleString (Date)](../../javascript/reference/tolocalestring-date.md)   
 [toLocaleDateString – metoda (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)   
 [toLocaleTimeString – metoda (Date)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)   
 [Intl.collator – objekt](../../javascript/reference/intl-collator-object-javascript.md)   
 [Intl.numberFormat – objekt](../../javascript/reference/intl-numberformat-object-javascript.md)