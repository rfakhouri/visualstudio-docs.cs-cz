---
title: 'Postupy: Potlačení upozornění analýzy kódu pro vygenerovaný kód | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9949a72abc46f2212fe448e193a06cce90b6df7c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438977"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Postupy: Potlačení upozornění analýzy kódu pro vygenerovaný kód
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Spravovaný kód často vygeneruje kód, který se přidá do projektu k usnadnění vývoje rychlý kód. Kromě toho vývojáři často pomocí nástroje třetích stran vám pomůžou s vývojem aplikací rychle. Tyto nástroje také generovat kód, který je přidán do projektu.  
  
 Můžete chtít zobrazit porušení pravidel, které zjistí analýzy kódu v generovaném kódu. Ale nebudete chtít zobrazovat v případě, že nelze zobrazit a spravovat kód, který obsahuje porušení zásady.  
  
 **Potlačit Výsledky generovaného kódu** zaškrtávací políčko na stránce vlastností analýzy kódu projektu umožňuje vybrat, jestli chcete zobrazit upozornění analýzy kódu v kódu generovaném nástrojem třetích stran.  
  
> [!NOTE]
> Tato možnost nepotlačuje analýzy kódu chyby a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Můžete jak zobrazit a spravovat zdrojový kód pro formuláře nebo šablony.  
  
### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>Potlačit upozornění pro vygenerovaný kód v projektu  
  
1. Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a potom klikněte na tlačítko **vlastnosti**.  
  
2. Klikněte na tlačítko **analýza kódu**.  
  
3. Vyberte **potlačit Výsledky generovaného kódu** zaškrtávací políčko.
