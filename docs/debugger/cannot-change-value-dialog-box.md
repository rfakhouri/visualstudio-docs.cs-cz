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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ca3f42f1fb4d02191e19655335189111f33c34fa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55009671"
---
# <a name="cannot-change-value-dialog-box"></a>Dialogové okno Nelze změnit hodnotu
## <a name="error"></a>Chyba  
 `The value of this variable cannot be changed` &#124;`The name` *název* `does not exist in the current context` &#124; *různé další zprávy*  
  
 Toto okno se zprávou se zobrazí, když se pokusíte změnit obsah proměnné na neplatnou hodnotu v okně ladicího programu (automatické hodnoty, sledování nebo lokální windows) nebo dialogového okna rychlého kukátka. Například pokud se pokusíte nastavit hodnotu proměnnou celého čísla na řetězec znaků, zobrazí se toto okno se zprávou.  
  
## <a name="solution"></a>Řešení  
 Ujistěte se, že vstup zadejte do okna ladicího programu nebo dialogového okna rychlého kukátka představuje platná hodnota pro proměnnou, kterou se pokoušíte nastavit.  
  
## <a name="see-also"></a>Viz také  
 [Výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md)