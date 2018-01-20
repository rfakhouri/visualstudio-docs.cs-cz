---
title: "Aktualizace aplikací UWP | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: ef42c0208b973707294a842376ef737216e13774
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="refresh-a-uwp-app-in-visual-studio"></a>Aktualizace aplikace UWP v sadě Visual Studio
  
 Můžete provádět změny kódu a ladění a potom aktualizujte aplikace pro UPW pomocí jazyka JavaScript výběrem **aplikace pro aktualizaci Windows** tlačítko **ladění** panelu nástrojů. Výběr toto tlačítko znovu načte aplikaci bez zastavení a spuštění ladicího programu. Funkce aktualizace umožňuje měnit kód HTML, CSS a JavaScript a rychle zobrazit výsledek. Tato funkce je podporována pro aplikace UWP.  
  
 Aktualizace není Udržovat stav vaší aplikace nebo odrážela tyto změny do vaší aplikace:  
  
-   Změny souboru manifestu balíčku, včetně změny zadané v manifestu balíčku bitové kopie.  
  
-   Odkaz na změny, jako je například přidávání nebo odebírání odkaz na sadu SDK, nebo změny Runtime součásti systému Windows (soubory .winmd).  
  
-   Změny prostředku, jako jsou například změny řetězců v .resjson soubory.  
  
-   Změny souborů projektu, jejichž výsledkem změny názvu cesty, nové soubory projektu nebo odstraněné soubory.  
  
-   Projektů a položek změny vlastností, jako jsou například změny na vybraná zařízení ladění, nebo změny akce balíčku pro soubor (v okně Vlastnosti).  
  
> [!IMPORTANT]
>  Pokud změníte odkazy, změnit manifest balíčku nebo provést další změny, zadaný v předchozím seznamu, budete muset zastavit a restartovat ladicího programu aktualizovat zdrojové soubory HTML, CSS a JavaScript.  
  
### <a name="to-refresh-an-app"></a>Aktualizace aplikace  
  
1.  S UWP projektem otevřeným v sadě Visual Studio, vyberte **místního počítače** jako cíl ladění.
  
     ![Vyberte možnost ladění cílového seznamu](../debugger/media/js_select_target.png "JS_Select_Target")  
  
3.  Stisknutím klávesy F5 a spusťte aplikaci v režimu ladění.  
  
4.  Umožňuje přepnout do sady Visual Studio. 
  
5.  Na domovské stránce aplikace UWP upravte některé HTML.
  
7.  Klikněte na tlačítko **aplikace pro aktualizaci Windows** tlačítka, který vypadá podobně jako tento: ![tlačítko aplikace aktualizovat Windows](../debugger/media/js_refresh.png "JS_Refresh"). (Nebo stisknutím klávesy F4.)  
  
8.  Umožňuje přepnout do aplikace. Aplikace je znovu a aktualizované HTML slouží k vykreslení aplikace.
  
## <a name="see-also"></a>Viz také  
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)