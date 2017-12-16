---
title: "Projekt nastavení pro konfiguraci ladění jazyka C# | Microsoft Docs"
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
- debug configurations, C#
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debugging [C#], debugger settings
ms.assetid: e30ca810-66e9-4d6e-9cf6-9f285cd0b100
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d588f43271b127c675a6ec2fdf9e55ef388eadf2
ms.sourcegitcommit: 1e08318a8a684b21609af7a5e48b56abcc3239e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/13/2017
---
# <a name="project-settings-for--c-debug-configurations"></a>Nastavení projektu pro konfiguraci ladění jazyka C#
Můžete změnit nastavení projektu pro konfiguraci ladění jazyka C# v **stránky vlastností** okno, jak je popsáno v [konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md). Následující tabulky popisují kde najít nastavení souvisejících s ladicí program v **stránky vlastností** okno.  
  
> [!WARNING]
>  Toto téma se nevztahuje na aplikace UWP a Windows 8.1. V tématu [spustit relaci ladění (jazyka Visual Basic, C#, C++ a XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_Debug_tab"></a>Karta Debug  
  
|**Nastavení**|**Popis**|  
|-----------------|---------------------|  
|**Konfigurace**|Nastaví režim kompilaci aplikace. Zvolte mezi **aktivní (ladění)**, **ladění**, **verze**, **všechny konfigurace**.|  
|**Zahájení**|Tato skupina ovládacích prvků určuje akci, která se stane, když vyberte počáteční z nabídky ladění.<br /><br /> -   **Spusťte projekt** je výchozí a spustí počáteční projekt pro ladění. Další informace najdete v tématu [výběr spouštěný projekt](http://msdn.microsoft.com/en-us/222e3f32-a6fe-4941-bf37-6b2a921129fd).<br />-   **Spuštění externího programu** umožňuje spustit a připojit k programu, který není součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Další informace najdete v tématu [připojení ke spuštění programu](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4).<br />-   **Spustit prohlížeč v adrese URL** umožňuje ladění webové aplikace.|  
|**Argumenty příkazového řádku.**|Určuje argumenty příkazového řádku pro program, který má ladit. Název příkazu je název program zadaný v externí program spustit. Pokud je spuštění akce nastavená na Spustit adresu URL, nelze zadat argumenty příkazového řádku.|  
|**Pracovní adresář**|Určuje pracovní adresář programu laděné. V [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], pracovní adresář je adresář je aplikace spuštěna z \bin\debug ve výchozím nastavení.|  
|**Použití vzdáleného počítače**|Název vzdáleného počítače kde bude aplikace spuštěna pro účely ladění nebo [název serveru Msvsmon](../debugger/remote-debugging.md). Umístění EXE ve vzdáleném počítači je zadána vlastnost výstupní cesta ve složce vlastnosti konfigurace, kategorie sestavení. Umístění musí být ke sdílení adresář ve vzdáleném počítači.|
|**Povolit ladění nespravovaného kódu**|Umožňuje ladění volání do nativního kódu (nespravovaný) Win32 ze spravované aplikace.|  
|**Povolit ladění na serveru SQL Server**|Umožňuje ladění objektů databáze systému SQL Server.|  
  
##  <a name="BKMK_Build_tab"></a>Karta sestavení  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Podmíněná kompilace symboly:**|Zde jsou definovány konstanty ladění a trasování.<br /><br /> Tyto konstanty povolit podmíněné kompilaci [Debug – třída](/dotnet/api/system.diagnostics.debug) a [Trasovací třída](/dotnet/api/system.diagnostics.trace). Pomocí těchto konstant definované, ladění a trasování metody třídy generovat výstup do [výstup – okno](../ide/reference/output-window.md). Bez těchto konstanty nejsou kompilovány metody třídy ladění a trasování a nevygeneruje žádný výstup.<br /><br /> -Debug je obvykle definováno v ladicí verze programu a není definována ve vydané verzi.<br />-Trasování je obvykle definováno v ladění a vydání verze.|  
|**Optimalizace kódu**|Pokud zjistíte, chyb, které se zobrazí jenom v optimalizovaný kód, nechte toto nastavení vypnuté v ladicí verzi. Optimalizovaný kód je těžší k ladění, protože pokyny neodpovídají přímo na příkazy v systému windows. zdroj.|  
|**Výstupní cesta:**|Obvykle nastavuje na bin\Debug pro ladění.|

> [!NOTE]
> Další informace o možnostech ladění zjistíte v **Upřesnit** tlačítko najdete v tématu [dialogové okno Upřesnit nastavení sestavení (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md). Přenosné formát souborů symbolu (.pdb) je nejnovější formát a platformy .NET Core. 
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)