---
title: 'Postupy: Změna oboru názvů jazyka specifického pro doménu'
ms.date: 10/31/2018
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 16fec4cf6150fe0711812d9fabe57fc667e36eef
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993496"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Postupy: Změna oboru názvů jazyka specifického pro doménu

Můžete změnit obor názvů jazyka specifického pro doménu. Proveďte změnu v hodnotě **Průzkumník DSL**ve vlastnostech projektu balíček Dsl a v informacích o sestavení.

## <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Chcete-li změnit obor názvů jazyka specifického pro doménu

1. V **Průzkumník DSL**, vyberte **Dsl** uzlu.

2. V **vlastnosti** okno Změnit **Namespace** vlastnost.

3. Uložte řešení a transformaci šablon.

4. Na **projektu** nabídce zvolte **Dsl vlastnosti**.

   Zobrazí vlastnosti pro váš projekt.

5. Vyberte **aplikace** kartu.

6. Změnit **výchozí obor názvů** vlastnost na nový název oboru názvů.

7. Pokud chcete změnit název sestavení, změňte **vlastnost názvu sestavení.**

8. Pokud jste změnili název sestavení, otevřete DslPackage\Package.tt a aktualizovat tento řádek:

   `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Pokud jste napsali žádný vlastní kód, ujistěte se, že chcete-li změnit odkazy na obor názvů a třídy v souboru kódu.

10. Resetujte Visual Studio experimentální instanci aplikace.

    1. Odstranit **\Users\\** _{name}_ **\AppData\Local\Microsoft\VisualStudio\\\*Exp**.

    2. V Windows **Start** nabídce zvolte **všechny programy** > **Microsoft Visual Studio 2010 SDK** > **nástroje**  >  **Resetovat experimentální instanci**.

11. Na **sestavení** nabídce zvolte **znovu sestavit řešení**.

## <a name="see-also"></a>Viz také:

[Glosář nástrojů jazyka specifického pro doménu](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)