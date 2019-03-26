---
title: Vícesouborové DSL v jediném řešení
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8c894ce7466c253916794495649fa65d703e6d67
ms.sourcegitcommit: 489aca71046fb6e4aafd0a4509cd7dc149d707b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/25/2019
ms.locfileid: "58416146"
---
# <a name="multiple-dsls-in-one-solution"></a>Vícesouborové DSL v jediném řešení

Jako součást jediného řešení můžete zabalit několik DSL, tak, že jsou nainstalovány společně.

Můžete použít několik technik k integraci vícesouborové DSL. Další informace najdete v tématu [integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md) a [jak: Přidání obslužné rutiny operace přetažení myší](../modeling/how-to-add-a-drag-and-drop-handler.md) a [přizpůsobení chování kopírování](../modeling/customizing-copy-behavior.md).

## <a name="build-more-than-one-dsl-in-the-same-solution"></a>Sestavení více než jednom DSL ve stejném řešení

1. Vytvořte nový **projekt VSIX** projektu.

2. Vytvoření dvou nebo více projektů DSL v adresáři řešení VSIX.

   - Pro každý DSL otevřete novou instanci sady Visual Studio. Vytvořte nový DSL a zadejte stejnou složku řešení jako řešení VSIX.

   - Ujistěte se, že vytvoření každé DSL s příponou jiný název souboru.

   - Změna názvů **Dsl** a **DslPackage** projekty tak, aby byly všechny různé. Příklad: `Dsl1`, `DslPackage1`, `Dsl2`, `DslPackage2`.

   - V každém **DslPackage\*\source.extension.tt**, aktualizujte tohoto řádku na správný název projektu Dsl:

      `string dslProjectName = "Dsl2";`

   - Do řešení VSIX, přidejte Dsl * a DslPackage\* projekty. Můžete chtít umístit každý pár ve vlastní složce řešení.

2. Kombinovat manifestu VSIX DSL:

   1.  Open _YourVsixProject_**\source.extension.manifest**.

   2.  Pro každý DSL, zvolte **přidat obsah** a přidejte:

       -   `Dsl*` projekt jako **Komponenta MEF**

       -   `DslPackage*` projekt jako **Komponenta MEF**

       -   `DslPackage*` projekt jako **balíček VS**

3. Sestavte řešení.

   Výsledný VSIX nainstaluje i DSL. Můžete otestovat pomocí klávesy F5 nebo nasadit _YourVsixProject_**\bin\Debug\\\*VSIX**.

## <a name="see-also"></a>Viz také:

- [Integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md)
- [Postupy: Přidání obslužné rutiny operace podporující přetahování](../modeling/how-to-add-a-drag-and-drop-handler.md)
- [Přizpůsobení chování kopírování](../modeling/customizing-copy-behavior.md)