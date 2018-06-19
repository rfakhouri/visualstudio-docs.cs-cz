---
title: Intl.collator – objekt (JavaScript) | Microsoft Docs
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
- Collator
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: acbb9461-f956-4b5b-ae5f-6a47815ae15c
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9a41507face20285124257be95197ef5ea53ef6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791508"
---
# <a name="intlcollator-object-javascript"></a>Intl.Collator – objekt (JavaScript)
Poskytuje porovnání řetězců specifická pro národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
collatorObj = new Intl.Collator([locales][, options])  
```  
  
#### <a name="parameters"></a>Parametry  
 `collatorObj`  
 Požadováno. Název proměnné přiřadit `Collator` do objektu.  
  
 `locales`  
 Volitelné. Pole řetězců národního prostředí, které obsahují jednu nebo více značek pro jazyk nebo národní prostředí. Pokud zahrnete více než jeden řetězec národního prostředí, jejich seznam v sestupném pořadí podle priority tak, aby první položka je upřednostňovaný národní prostředí. Pokud tento parametr nezadáte, použije se výchozí národní prostředí runtime jazyka JavaScript. Další informace naleznete v části Poznámky.  
  
 `options`  
 Volitelné. Objekt, který obsahuje jednu nebo více vlastností, které zadejte možnosti porovnání. Najdete v části poznámky podrobnosti.  
  
## <a name="remarks"></a>Poznámky  
 `locales` Musí odpovídat parametr [BCP 47](http://tools.ietf.org/html/rfc5646) značky jazyk nebo národní prostředí, například "en US" a "zh-Hans-CN". Značky mohou zahrnovat jazyka, oblasti, země a typu variant. Seznam jazyků, najdete v článku [IANA jazyk podznačky registru](http://go.microsoft.com/fwlink/p/?linkid=227303). Příklady značky jazyka najdete v tématu [příloha A](http://tools.ietf.org/html/rfc5646#appendix-A) 47 BCP. Pro `Collator`, může zahrnovat -u rozšíření v řetězci národní prostředí zadejte jedno nebo více z následujících přípon Unicode:  
  
-   -co k určení variant kolace (specifické pro národní prostředí): "*jazyk*-*oblast*-u – co -*hodnotu*".  
  
-   -kn k určení číselné porovnání: "*jazyk*-*oblast*- u – kn – true &#124; false".  
  
-   -kf k určení, zda seřadíte velké nebo malé znaky: "*jazyk*-*oblast*- u-kf vyšší &#124; nižší &#124; false"). Toto rozšíření není aktuálně podporován.  
  
 Pokud chcete zadat číselné porovnání, můžete nastavit rozšíření -kn v řetězci národního prostředí nebo použít `numeric` vlastnost v `options` parametr. Pokud používáte `numeric` - kn hodnota vlastnosti, nebudou platit.  
  
 `options` Parametru může zahrnovat následující vlastnosti:  
  
-   `localeMatcher`. Určuje algoritmus porovnávání národního prostředí použít. Možné hodnoty jsou "vyhledávání" a "nejvhodnější". Výchozí hodnota je "nejlepší".  
  
-   `usage`. Určuje, zda je cílem porovnání řazení nebo vyhledávání. Možné hodnoty jsou "řazení" a "Vyhledat". Výchozí hodnota je "seřadit".  
  
-   `sensitivity`. Určuje kompletování velkých a malých písmen. Možné hodnoty jsou "základní", "zvýraznění", "případ" a "variant". Výchozí hodnota je `undefined`.  
  
-   `ignorePunctuation`. Určuje, zda je v porovnání ignorován interpunkce. Možné hodnoty jsou "true" a "false". Výchozí hodnota je `false`.  
  
-   `numeric`. Určuje, jestli se používá číselnou řazení. Možné hodnoty jsou "true" a "false". Výchozí hodnota je `false`.  
  
-   `caseFirst`. Není aktuálně podporováno.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Collator` objektu.  
  
|||  
|-|-|  
|Vlastnost|Popis|  
|[porovnání](../../javascript/reference/compare-property-intl-collator.md)|Vrátí funkci, který porovnává dva řetězce pomocí kompletování pořadí řazení.|  
|[Konstruktor](../../javascript/reference/constructor-property-intl-collator.md)|Určuje funkce, která vytvoří kompletování.|  
|[prototyp](../../javascript/reference/prototype-property-intl-collator.md)|Vrátí odkaz na prototypu pro kompletování.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Collator` objektu.  
  
|||  
|-|-|  
|Metoda|Popis|  
|[resolvedoptions –](../../javascript/reference/resolvedoptions-method-intl-collator.md)|Vrátí objekt obsahující vlastnosti a hodnoty kompletování.|  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří `Collator` objektu a provede porovnání.  
  
```JavaScript  
var co = new Intl.Collator(["de-DE"]);  
co.compare("a", "b"); // Returns -1  
  
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
 Následující příklad používá `Collator` objektu pro hledání řetězce a určuje porovnání možnosti.  
  
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
 [localeCompare – metoda (String)](../../javascript/reference/localecompare-method-string-javascript.md)   
 [Intl.DateTimeFormat – objekt](../../javascript/reference/intl-datetimeformat-object-javascript.md)   
 [Intl.numberFormat – objekt](../../javascript/reference/intl-numberformat-object-javascript.md)