---
title: 'Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
ms.assetid: 618f6ff3-db0e-46cb-b08d-dfa35e62c9e7
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a37ededab38cf27a002117f874d17d6a340000d9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63429160"
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Postupy: Konfigurace analýzy kódu pro projekt spravovaného kódu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)] a [!INCLUDE[vsPro](../includes/vspro-md.md)], můžete vybrat ze seznamu analýzy kódu *sad pravidel* má použít pro spravovaný projekt kódu. Výchozí sada pravidel je Microsoft Minimální doporučená pravidla. Můžete použít jiné pravidlo nastavit do projektu nebo do všech projektů v řešení.  
  
> [!NOTE]
> Informace o tom, jak nakonfigurovat sadu pravidel pro webové aplikace ASP.NET najdete v tématu [jak: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).  
  
### <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Chcete-li konfigurovat sadu pravidel pro projekt rozhraní .NET Framework  
  
1. V **Průzkumníka řešení**, klikněte na projekt.  
  
2. Na **analyzovat** nabídky, klikněte na tlačítko **konfigurovat analýzu kódu pro** *ProjectName*.  
  
3. V **konfigurace** a **platformy** seznamy, klikněte na konfigurace a cílovou platformu sestavení.  
  
4. Chcete-li spustit nástroj Analýza kódu pokaždé, když se sestavení projektu použitím vybrané konfigurace, vyberte **povolit analýzu kódu na sestavení (definuje konstantu CODE_ANALYSIS)** zaškrtávací políčko. Můžete také spustit analýzu kódu ručně tak, že otevřete **analyzovat** nabídky a kliknutím na **spustit analýzu kódu na** *ProjectName*.  
  
5. Ve výchozím nastavení analýza kódu sestavu upozornění z kódu, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění z generovaného kódu, zrušte **potlačit Výsledky generovaného kódu** zaškrtávací políčko.  
  
    > [!NOTE]
    > Tato možnost není potlačit chyby analýzy kódu a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Můžete jak zobrazit a spravovat zdrojový kód pro formuláře nebo šablony.  
  
6. V **spustit tuto sadu pravidel** seznamu, proveďte jednu z následujících akcí:  
  
    - Klikněte na sadu pravidel, kterou chcete použít.  
  
    - Klikněte na tlačítko  **\<Procházet... >** zadat sadu existujících vlastních pravidel, která se nenachází v seznamu.  
  
    - Definujte vlastní sady pravidel.  
  
         Další informace najdete v tématu [vytvoření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
## <a name="see-also"></a>Viz také  
 [Návod: Nastavení konfigurace a používání vlastního pravidla](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)
