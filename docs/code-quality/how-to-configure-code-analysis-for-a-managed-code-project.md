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
ms.openlocfilehash: a1b09b77eb051d32a3aabb929e9058786215cfb4
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551048"
---
# <a name="how-to-configure-legacy-analysis-for-managed-code"></a>Postupy: Konfigurace starší verze analýzy pro spravovaný kód

V sadě Visual Studio můžete zvolit ze seznamu [sad pravidel](../code-quality/rule-set-reference.md) analýzy kódu, které se mají použít pro projekt spravovaného kódu. Ve výchozím nastavení **Microsoft Minimální doporučená pravidla** je vybraná sada pravidel, můžete ale použít jinou sadu v případě potřeby pravidel. Sady pravidel lze použít na jeden nebo více projektů v řešení.

Informace o tom, jak nakonfigurovat sadu pravidel pro webové aplikace v ASP.NET, najdete [v tématu How to: Konfigurace analýzy kódu pro webovou aplikaci](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)v ASP.NET.

> [!NOTE]
> Tento článek se vztahuje na verzi Analysis pro starší verze, nikoli na [.NET Compiler Platform analyzátory kódu založené na](use-roslyn-analyzers.md)kódu, které po sestavení nespouštějí analýzu kódu.

## <a name="configure-a-rule-set-for-a-net-framework-project"></a>Konfigurace sady pravidel pro .NET Framework projekt

1. Otevřít **analýzy kódu** karty na stránkách vlastností projektu. Můžete to provést v jednom z následujících způsobů:

   - V **Průzkumníka řešení**, vyberte projekt. Na panelu nabídek vyberte **analyzovat** > **konfigurovat analýzu kódu** > **pro \<projectname >** .

   - Klikněte pravým tlačítkem na projekt v **Průzkumníka řešení** a vyberte **vlastnosti**a pak vyberte **analýzy kódu** kartu.

1. V **konfigurace** a **platformy** seznamy, vyberte sestavení konfigurace a cílovou platformu.

1. Chcete-li spustit nástroj Analýza kódu pokaždé, když se sestavení projektu použitím vybrané konfigurace, vyberte **povolit analýzu kódu na sestavení** zaškrtávací políčko. Můžete také spustit analýzu kódu ručně tak, že vyberete **analyzovat** > **spustit analýzu kódu** > **spustit analýzu kódu na \<projectname >** .

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
- [Postupy: Konfigurace analýzy kódu pro webovou aplikaci v ASP.NET](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)
