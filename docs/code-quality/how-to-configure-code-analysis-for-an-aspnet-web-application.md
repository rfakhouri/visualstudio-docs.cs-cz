---
title: "Postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.asp
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- aspnet
ms.openlocfilehash: 3d8d9b544b8cb4489ebfdfda8c6a237cb73c118f
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2018
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>Postupy: Konfigurace Analýzy kódu pro webovou aplikaci ASP.NET

V sadě Visual Studio, můžete vybrat ze seznamu analýza kódu *sad pravidel* použít [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Sada pravidel výchozí je Microsoft Minimální doporučená pravidla. Můžete vybrat jiné pravidlo nastavena na webovém serveru použít.

## <a name="to-configure-a-rule-set-for-an-aspnet-page-framework-project"></a>Chcete-li nakonfigurovat sadu pravidel pro projekt technologie ASP.NET

1. Vyberte web v **Průzkumníku řešení**.

2. Na **analyzovat** nabídky, klikněte na tlačítko **konfigurace analýzy kódu pro webovou stránku**.

3. Pokud jste vybrali řešení a řešení obsahuje více než jeden projekt, vyberte v sestavení konfigurace a cíle operačního systému z **konfigurace** a **platformy** uvádí.

4. Pro každý projekt v řešení, klikněte **sady pravidel** sloupec a potom klikněte na název pravidla nastaven na spouštění.

5. Analýza kódu je ve výchozím nastavení, spusťte na všechny projekty v řešení. Zakázání nebo povolení analýzy kódu pro konkrétní projekt, postupujte takto:

    1. Klikněte pravým tlačítkem na název projektu a pak klikněte na položku Vlastnosti.

    2. Zaškrtněte nebo zrušte zaškrtnutí **povolit analýza kódu** zaškrtávací políčko. Vám může také ruční spuštění analýzy kódu tak, že vyberete **spuštění analýzy kódu na webovém serveru** z **analyzovat** nabídky.

6. V **spuštění této sady pravidel** rozevírací seznam, postupujte takto:

    - Vyberte sadu pravidel, který chcete použít.

    - Vyberte  **\<procházet >** zadat existující vlastní pravidlo nastavit, který se nenachází v seznamu.

    - Definujte vlastní sady pravidel. Další informace najdete v tématu [vytváření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).