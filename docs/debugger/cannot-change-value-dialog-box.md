---
title: Nelze změnit hodnotu – dialogové | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Cannot Change Value dialog box
- variables [debugger], editing
ms.assetid: 19e930c2-5fbf-4c83-aae8-a1dc3f8fcae8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fd6b184b72acc2ecd08123160a512e5473e6611
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53966544"
---
# <a name="cannot-change-value-dialog-box"></a>Dialogové okno Nelze změnit hodnotu
## <a name="error"></a>Chyba  
 `The value of this variable cannot be changed` &#124;`The name` *název* `does not exist in the current context` &#124; *různé další zprávy*  
  
 Toto okno se zprávou se zobrazí, když se pokusíte změnit obsah proměnné na neplatnou hodnotu v okně ladicího programu (automatické hodnoty, sledování nebo lokální windows) nebo dialogového okna rychlého kukátka. Například pokud se pokusíte nastavit hodnotu proměnnou celého čísla na řetězec znaků, zobrazí se toto okno se zprávou.  
  
## <a name="solution"></a>Řešení  
 Ujistěte se, že vstup zadejte do okna ladicího programu nebo dialogového okna rychlého kukátka představuje platná hodnota pro proměnnou, kterou se pokoušíte nastavit.  
  
## <a name="see-also"></a>Viz také  
 [Výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md)