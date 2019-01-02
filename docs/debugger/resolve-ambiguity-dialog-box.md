---
title: Vyřešit nejednoznačnosti – dialogové okno | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.Disambig
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a31d217f8dc492468a894f78f10a4f7656677521
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53945064"
---
# <a name="resolve-ambiguity-dialog-box"></a>Dialogové okno Vyřešit nejednoznačnosti
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