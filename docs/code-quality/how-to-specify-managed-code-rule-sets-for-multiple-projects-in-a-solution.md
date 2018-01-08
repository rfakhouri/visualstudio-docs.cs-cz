---
title: "Postupy: určení sad pravidel spravovaného kódu pro více projektů v určitém řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.solution
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 346ddadef815f4926b0a87a924a502ab2184de3e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>Postupy: Určení sad pravidel spravovaného kódu pro více projektů v určitém řešení
Ve výchozím nastavení, všechny projekty, které jsou spravované řešení přiřazené analýza kódu Microsoft Minimální doporučená pravidla *sadu pravidel*. Sady pravidel, které jsou přiřazeny k projektům řešení v dialogovém okně Vlastnosti pro řešení, můžete změnit.  
  
> [!NOTE]
>  Analýza kódu projektu není ve výchozím nastavení spustí jako krok sestavení. Analýza kódu jako krok sestavení povolit, najdete v části [postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md).  
  
### <a name="to-specify-a-rule-set-for-multiple-projects-in-a-managed-code--solution"></a>Chcete-li určit sadu pravidel pro více projektů v určitém řešení pro spravovaný kód  
  
1.  V [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]. [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], nebo [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)] otevřete řešení.  
  
2.  Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro řešení**.  
  
3.  V případě potřeby rozbalte **společných vlastností**a potom klikněte na **nastavení analýzy kódu**.  
  
4.  Můžete zadat sadu pravidel pro jednoho nebo několika projektů.  
  
    -   Pokud chcete zadat sadu pravidel pro jednotlivé projektu, klikněte na název projektu.  
  
    -   Pokud chcete zadat sadu pravidel pro více projektů, podržte klávesu CTRL a klikněte na název projektu.  
  
    -   Chcete-li zadat všechny projekty v řešení, podržte stisknutou klávesu SHIFT a klikněte v seznamu projektu.  
  
5.  Klikněte **pravidlo nastavené** pole projektu a pak klikněte na název pravidla nastavit, že chcete použít.