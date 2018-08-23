---
title: Nelze změnit hodnotu – dialogové | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a464be8e52a96da027e26ae48c5efb73ca2b5bf3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633627"
---
# <a name="cannot-change-value-dialog-box"></a>Dialogové okno Nelze změnit hodnotu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [nelze změnit hodnotu – dialogové](https://docs.microsoft.com/visualstudio/debugger/cannot-change-value-dialog-box).  
  
Chyba  
 `The value of this variable cannot be changed` &#124;`The name` *název* `does not exist in the current context` &#124; *různé další zprávy*  
  
 Toto okno se zprávou se zobrazí, když se pokusíte změnit obsah proměnné na neplatnou hodnotu v okně ladicího programu (automatické hodnoty, sledování nebo lokální windows) nebo dialogového okna rychlého kukátka. Například pokud se pokusíte nastavit hodnotu proměnnou celého čísla na řetězec znaků, zobrazí se toto okno se zprávou.  
  
## <a name="solution"></a>Řešení  
 Ujistěte se, že vstup zadejte do okna ladicího programu nebo dialogového okna rychlého kukátka představuje platná hodnota pro proměnnou, kterou se pokoušíte nastavit.  
  
## <a name="see-also"></a>Viz také  
 [Výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md)



