---
title: Nelze změnit hodnotu – dialogové | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Cannot Change Value dialog box
- variables [debugger], editing
ms.assetid: 19e930c2-5fbf-4c83-aae8-a1dc3f8fcae8
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bfe275411346e499312ba51c50a3a2ac3f4ed7d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68161651"
---
# <a name="cannot-change-value-dialog-box"></a>Dialogové okno Nelze změnit hodnotu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chyba  
 `The value of this variable cannot be changed` &#124;`The name` *název* `does not exist in the current context` &#124; *různé další zprávy*  
  
 Toto okno se zprávou se zobrazí, když se pokusíte změnit obsah proměnné na neplatnou hodnotu v okně ladicího programu (automatické hodnoty, sledování nebo lokální windows) nebo dialogového okna rychlého kukátka. Například pokud se pokusíte nastavit hodnotu proměnnou celého čísla na řetězec znaků, zobrazí se toto okno se zprávou.  
  
## <a name="solution"></a>Řešení  
 Ujistěte se, že vstup zadejte do okna ladicího programu nebo dialogového okna rychlého kukátka představuje platná hodnota pro proměnnou, kterou se pokoušíte nastavit.  
  
## <a name="see-also"></a>Viz také  
 [Výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md)
