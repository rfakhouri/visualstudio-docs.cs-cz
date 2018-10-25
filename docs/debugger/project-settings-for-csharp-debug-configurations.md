---
title: Nastavení pro konfiguraci ladění jazyka C# projektu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: a65928e8a5a734e84d51cbb4368c7346ba8c2edb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49896338"
---
# <a name="project-settings-for--c-debug-configurations"></a>Nastavení projektu pro konfiguraci ladění jazyka C#
Můžete změnit nastavení projektu pro konfiguraci ladění jazyka C# v **stránky vlastností** okna, jak je popsáno v [konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md). Následující tabulky popisují, kde najít nastavení související s ladicí program v **stránky vlastností** okna.  
  
> [!WARNING]
>  Toto téma se nevztahuje na aplikacích pro UPW. Zobrazit [spustíte relaci ladění (VB, C#, C++ a XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
##  <a name="BKMK_Debug_tab"></a> Ladění kartu  
  
| **Nastavení** | **Popis** |
|-------------------------------------| - |
| **Konfigurace** | Nastaví režim pro kompilaci aplikace. Zvolte mezi **aktivní (ladění)**, **ladění**, **vydání**, **všechny konfigurace**. |
| **Spustit akci** | Tato skupina ovládacích prvků určuje akci, která bude vytvářena při výběru spuštění v nabídce ladění.<br /><br /> -   **Spustit projekt** je výchozí nastavení a spuštění projektu po spuštění pro ladění. Další informace najdete v tématu [výběr spouštěného projektu](/previous-versions/visualstudio/visual-studio-2010/0s590bew(v=vs.100)).<br />-   **Spustit externí program** umožňuje spuštění a připojení k programu, který není součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Další informace najdete v tématu [připojení ke spuštění programu](/previous-versions/visualstudio/visual-studio-2010/c6wf8e4z(v=vs.100)).<br />-   **Spustit prohlížeč v adrese URL** umožňuje ladění webové aplikace. |
| **Argumenty příkazového řádku** | Určuje argumenty příkazového řádku pro program k ladění. Název příkazu je zadané ve spuštění programu externí název programu. Pokud se spouštěcí akce nastavená na Otevřít adresu URL, nelze zadat argumenty příkazového řádku. |
| **Pracovní adresář** | Určuje pracovní adresář laděného programu. V [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], pracovní adresář je adresář spuštění aplikace z \bin\debug ve výchozím nastavení. |
| **Použití vzdáleného počítače** | Název vzdáleného počítače kde bude aplikace spuštěna, pro účely ladění nebo [název serveru Msvsmon](../debugger/remote-debugging.md). Umístění souboru exe ve vzdáleném počítači, je určené vlastností výstupní cestu ve složce vlastnosti konfigurace sestavení kategorie. Umístění musí být sdíleném adresáři na vzdáleném počítači. |
| **Povolit ladění nespravovaného kódu** | Umožňuje ladit volání nativního (nespravovaného) kódu Win32 z vaší spravované aplikace. |
| **Povolit ladění SQL serveru** | Umožňuje ladění objektů databáze systému SQL Server. |
  
##  <a name="BKMK_Build_tab"></a> Vytvořit kartu  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Symboly podmíněné kompilace:**|Zde jsou definovány konstanty ladění a trasování.<br /><br /> Tyto konstanty povolit podmíněné kompilace [Debug – třída](/dotnet/api/system.diagnostics.debug) a [Trasovací třída](/dotnet/api/system.diagnostics.trace). Pomocí těchto konstanty definované, ladění a trasování metody třídy generovat výstup do [okno výstup](../ide/reference/output-window.md). Bez těchto konstanty ladění a trasování metody třídy nejsou zkompilovány a nebude vygenerován žádný výstup.<br /><br /> -Debug je obvykle definované v ladicí verzi programu a nedefinované ve vydané verzi.<br />-Trasování je obvykle definováno v ladění i vydání verze.|  
|**Optimalizovat kód**|Pokud zjistíte chybu, která se zobrazí pouze v optimalizovaném kódu, nechte toto nastavení vypnuté v ladicí verzi. Optimalizovaný kód je těžší ladit, protože pokyny neodpovídají přímo pro příkazy ve zdrojových oknech.|  
|**Výstupní cesta:**|Nastavte obvykle bin\Debug pro ladění.|

> [!NOTE]
> Další informace o najdete v možnostech ladění **Upřesnit** tlačítko, naleznete v tématu [dialogové okno Upřesnit nastavení sestavení (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md). Přenosný formát pro soubory symbolů (PDB) je nejnovější formát pro různé platformy pro .NET Core. 
  
## <a name="see-also"></a>Viz také  
 [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)