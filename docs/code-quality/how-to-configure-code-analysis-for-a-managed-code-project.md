---
title: "Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
ms.assetid: 618f6ff3-db0e-46cb-b08d-dfa35e62c9e7
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d62957a75c844d736a1168010616d5cf2c795bee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Postupy: Konfigurace Analýzy kódu pro spravovaný projekt kódu
V [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] a [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], můžete ze seznamu analýza kódu *sad pravidel* chcete použít pro spravovaný projekt kódu. Sada pravidel výchozí je Microsoft Minimální doporučená pravidla. Můžete použít jiné pravidlo nastaven na projektu nebo na všechny projekty v řešení.  
  
> [!NOTE]
>  Informace o tom, jak nakonfigurovat sadu pravidel pro webové aplikace ASP.NET najdete v tématu [postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).  
  
### <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Chcete-li nakonfigurovat sadu pravidel pro rozhraní .NET Framework projektu  
  
1.  V **Průzkumníku**, klikněte na projekt.  
  
2.  Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro** *ProjectName*.  
  
3.  V **konfigurace** a **platformy** seznamy, klikněte na tlačítko sestavení konfigurace a cílové platformy.  
  
4.  Analýza kódu spustit v každém projektu je sestaven pomocí vybrané konfigurace, vyberte **povolit analýza kódu v sestavení (definuje CODE_ANALYSIS konstanta)** zaškrtávací políčko. Vám může také ruční spuštění analýzy kódu otevřením **analyzovat** nabídky a kliknutím na **spuštění analýzy kódu na** *ProjectName*.  
  
5.  Ve výchozím nastavení analýza kódu sestavu upozornění kód, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění generovaného kódu, zrušte **potlačit výsledky z generovaného kódu** zaškrtávací políčko.  
  
    > [!NOTE]
    >  Tato možnost není chyby analýzy kódu a upozornění z generovaného kódu při potlačit chyby a upozornění se zobrazí ve formulářích a šablony. Můžete zobrazit i udržovat zdrojový kód pro formuláře nebo šablony.  
  
6.  V **spuštění této sady pravidel** seznamu, proveďte jednu z následujících akcí:  
  
    -   Klikněte na tlačítko sada pravidel, která chcete použít.  
  
    -   Klikněte na tlačítko  **\<Procházet... >** zadat existující vlastní pravidlo nastavit, který se nenachází v seznamu.  
  
    -   Definujte vlastní sady pravidel.  
  
         Další informace najdete v tématu [vytváření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Konfigurace a používání vlastní sady pravidel](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)