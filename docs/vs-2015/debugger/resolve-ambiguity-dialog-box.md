---
title: Vyřešit nejednoznačnosti – dialogové okno | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.Disambig
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 115c3dc86515f44d5b4be85b95e54ca62022efd1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49303183"
---
# <a name="resolve-ambiguity-dialog-box"></a>Dialogové okno Vyřešit nejednoznačnosti
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Resolve Ambiguity` Dialogové okno se zobrazí, když ladicí program nelze vybrat místa pro zobrazení. Například pokud použijete šablony jazyka C++, můžete vytvořit více funkcí z jedinou šablonu funkce. Pokud ladicí program se zastaví na umístění zdroje v šabloně, a vy zvolíte `Go To Disassembly`, ladicí program má několik možností. Každá funkce ze šablony má svůj vlastní zpětný překlad kódu a ladicí program neví, který kód chcete zobrazit. `Resolve Ambiguity` Dialogové okno umožňuje vybrat umístění, které chcete seznam všech odpovídajících místech.  
  
 `Choose the specific location`  
 Zobrazuje seznam všech umístění odpovídající svých rukou.  
  
 `Address`  
 Ukazuje adresy paměti pro každou funkci.  
  
 `Function`  
 Zobrazí název jednotlivých funkcí.  
  
 `Module`  
 Ukazuje modulu (EXE nebo DLL) obsahující objektový kód pro funkci.  
  
## <a name="see-also"></a>Viz také  
 [Výrazy v ladicím programu](../debugger/expressions-in-the-debugger.md)



