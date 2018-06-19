---
title: Metody značek HTML (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- link method [JavaScript]
- blink method [JavaScript]
- fontsize method [JavaScript]
- italics method [JavaScript]
- sup method [JavaScript]
- anchor method [JavaScript]
- fixed method [JavaScript]
- fontcolor method [JavaScript]
- bold method [JavaScript]
- small method [JavaScript]
- HTML Tag methods [JavaScript]
- sub method [JavaScript]
- big method [JavaScript]
ms.assetid: 50376223-be95-4aa4-9147-9e738a5d3cfa
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7639bc609d8e9b7e4b212fe67ae40f81487d708e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791103"
---
# <a name="html-tag-methods-javascript"></a>Metody značek HTML (JavaScript)
Metody značek HTML můžete umístit elementů HTML kolem textu v `String` objektu.  
  
## <a name="syntax"></a>Syntaxe  
 Následující tabulka uvádí syntaxe a popis jednotlivých metod značky HTML.  
  
 Ve sloupci syntaxe `string1` je `String` objekt nebo literál.  
  
 Standardní sloupec zobrazuje informace o [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/?LinkId=199553) doporučení pro specifikaci HTML 4. "Nedoporučuje" označuje, že prvek HTML se nedoporučuje považuje stylů.  
  
|Syntaxe|Popis – metoda|Popis parametru|Standard|  
|------------|------------------------|---------------------------|--------------|  
|`string1`.Anchor (`name`)|Umístí HTML anchor, které má atribut NAME kolem textu.|`name` Parametr je text uvést do atribut názvu HTML anchor.||  
|`string1`.Big()|Umístí HTML \<BIG > značky kolem textu.||Nedoporučuje.|  
|`string1`.BLINK()|Umístí HTML \<BLINK > značky kolem textu. \<BLINK > značky není podporována v aplikaci Internet Explorer.||Není ve verzi standard|  
|`string1`.Bold()|Umístí HTML \<B > značky kolem textu.||Nedoporučuje.|  
|`string1`.fixed()|Umístí HTML \<TT > značky kolem textu.||Nedoporučuje.|  
|`string1`.fontcolor (`color`)|Umístí HTML \<písma > značky s atributem barvu kolem textu.|`color` Parametr je řetězcovou hodnotu obsahující šestnáctkové hodnoty nebo předdefinované název barvy. Názvy platnou barvu předdefinovaného závisí na [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hostitele prohlížeče a její verzi.|Zastaralé|  
|`string1`.FontSize (`size`)|Umístí HTML \<písma > značky s atributem velikost kolem textu.|`size` Parametr je celočíselná hodnota, která určuje velikost textu. Platné celé číslo hodnoty závisí na [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hostitele prohlížeče a její verzi.|Zastaralé|  
|`string1`.italics()|Umístí HTML \<I > značky kolem textu.||Nedoporučuje.|  
|`string1`.Link (`href`)|Umístí HTML anchor, které má atribut HREF kolem textu.|`href` Parametr je text uvést do atribut HREF HTML anchor.||  
|`string1`.Small()|Umístí HTML \<malé > značky kolem textu.||Nedoporučuje.|  
|`string1`.Strike()|Umístí HTML \<vytvořit > značky kolem textu.||Zastaralé|  
|`string1`.Sub()|Umístí HTML \<SUB > značky kolem textu.|||  
|`string1`.sup()|Umístí HTML \<SUP > značky kolem textu.|||  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li zjistit, zda byly pro řetězec již použity značky HTML se neprovádí žádné kontrola.  
  
## <a name="example"></a>Příklad  
 Následující příklady ukazují, jak používat metody značek HTML.  
  
```JavaScript  
// anchor method.  
var strVariable = "This is an anchor.";  
document.write(strVariable.anchor("Anchor1"));  
// Output: <A NAME="Anchor1">This is an anchor.</A>  
  
// big method.  
var strVariable = "This is a string.";  
document.write(strVariable.big());  
// Output: <BIG>This is a string.</BIG>  
  
//  blink method.  
var strVariable = "This is a string.";  
document.write(strVariable.blink());  
// Output: <BLINK>This is a string.</BLINK>  
  
//  bold method.  
var strVariable = "This is a string.";  
document.write(strVariable.bold());  
// Output: <B>This is a string.</B>  
  
//  fixed method.  
var strVariable = "This is a string.";  
document.write(strVariable.fixed());  
// Output: <TT>This is a string.</TT>  
  
//  fontcolor method.  
var strVariable = "This is a string.";  
document.write(strVariable.fontcolor("red"));  
// Output: <FONT COLOR="red">This is a string.</FONT>  
  
//  fontsize method.  
var strVariable = "This is a string.";  
document.write(strVariable.fontsize(-1));  
// Output: <FONT SIZE="-1">This is a string.</FONT>  
  
//  italics method  
var strVariable = "This is a string.";  
document.write(strVariable.italics());  
// Output: <I>This is a string.</I>  
  
//  link method.  
var strVariable = "This is a hyperlink.";  
document.write(strVariable.link("http://www.microsoft.com"));  
// Output: <A HREF="http://www.microsoft.com">This is a hyperlink.</A>  
  
//  small method.  
var strVariable = "This is a string.";  
document.write(strVariable.small());  
// Output: <SMALL>This is a string.</SMALL>  
  
//  strike method.  
var strVariable = "This is a string.";  
document.write(strVariable.strike());  
// Output: <STRIKE>This is a string.</STRIKE>  
  
//  sub method.  
var strVariable = "This is a string.";  
document.write(strVariable.sub());  
// Output: <SUB>This is a string.</SUB>  
  
//  sup method.  
var strVariable = "This is a string.";  
document.write(strVariable.sup());  
// Output: <SUP>This is a string.</SUP>  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [String – objekt](../../javascript/reference/string-object-javascript.md)