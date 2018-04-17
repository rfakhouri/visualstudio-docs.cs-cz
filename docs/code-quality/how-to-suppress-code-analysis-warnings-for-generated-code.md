---
title: 'Postupy: potlačení upozornění analýzy kódu pro vygenerovaný kód | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a44dae0dce544a4783be3068cbd52d7b9825e4bd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Postupy: Potlačení upozornění Analýzy kódu pro vygenerovaný kód
Spravovaný kód kompilátory často generovat kód, který se přidá do projektu usnadňuje vývoj rychlé kódu. Kromě toho vývojáři často používat nástroje třetích stran pomohou rychle vyvíjet aplikace. Tyto nástroje také generovat kód, který se přidá do projektu.  
  
 Můžete chtít najdete v části porušení pravidel, které zjistí analýza kódu generovaného kódu. Nemusí ale chcete zobrazovat v případě, že nelze zobrazit a spravovat kód, který obsahuje porušení zásady.  
  
 **Potlačit výsledky z generovaného kódu** zaškrtnutí políčka na stránce vlastností analýzy kódu projektu umožňuje vybrat, zda chcete zobrazit upozornění analýzy kódu z kód vygenerovaný nástroj třetí strany.  
  
> [!NOTE]
>  Tato možnost není analýza kódu chyby a upozornění z generovaného kódu při potlačit chyby a upozornění se zobrazí ve formulářích a šablony. Můžete zobrazit i udržovat zdrojový kód pro formuláře nebo šablony.  
  
### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>K potlačení upozornění pro vygenerovaný kód v projektu  
  
1.  Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a pak klikněte na **vlastnosti**.  
  
2.  Klikněte na tlačítko **analýza kódu**.  
  
3.  Vyberte **potlačit výsledky z generovaného kódu** zaškrtávací políčko.