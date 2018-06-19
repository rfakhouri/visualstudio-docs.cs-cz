---
title: Konfigurace analýzy kódu v sadě Visual Studio
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.csvb
- vs.codeanalysis.propertypages.solution
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: afa7a75ae083133f2cff1197b2aa111a1d7bf719
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31918753"
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Postupy: Konfigurace Analýzy kódu pro spravovaný projekt kódu

V sadě Visual Studio, můžete ze seznamu analýza kódu *sad pravidel* chcete použít pro spravovaný projekt kódu. Je sada pravidel výchozí *Microsoft Minimální doporučená pravidla*. Můžete použít jiné pravidlo nastaven na projektu nebo na všechny projekty v řešení.

> [!TIP]
> Informace o tom, jak nakonfigurovat sadu pravidel pro webové aplikace ASP.NET najdete v tématu [postupy: Konfigurace analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).

## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Chcete-li nakonfigurovat sadu pravidel pro rozhraní .NET Framework projektu

1. Otevřete **analýza kódu** karty na stránkách vlastností projektu. To provedete v některém z následujících způsobů:

   - V **Průzkumníku**, vyberte projekt. Na panelu nabídek vyberte **analyzovat** > **konfigurace analýzy kódu** > **pro \<název projektu >**.

   - Klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **vlastnosti**a pak vyberte **analýza kódu** kartě.

1. V **konfigurace** a **platformy** seznamy, vyberte platformu sestavení, konfiguraci a cíle.

1. Analýza kódu spustit v každém projektu je sestaven pomocí vybrané konfigurace, vyberte **povolit analýza kódu při sestavování** zaškrtávací políčko. Vám může také ruční spuštění analýzy kódu tak, že vyberete **analyzovat** > **spuštění analýzy kódu** > **spuštění analýzy kódu na \<název projektu >**.

1. Ve výchozím nastavení analýza kódu sestavu upozornění kód, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění generovaného kódu, zrušte **potlačit výsledky z generovaného kódu** zaškrtávací políčko.

    > [!NOTE]
    > Tato možnost není chyby analýzy kódu a upozornění z generovaného kódu při potlačit chyby a upozornění se zobrazí ve formulářích a šablony. Můžete zobrazit i udržovat zdrojový kód pro formuláře nebo šablony, bez nutnosti jej přepsat.

1. V **spuštění této sady pravidel** seznamu, proveďte jednu z následujících akcí:

    - Vyberte sadu pravidel, který chcete použít.

    - Vyberte  **\<Procházet... >** najít existující vlastní pravidlo nastavit, který se nenachází v seznamu.

    - Definování [vlastní sady pravidel](../code-quality/how-to-create-a-custom-rule-set.md).

## <a name="specify-rule-sets-for-multiple-projects-in-a-solution"></a>Zadejte sad pravidel pro více projektů v určitém řešení

Ve výchozím nastavení, jsou přiřazeny všechny spravované projekty řešení *Microsoft Minimální doporučená pravidla* code analysis sady pravidel. Sady pravidel, které jsou přiřazeny k projekty v řešení, můžete změnit **vlastnosti** dialogové okno pro řešení.

1. Otevřete řešení v sadě Visual Studio.

2. Na **analyzovat** nabídce vyberte možnost **konfigurace analýzy kódu pro řešení**.

3. V případě potřeby rozbalte **společných vlastností**a potom vyberte **nastavení analýzy kódu**.

4. Můžete určit sadu pravidel pro jednoho nebo několika projektů:

    - Pokud chcete zadat sadu pravidel pro jednotlivé projekt, vyberte název projektu.

    - Chcete-li zadat sadu pravidel pro více projektů, podržte klávesu **Ctrl** a vyberte názvy projektů.

    - Chcete-li zadat všechny projekty v řešení, podržte klávesu **Shift** a klikněte na projekt v okně.

5. Vyberte **pravidlo nastavené** pole projektu a pak vyberte název pravidla nastavit, kterou chcete použít.

## <a name="see-also"></a>Viz také

- [Postupy: Konfigurace Analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)