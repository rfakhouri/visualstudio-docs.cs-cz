---
title: Aktualizace aplikace Windows 8.1 nebo aplikace UWP | Microsoft Docs
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
ms.openlocfilehash: c5f5592893452c3fdf7f535758f09d7877030c03
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="refresh-a-uwp-or-windows-81-app"></a>Aktualizujte UWP nebo aplikace Windows 8.1
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Můžete provádět změny kódu a ladění a potom aktualizujte aplikace pro UPW pomocí jazyka JavaScript výběrem **aplikace pro aktualizaci Windows** tlačítko **ladění** panelu nástrojů. Výběr toto tlačítko znovu načte aplikaci bez zastavení a spuštění ladicího programu. Funkce aktualizace umožňuje měnit kód HTML, CSS a JavaScript a rychle zobrazit výsledek. Tato funkce je podporována pro aplikace UWP a Windows 8.1.  
  
 Aktualizace není Udržovat stav vaší aplikace nebo odrážela tyto změny do vaší aplikace:  
  
-   Změny souboru manifestu balíčku, včetně změny zadané v manifestu balíčku bitové kopie.  
  
-   Odkaz na změny, jako je například přidávání nebo odebírání odkaz na sadu SDK, nebo změny Runtime součásti systému Windows (soubory .winmd).  
  
-   Změny prostředku, jako jsou například změny řetězců v .resjson soubory.  
  
-   Změny souborů projektu, jejichž výsledkem změny názvu cesty, nové soubory projektu nebo odstraněné soubory.  
  
-   Projektů a položek změny vlastností, jako jsou například změny na vybraná zařízení ladění, nebo změny akce balíčku pro soubor (v okně Vlastnosti).  
  
> [!IMPORTANT]
>  Pokud změníte odkazy, změnit manifest balíčku nebo provést další změny, zadaný v předchozím seznamu, budete muset zastavit a restartovat ladicího programu aktualizovat zdrojové soubory HTML, CSS a JavaScript.  
  
### <a name="to-refresh-an-app"></a>Aktualizace aplikace  
  
1.  V sadě Visual Studio vytvořte nový projekt pomocí šablony projektu aplikace navigace.  
  
     To může být aplikace pro UPW nebo aplikace Windows 8.1.  
  
2.  Pomocí šablony otevřete v sadě Visual Studio, vyberte cíl ladění.  
  
     Pokud projekt Windows Phone je vaše aktuální spouštěný projekt, vyberte emulátoru Windows Phone pro cíl ladění. Jinak vyberte možnost **simulátoru** nebo **místního počítače**.  
  
     ![Vyberte možnost ladění cílového seznamu](../debugger/media/js_select_target.png "JS_Select_Target")  
  
3.  Stisknutím klávesy F5 a spusťte aplikaci v režimu ladění.  
  
4.  Umožňuje přepnout do sady Visual Studio. (Stisknutím klávesy F12).  
  
5.  V **Průzkumníku řešení**v **stránky** > **domácí** složku, otevřete home.html.  
  
6.  Změňte text nadpisu stránky z  
  
    ```html  
    Welcome to yourAppName!  
    ```  
  
     na něco jiného, například takto:  
  
    ```html  
    Hello!  
    ```  
  
7.  Klikněte na tlačítko **aplikace pro aktualizaci Windows** tlačítka, který vypadá podobně jako tento: ![tlačítko aplikace aktualizovat Windows](../debugger/media/js_refresh.png "JS_Refresh"). (Nebo stisknutím klávesy F4.)  
  
8.  Umožňuje přepnout do aplikace. Aplikace je znovu bez restartování ladicího programu a zobrazí se název nové stránky.  
  
## <a name="see-also"></a>Viz také  
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)