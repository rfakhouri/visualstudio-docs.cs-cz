---
title: "Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 575b81e9c213e4025cd38921ad467869686d867c
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Postupy: Konfigurace Analýzy kódu pro spravovaný projekt kódu

V sadě Visual Studio, můžete ze seznamu analýza kódu *sad pravidel* chcete použít pro spravovaný projekt kódu. Sada pravidel výchozí je Microsoft Minimální doporučená pravidla. Můžete použít jiné pravidlo nastaven na projektu nebo na všechny projekty v řešení.  
  
> [!NOTE]
> Informace o tom, jak nakonfigurovat sadu pravidel pro webové aplikace ASP.NET najdete v tématu [postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).  
  
## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Chcete-li nakonfigurovat sadu pravidel pro rozhraní .NET Framework projektu  
  
1.  V **Průzkumníku**, klikněte na projekt.  
  
2.  Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro** *ProjectName*.  
  
3.  V **konfigurace** a **platformy** seznamy, klikněte na tlačítko sestavení konfigurace a cílové platformy.  
  
4.  Analýza kódu spustit v každém projektu je sestaven pomocí vybrané konfigurace, vyberte **povolit analýza kódu při sestavování** zaškrtávací políčko. Vám může také ruční spuštění analýzy kódu otevřením **analyzovat** nabídky a výběr ** spuštění analýzy kódu na * ProjectName ***.  
  
5.  Ve výchozím nastavení analýza kódu sestavu upozornění kód, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění generovaného kódu, zrušte **potlačit výsledky z generovaného kódu** zaškrtávací políčko.  
  
    > [!NOTE]
    > Tato možnost není chyby analýzy kódu a upozornění z generovaného kódu při potlačit chyby a upozornění se zobrazí ve formulářích a šablony. Můžete zobrazit i udržovat zdrojový kód pro formuláře nebo šablony, bez nutnosti jej přepsat.
  
6.  V **spuštění této sady pravidel** seznamu, proveďte jednu z následujících akcí:  
  
    -   Klikněte na tlačítko sada pravidel, která chcete použít.  
  
    -   Klikněte na tlačítko  **\<Procházet... >** zadat existující vlastní pravidlo nastavit, který se nenachází v seznamu.  
  
    -   Definujte vlastní sady pravidel.  
  
         Další informace najdete v tématu [vytváření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).  
  
## <a name="see-also"></a>Viz také

[Návod: Konfigurace a používání vlastní sady pravidel](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)