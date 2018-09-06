---
title: 'Postupy: Změna oboru názvů jazyka specifického pro doménu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: a237664a30dacf351edc048c82d8c9cdc304aa45
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775887"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Postupy: Změna oboru názvů jazyka specifického pro doménu
Můžete změnit obor názvů jazyka specifického pro doménu. Je nutné provést změny v **Průzkumník DSL**ve vlastnostech projektu balíček Dsl a v informacích o sestavení.

### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Chcete-li změnit obor názvů jazyka specifického pro doménu

1.  V **Průzkumník DSL**, klikněte na tlačítko **Dsl** uzlu.

2.  V **vlastnosti** okno Změnit **Namespace** vlastnost.

3.  Uložte řešení a transformaci šablon.

4.  Na **projektu** nabídky, klikněte na tlačítko **Dsl vlastnosti**.

     Zobrazí vlastnosti pro váš projekt.

5.  Klikněte na tlačítko **aplikace** kartu.

6.  Změnit **výchozí obor názvů** vlastnost na nový název oboru názvů.

7.  Pokud chcete změnit název sestavení, změňte **vlastnost názvu sestavení.**

8.  Pokud jste změnili název sestavení, otevřete DslPackage\Package.tt a aktualizovat tento řádek:

     `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Pokud jste napsali žádný vlastní kód, ujistěte se, že chcete-li změnit odkazy na obor názvů a třídy v souboru kódu.

10. Resetujte Visual Studio experimentální instanci aplikace.

    1.  Odstranit **\Users\\**_{name}_**\AppData\Local\Microsoft\VisualStudio\\\*Exp**

    2.  V Windows **Start** nabídce zvolte **všechny programy**, **Microsoft Visual Studio 2010 SDK**, **nástroje**, **resetovat Experimentální instanci**.

11. Na **sestavení** nabídce zvolte **znovu sestavit řešení**.

## <a name="see-also"></a>Viz také:

- [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)