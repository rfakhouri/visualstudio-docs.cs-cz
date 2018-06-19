---
title: Jaký & č. 39; s nové v jazyce JavaScript | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 342b68ef-df93-48c4-81de-bdf6b6ce58d9
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 540d10958a7f2d406a6d70a633fc09a2cada8f41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792150"
---
# <a name="what39s-new-in-javascript"></a>Jaký & č. 39; s nové v jazyce JavaScript
Tento dokument obsahuje seznam nových funkcí v jazyce JavaScript, které jsou podporovány v obou [Edge režimu](http://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx), [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)]a aplikace pro Windows Phone Store.  
  
 Chcete zjistit, které prvky JavaScript podporuje v režimu Edge, ale zastaralé v [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] aplikace, najdete v části [informace o verzi](../javascript/reference/javascript-version-information.md).  
  
> [!IMPORTANT]
>  Informace o tom, jak vytvořit [!INCLUDE[win8_appname_long](../javascript/includes/win8-appname-long-md.md)] a aplikace pro Windows Phone Store pomocí jazyka JavaScript, včetně informací o editoru Visual Studio JavaScript a další funkce, najdete v části [aplikace pro vývoj Windows Store pomocí sady Visual Studio 2013](http://go.microsoft.com/fwlink/p/?LinkID=238263).  
  
## <a name="new-features-in-javascript"></a>Nové funkce v jazyce JavaScript  
  
|Funkce|Popis|  
|-------------|-----------------|  
|Třídy|Podporuje nové syntaxe deklarace [třídy](../javascript/reference/class-statement-javascript.md).|  
|Lišící|[Lišící](../javascript/reference/promise-object-javascript.md) povolit jednodušší a čisticí asynchronní kódování. Promise konstruktory jsou podporovány, spolu s `all` a `race` pomocné metody.|  
|Iterátory|Nyní můžete iterovat přes iterable objekty (včetně polí, jako pole objektů a iterátory), vyvolání háku vlastní iterace s příkazy, které mají být provedeny pro hodnotu každé vlastnosti distinct. Další informace najdete v tématu [iterátory a generátory](../javascript/advanced/iterators-and-generators-javascript.md). **Poznámka:** generátory ještě nejsou podporovány.|  
|Šipka funkce|Funkce šipku (= >) poskytuje syntaxi ve zkráceném tvaru pro `function` – klíčové slovo, které funkce lexikální `this` vazby.|  
|Nové metody pro předdefinované objekty|[Objekt Array](../javascript/reference/array-object-javascript.md), [Math – objekt](../javascript/reference/math-object-javascript.md), [číslo objekt](../javascript/reference/number-object-javascript.md), [objekt objektu](../javascript/reference/object-object-javascript.md), a [řetězce objektu](../javascript/reference/string-object-javascript.md) předdefinované objekty zahrnují mnoho nových funkcí nástroje a pro manipulace a zkontrolujete data.|  
|Objekt literálu vylepšení|Objekty teď podporují počítaný vlastností, metoda stručným definice a syntaxi ve zkráceném tvaru pro vlastnosti, jehož hodnota je inicializováno proměnné se stejným názvem. Další informace najdete v tématu [vytváření objektů](../javascript/creating-objects-javascript.md).|  
|Proxy|[Proxy](../javascript/reference/proxy-object-javascript.md) povolit vlastní chování pro objekty.|  
|Parametry REST|Parametry REST umožňují zapnout po sobě jdoucích argumenty ve volání funkce na pole. Další informace najdete v tématu [funkce](../javascript/functions-javascript.md).|  
|Spread – operátor|[Šíření operátor](../javascript/reference/spread-operator-decrement-dot-dot-dot-javascript.md) (`...`) rozšíří iterable výrazy do jednotlivých argumenty. Například `a.b(...array)` je přibližně stejné jako `a.b.apply(a, array)`.|  
|Symboly|[Symbol](../javascript/reference/symbol-object-javascript.md) objekty povolit vlastnosti, které chcete přidat do stávajících objektů se možné narušení s existující vlastnosti objektu, žádné nezamýšleným viditelnost a žádné nekoordinovaná dodatky jiným kódem.|  
|Řetězce šablon|[Řetězce šablon](../javascript/advanced/template-strings-javascript.md) jsou textové literály, které umožňují výrazy a vyhodnotit a zřetězen s řetězcový literál.|  
|Vylepšení kódování Unicode|Byla vylepšena podpoře kódování Unicode. Nový formát řídicí sekvence například podporuje astral kód bodů (body kódu s více než čtyři šestnáctkové číslice). Další informace najdete v tématu [speciální znaky](../javascript/advanced/special-characters-javascript.md).|  
|WeakSet|A [WeakSet](../javascript/reference/weakset-object-javascript.md) je odkazováno na kolekci objektů, které budou uvolnění z paměti, pokud nejsou kdekoliv jinde.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace jazyka JavaScript](../javascript/javascript-language-reference.md)