---
title: "Postupy: potlačení upozornění analýzy kódu pro vygenerovaný kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bd917c8c9a3b66dc1fe34e089e14481c2b7df5a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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