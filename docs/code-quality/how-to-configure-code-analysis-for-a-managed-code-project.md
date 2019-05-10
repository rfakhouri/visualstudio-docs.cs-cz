---
title: Konfigurace analýzy kódu
ms.date: 04/04/2018
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.csvb
- vs.codeanalysis.propertypages.solution
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a17db8fbdb281139ba095070130e6c608954b5a7
ms.sourcegitcommit: 62f42113ae4dae1ddfff1c4e02445acc09913445
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/29/2019
ms.locfileid: "64878174"
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>Postupy: Konfigurace analýzy kódu pro projekt spravovaného kódu

V sadě Visual Studio, můžete ze seznamu analýzy kódu [sad pravidel](../code-quality/rule-set-reference.md) má použít pro spravovaný projekt kódu. Ve výchozím nastavení **Microsoft Minimální doporučená pravidla** je vybraná sada pravidel, můžete ale použít jinou sadu v případě potřeby pravidel. Sady pravidel lze použít na jeden nebo více projektů v řešení.

> [!TIP]
> Informace o tom, jak nakonfigurovat sadu pravidel pro webové aplikace ASP.NET najdete v tématu [jak: Konfigurace analýzy kódu pro ASP.NET web Application](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md).

## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>Chcete-li konfigurovat sadu pravidel pro projekt rozhraní .NET Framework

1. Otevřít **analýzy kódu** karty na stránkách vlastností projektu. Můžete to provést v jednom z následujících způsobů:

   - V **Průzkumníka řešení**, vyberte projekt. Na panelu nabídek vyberte **analyzovat** > **konfigurovat analýzu kódu** > **pro \<projectname >**.

   - Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a vyberte **vlastnosti**a pak vyberte **analýzy kódu** kartu.

1. V **konfigurace** a **platformy** seznamy, vyberte sestavení konfigurace a cílovou platformu.

1. Chcete-li spustit nástroj Analýza kódu pokaždé, když se sestavení projektu použitím vybrané konfigurace, vyberte **povolit analýzu kódu na sestavení** zaškrtávací políčko. Můžete také spustit analýzu kódu ručně tak, že vyberete **analyzovat** > **spustit analýzu kódu** > **spustit analýzu kódu na \<projectname >**.

1. Ve výchozím nastavení analýza kódu sestavu upozornění z kódu, který je automaticky generován externí nástroje. Chcete-li zobrazit upozornění z generovaného kódu, zrušte **potlačit Výsledky generovaného kódu** zaškrtávací políčko.

    > [!NOTE]
    > Tato možnost není potlačit chyby analýzy kódu a upozornění z generovaného kódu při chyby a upozornění se zobrazí ve formulářích a šablony. Můžete jak zobrazit a spravovat zdrojový kód pro formuláře nebo šablony, aniž by ji přepsat.

1. V **spustit tuto sadu pravidel** seznamu, proveďte jednu z následujících akcí:

    - Vyberte sadu pravidel, který chcete použít.

    - Vyberte  **\<Procházet... >** najít stávající vlastní sadu pravidel, která se nenachází v seznamu.

    - Definování [vlastní sady pravidel](../code-quality/how-to-create-a-custom-rule-set.md).

## <a name="specify-rule-sets-for-multiple-projects-in-a-solution"></a>Určení sad pravidel pro více projektů v řešení

Ve výchozím nastavení, jsou přiřazeny všechny spravované projekty z řešení *Microsoft Minimální doporučená pravidla* sada pravidel analýzy kódu. Sady pravidel, které jsou přiřazeny k projektům v řešení můžete změnit **vlastnosti** dialogové okno pro řešení.

1. Otevřete řešení v sadě Visual Studio.

2. Na **analyzovat** nabídce vyberte možnost **konfigurovat analýzu kódu pro řešení**.

3. V případě potřeby rozbalit **společné vlastnosti**a pak vyberte **nastavení analýzy kódu**.

4. Můžete určit sadu pravidel pro jeden nebo více projektů:

    - Chcete-li určit sadu pravidel pro individuální projekt, vyberte název projektu.

    - Chcete-li určit sadu pravidel pro více projektů, podržte **Ctrl** a vyberte název projektu.

    - Chcete-li určit všechny projekty v řešení, podržte **Shift** a klikněte na tlačítko v seznamu projektu.

5. Vyberte **sady pravidel** pole projektu a pak vyberte název pravidla nastavit, že chcete použít.

## <a name="see-also"></a>Viz také:

- [Referenční dokumentace sady pravidel nástroje Analýza kódu](../code-quality/rule-set-reference.md)
- [Postupy: Konfigurace analýzy kódu pro ASP.NET web Application](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)
