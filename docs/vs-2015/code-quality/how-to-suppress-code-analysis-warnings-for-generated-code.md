---
title: 'Postupy: potlačení upozornění analýzy kódu pro vygenerovaný kód | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a96434e-d419-43a7-81ba-95cccac835b8
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 81bb371a3e16236e22ab3a1fd4ac5ab431f61512
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667321"
---
# <a name="how-to-suppress-code-analysis-warnings-for-generated-code"></a>Postupy: Potlačení upozornění Analýzy kódu pro vygenerovaný kód
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: potlačení upozornění analýzy kódu pro kód generovaný](https://docs.microsoft.com/visualstudio/code-quality/how-to-suppress-code-analysis-warnings-for-generated-code).  
  
Spravovaný kód často vygeneruje kód, který se přidá do projektu k usnadnění vývoje rychlý kód. Kromě toho vývojáři často pomocí nástroje třetích stran vám pomůžou s vývojem aplikací rychle. Tyto nástroje také generovat kód, který je přidán do projektu.  
  
 Můžete chtít zobrazit porušení pravidel, které zjistí analýzy kódu v generovaném kódu. Ale nebudete chtít zobrazovat v případě, že nelze zobrazit a spravovat kód, který obsahuje porušení zásady.  
  
 **Potlačit Výsledky generovaného kódu** zaškrtávací políčko na stránce vlastností analýzy kódu projektu umožňuje vybrat, jestli chcete zobrazit upozornění analýzy kódu v kódu generovaném nástrojem třetích stran.  
  
> [!NOTE]
>  Tato možnost nepotlačuje analýzy kódu chyby a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Můžete jak zobrazit a spravovat zdrojový kód pro formuláře nebo šablony.  
  
### <a name="to-suppress-warnings-for-generated-code-in-a-project"></a>Potlačit upozornění pro vygenerovaný kód v projektu  
  
1.  Klikněte pravým tlačítkem na projekt v Průzkumníku řešení a potom klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **analýza kódu**.  
  
3.  Vyberte **potlačit Výsledky generovaného kódu** zaškrtávací políčko.



