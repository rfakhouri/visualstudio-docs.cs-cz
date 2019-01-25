---
title: 'Postupy: Určení sad pravidel spravovaného kódu pro více projektů v řešení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.solution
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2bf83c66f86d516d18221d01470e125979d39349
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54757924"
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>Postupy: Určení sad pravidel spravovaného kódu pro více projektů v řešení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ve výchozím nastavení, jsou přiřazeny všechny spravované projekty řešení Microsoft Minimální doporučená pravidla analýzy kódu *sada pravidel, která*. Můžete změnit sady pravidel, které jsou přiřazeny k projektům řešení v dialogovém okně vlastností řešení.  
  
> [!NOTE]
>  Analýza kódu projektu není ve výchozím nastavení spustí jako krok sestavení. Chcete-li povolit analýzu kódu jako krok sestavení, přečtěte si téma [jak: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).  
  
### <a name="to-specify-a-rule-set-for-multiple-projects-in-a-managed-code--solution"></a>Chcete-li určit sadu pravidel pro více projektů v řešení pro spravovaný kód  
  
1.  V [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]. [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], nebo [!INCLUDE[vsPro](../includes/vspro-md.md)] otevřete řešení.  
  
2.  Na **analyzovat** nabídky, klikněte na tlačítko **konfigurovat analýzu kódu pro řešení**.  
  
3.  V případě potřeby rozbalit **společné vlastnosti**a potom klikněte na tlačítko **nastavení analýzy kódu**.  
  
4.  Můžete určit sadu pravidel pro jeden nebo více projektů.  
  
    -   Chcete-li určit sadu pravidel pro jednotlivé projektu, klikněte na název projektu.  
  
    -   Chcete-li určit sadu pravidel pro více projektů, podržte stisknutou klávesu CTRL a klikněte na název projektu.  
  
    -   Chcete-li určit všechny projekty v řešení, podržte klávesu SHIFT a klikněte na tlačítko v seznamu projektu.  
  
5.  Klikněte na tlačítko **sady pravidel** pole projektu a pak klikněte na název pravidla nastavit, že chcete použít.
