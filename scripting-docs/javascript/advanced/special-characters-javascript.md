---
title: "Speciální znaky (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- line terminator character
- white space character
- Unicode character
- escape sequence
- backslash (\)
ms.assetid: 3b38b1bd-1f0f-4748-b13e-55cab36fd126
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0eaae8dfc84d9a3be6db54c50558d4cf675a53a8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="special-characters-javascript"></a>Speciální znaky (JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]poskytuje řídicí sekvence, které lze zahrnout v řetězcích vytvořit znaky, které nelze zadat přímo.  
  
## <a name="remarks"></a>Poznámky  
 Hodnotu řetězce je řadu nula nebo více znaků Unicode (písmena, číslice a dalšími znaky). Textové literály jsou uzavřené v odpovídajícím jednoduché nebo dvojité uvozovky. Dvojité uvozovky, může být obsažený řetězec, který je uzavřen v jednoduchých uvozovkách. Jednoduché uvozovky může být obsažený řetězec, který je uzavřena v uvozovkách.  
  
 Řídicí sekvence může být reprezentovaný každý znak v řetězcový literál. Řídicí sekvence začíná zpětné lomítko (\\), informuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] překladač, že další znak je speciální znak.  
  
 Můžete zadat znak Unicode pomocí \u*hhhh* řídicí sekvenci, kdy *hhhh* se o hexadecimální číslo čtyř číslic. Řídicí sekvence Unicode může představovat libovolný znak 16 bitů. Další informace najdete v tématu [Unicode kód bodu řídicí sekvence](#CodePoint).  
  
 Můžete vytvořit jeden znak řídicí sekvence pro některé znaky. Například \t určuje znaku tabulátoru.  
  
## <a name="escape-sequences"></a>Řídicí sekvence  
 Následující tabulka uvádí několik příkladů řídicí sekvence znaků běžné.  
  
|Hodnota znak Unicode|Řídicí sekvence|Význam|Kategorie|  
|-----------------------------|---------------------|-------------|--------------|  
|\u0008|\b|Backspace||  
|\u0009|\t|Tabulátor|Prázdné znaky|  
|\u000A|\n|Řádek informačního kanálu (nový řádek)|Ukončení řádku|  
|\u000B|\v<br /><br /> (Viz poznámku za touto tabulkou.)|Vertikální tabulátor|Prázdné znaky|  
|\u000C|\f|řídicí znak|Prázdné znaky|  
|\u000D|\r|Návrat na začátek řádku|Ukončení řádku|  
|\u0020||Místo|Prázdné znaky|  
|\u0022|\\"|Dvojité uvozovky (")||  
|\u0027|\\'|Jednoduché uvozovky (')||  
|\u005C|\\\|Zpětné lomítko (\\)||  
|\u00A0||Pevné mezery|Prázdné znaky|  
|\u2028||Oddělovač řádků|Ukončení řádku|  
|\u2029||Oddělovač odstavců|Ukončení řádku|  
|\uFEFF||Značka pořadí bajtů|Prázdné znaky|  
  
 Sloupci kategorie určuje, zda znak je ukončovací znak mezery nebo řádku. [Trim – metoda (String)](../../javascript/reference/trim-method-string-javascript.md) odebere počátečních a koncových mezer a řádku ukončovací znaků z řetězce.  
  
 Zpětné lomítko, samotné slouží jako řídicí znak. Proto nelze zadat přímo jeden ve vašem skriptu. Pokud chcete zapsat zpětné lomítko, musíte zadat dva z nich společně (\\\\).  
  
> [!NOTE]
>  Počínaje [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)], prohlížeč nemůže identifikovat jako aplikace Internet Explorer testování pro rovnocennosti vertikální tabulátor (\v) a "v". V dřívějších verzích, výraz `"\v" === "v"` vrátí `true`. V [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)], vrátí výraz `false`.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje \\\ a \\' řídicí sekvence.  
  
### <a name="code"></a>Kód  
  
```JavaScript  
document.write('The image path is C:\\webstuff\\mypage\\gifs\\garden.gif.');  
document.write ("<br />");  
document.write('The caption reads, "After the snow of \'97. Grandma\'s house is covered."');  
```  
  
<a name="CodePoint"></a>   
## <a name="unicode-code-point-escape-sequences"></a>Unicode kód bodu řídicí sekvence  
 V [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)], plně podporuje kódování Unicode. Nejběžnější body kódu Unicode jsou reprezentované pomocí čtyř šestnáctkových číslic, například /u0009 pro znaku tabulátoru. Body astral kódu, které zahrnují všechny symboly, které vyžadují víc než čtyři šestnáctkových číslic, jsou nyní podporovány ve zjednodušené formátu. Ve formátu "\u {*codepoint*}", představovat úplnou sadu znaků Unicode ve formátu literálu. Například můžete k reprezentaci symbol "𠮷", použijte následující formát: "\u{20BB7}".  
  
 V následujícím příkladu kódu jsou všechny ekvivalentní řetězce. (\uD842\uDFB7 je metoda alternativní řešení Chcete-li určit tento symbol v předchozích verzích.)  
  
```JavaScript  
"\u{20BB7}"=="𠮷"=="\uD842\uDFB7"  
```  
  
 RegExp nyní zahrnuje /u příznaku pro povolení plnou podporu pro body astral kódu. V následujícím příkladu kódu, například příznak /u v odpovídajícím astral povoluje regulární výraz kódu body (období odpovídá jakémukoliv znaku v řetězci zadané).  
  
```JavaScript  
"𠮷".match(/./u)[0].length == 2  
```  
  
 Příznak /u umožňuje analýze nový formát \u{codepoint}), jako typu Unicode řídicí sekvenci. To je nezbytné, protože \u{xxxxx} bez /u příznak má jiný význam v regulárním výrazu.  
  
> [!NOTE]
>  Pro body astral kódu délka je vždy 2. To odpovídá chování v předchozích verzích.  
  
 Objekt String teď obsahuje dvě nové metody, String.codePointAt a String.fromcodepoint –, aby podporovaly astral kód body. Codepointat – můžete například použít vrátit bod kódu ekvivalentní pro symbol "𠮷".  
  
```JavaScript  
"𠮷".codePointAt(0) == 0x20BB7  
  
```  
  
 Můžete také iterovat body kódu pomocí `for...of` příkaz.  
  
```JavaScript  
for(var c of "𠮷") {  
    console.log(c);  
}  
  
```  
  
## <a name="see-also"></a>Viz také  
 [String.fromCharCode – funkce](../../javascript/reference/string-fromcharcode-function-javascript.md)