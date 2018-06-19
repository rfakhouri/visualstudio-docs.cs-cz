---
title: Použití polí (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- arrays [JavaScript]
- arrays [JavaScript], objects
ms.assetid: 785c5acd-b8b3-4152-af9a-dd42ecdd75ba
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c5218a8353a796128d8b672ecc781665c6bde20
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788787"
---
# <a name="using-arrays-javascript"></a>Použití polí (JavaScript)
Maticových v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] jsou *zhuštěných*. To znamená pokud máte pole s tři prvky, které jsou číslem 0, 1, 2, můžete vytvořit element 50 bez obav o elementy 3 až 49. Pokud má proměnná automatické délka pole (najdete v části [vnitřní objekty](../../javascript/intrinsic-objects-javascript.md) vysvětlení automatické monitorování délka pole), Délka proměnná se nastaví na 51, nikoli na 4. Můžete vytvořit pole, ve kterých nejsou žádné mezery v číslování elementů, ale nejste-li to požadováno.  
  
 V [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)], objekty a pole jsou téměř shodné s navzájem. Dva hlavní rozdíly jsou, není pole objektů nemají automatické length – vlastnost a pole nemají vlastnosti a metody objektu.  
  
## <a name="addressing-arrays"></a>Adresování pole  
 Pole vyřešíte pomocí hranatých závorek ([]), jak je znázorněno v následujícím příkladu. Hranaté závorky uzavřete číselnou hodnotu nebo výraz, který se vyhodnotí jako celé číslo.  
  
```JavaScript  
var entryNum = 5;  
  
sample = new Array();  
  
sample[1] = "Maple Street";  
sample[entryNum] = 25;  
  
document.write (sample[1]);  
document.write (" ");  
document.write (sample[entryNum]);  
  
// Output: Maple Street 25  
  
```  
  
## <a name="objects-as-associative-arrays"></a>Objekty jako asociativní pole  
 Obecně použít operátor tečky "." pro přístup k vlastnostem objektu. Například  
  
```JavaScript  
myObject.aProperty  
```  
  
 Název vlastnosti v tomto případě je identifikátor. Vlastnosti objektu se dostanete pomocí operátoru indexu ([]). V takovém případě jsou objekt práce jako *asociativní pole* v datových hodnoty jsou spojené s řetězci. Například  
  
```JavaScript  
myObject["aProperty"] // Same as above.  
```  
  
 Operátor index je běžně související s přístupem k prvků pole. Pokud se používá s objekty, index je řetězcový literál, který představuje název vlastnosti.  
  
 Všimněte si důležitých rozdílů mezi dvěma způsoby přístupu k vlastnosti objektu.  
  
1.  Název vlastnosti zacházet jako identifikátor (syntaxe tečku (.)) nelze nakládat jako data.  
  
2.  Název vlastnosti zacházet jako index (složené závorky ([]) syntaxe) smí uživatel manipulovat jako data.  
  
 Tento rozdíl je užitečné, když si nejste jisti, co názvy vlastností, které budou, dokud nebudou runtime (například když jsou vytváření objektů, které jsou založené na vstup uživatele). Chcete-li extrahovat všechny vlastnosti z asociativní pole, je nutné použít `for...in` smyčky.