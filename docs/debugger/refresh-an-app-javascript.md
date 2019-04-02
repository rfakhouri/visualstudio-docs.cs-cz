---
title: Aktualizace aplikace pro UPW | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- JavaScript debugging, refreshing pages [UWP apps]
- debugging, refreshing pages [UWP apps]
- DOM Explorer, Refresh [UWP apps]
- Refresh [UWP apps]
ms.assetid: fd99ee60-fa94-46df-8b17-369f60bfd908
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- uwp
ms.openlocfilehash: 751deec205eabb8bc6e4a492c7242095b2d67475
ms.sourcegitcommit: d4bea2867a4f0c3b044fd334a54407c0fe87f9e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58790287"
---
# <a name="refresh-a-uwp-app-in-visual-studio"></a>Aktualizace aplikace pro UPW v sadě Visual Studio

 Můžete provedete změny kódu během ladění a pak aktualizujte aplikace pro UPW pomocí jazyka JavaScript výběrem **aktualizovat Windows app** tlačítko **ladění** nástrojů. Výběrem tohoto tlačítka znovu načte aplikace bez zastavení a restartování ladicího programu. Funkce aktualizace umožňuje upravit kód HTML, CSS a JavaScriptu a rychle zobrazit výsledek. Tato funkce je podporována pro aplikace pro UPW.

 Aktualizaci nelze udržovat stav vaší aplikace nebo zahrnují následující změny do vaší aplikace:

-   Změny souboru manifestu balíčku, včetně změn imagí v manifestu balíčku.

-   Odkaz na změny, jako je například přidávání nebo odebírání odkaz na sadu SDK nebo změny součástí prostředí Windows Runtime (soubory .winmd).

-   Změny zdrojů, jako jsou například změny v souborech .resjson řetězce.

-   Soubor projektu se změní výsledek ve změně názvu cesty, nové soubory projektu nebo odstraněné soubory.

-   Projektů a položek změny vlastností, jako jsou například změny vybrané ladění zařízení, nebo změny akce balíčku souboru (v okně Vlastnosti).

> [!IMPORTANT]
>  Pokud změníte odkazy, změňte manifest balíčku nebo provést další změny, které uvedli v předchozím seznamu, budete muset zastavit a restartovat ladicí program k aktualizaci zdrojové soubory HTML, CSS a JavaScriptu.

### <a name="to-refresh-an-app"></a>Chcete-li aktualizovat aplikaci

1.  Otevřít v sadě Visual Studio projektu UPW, vyberte **místního počítače** jako cíl ladění.

     ![Seznam cílů ladění vyberte](../debugger/media/js_select_target.png "JS_Select_Target")

3.  Stisknutím klávesy F5 spusťte aplikaci v režimu ladění.

4.  Přepněte do aplikace Visual Studio.

5.  Na domovské stránce vaší aplikace pro UPW upravte některé HTML.

7.  Klikněte na tlačítko **aktualizovat Windows app** tlačítka, která vypadá přibližně takto: ![Aktualizovat aplikaci Windows](../debugger/media/js_refresh.png "JS_Refresh"). (Nebo stisknutím klávesy F4).

8.  Přepněte do aplikace. Aplikace je znovu načíst a aktualizované HTML se použije k vykreslení aplikace.

## <a name="see-also"></a>Viz také
- [Rychlý start: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)