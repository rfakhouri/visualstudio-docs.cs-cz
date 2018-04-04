---
title: 'Postupy: Konfigurace analýzy kódu pro spravovaný projekt kódu | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
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
ms.openlocfilehash: 46d41b09f0f6639195613c8a4d9a08f952c79525
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
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

    - Definujte vlastní sady pravidel. Další informace najdete v tématu [vytváření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md).

## <a name="see-also"></a>Viz také

- [Návod: Konfigurace a používání vlastní sady pravidel](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)
- [Postupy: Konfigurace Analýzy kódu pro webovou aplikaci ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)