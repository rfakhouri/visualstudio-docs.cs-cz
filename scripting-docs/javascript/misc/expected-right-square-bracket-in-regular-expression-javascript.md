---
title: Byl očekáván ']' v regulárním výrazu (JavaScript) | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c49ab90dae8f30dae075906bb9c7ecb7881428f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60065074"
---
# <a name="expected--in-regular-expression-javascript"></a>V regulárním výrazu byl očekáván znak ']' (JavaScript)
Se pokusil vytvořit třídu znaků shody regulárního výrazu, ale neobsahuje pravou závorku. Jednotlivý znak literálu kombinace lze sestavit do třídy znaků tak, že je umístíte do hranatých závorek. Třída znaků odpovídá jeden libovolný znak, který ji obsahuje. Například / [abc] / odpovídá jakémukoli znaku z písmen "a", "b" nebo "c".  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Přidejte pravou závorku regulárnímu výrazu.  
  
    > [!NOTE]
    >  Pokud chcete odpovídat jedné závorky, před něj zpětné lomítko - \\[– aby nebyl interpretován jako znak zvláštní podle [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxe regulárního výrazu (JavaScript)](https://msdn.microsoft.com/library/1400241x)