---
title: "Nastavení pro konfiguraci ladění jazyka Visual Basic projektu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vbProjectPropertiesDebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- debugging [Visual Basic], debugger settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debug configurations, Visual Basic
ms.assetid: 72a8483a-af0b-4403-8b0d-ee9ad71ee435
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cc51c3d6525bcbecb0b0ef132aaa029ec7a9fcd
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="project-settings-for-a-visual-basic-debug-configuration"></a>Nastavení projektu pro konfiguraci ladění jazyka Visual Basic
Můžete změnit nastavení projektu pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] konfiguraci ladění v **stránky vlastností** okno, jak je popsáno v [konfigurace ladění a verzí](../debugger/how-to-set-debug-and-release-configurations.md). Následující tabulky popisují kde najít nastavení souvisejících s ladicí program v **stránky vlastností** okno.  
  
> [!WARNING]
>  Toto téma se nevztahuje na aplikace UWP. V tématu [spustit relaci ladění (jazyka Visual Basic, C#, C++ a XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)  
  
### <a name="debug-tab"></a>Karta Debug  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Konfigurace**|Nastaví režim kompilaci aplikace. Zvolte mezi **aktivní (ladění)**, **ladění**, **verze**, **všechny konfigurace**.|  
|**Zahájení**|Tato skupina ovládacích prvků určuje akci, která se stane, když vyberte počáteční z nabídky ladění.<br /><br /> -   **Spusťte projekt** je výchozí a spustí počáteční projekt pro ladění. Další informace najdete v tématu [NIB způsobu: nastavit projekty po spuštění](http://msdn.microsoft.com/en-us/31465836-0911-48db-a5d9-e456b635e970).<br />-   **Spuštění externího programu** umožňuje spustit a připojit k programu, který není součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Další informace najdete v tématu [přiřadit běžící procesy](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).<br />-   **Spustit prohlížeč v adrese URL** umožňuje ladění webové aplikace.|  
|**Argumenty příkazového řádku.**|Určuje argumenty příkazového řádku pro program, který má ladit. Název příkazu je název program zadaný v externí program spustit. Pokud je spuštění akce nastavená na Spustit adresu URL, argumenty příkazového řádku se ignorují.|  
|**Pracovní adresář**|Určuje pracovní adresář programu laděné. V [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], pracovní adresář je adresář je aplikace spuštěna z. Výchozí pracovní adresář je \bin\Debug nebo \bin\Release, v závislosti na aktuální konfiguraci.|  
|**Použití vzdáleného počítače**|Pokud je zaškrtnuté políčko, je povoleno vzdálené ladění. Do textového pole, můžete zadat název vzdáleného počítače kde bude aplikace spuštěna pro účely ladění nebo [název serveru Msvsmon](../debugger/remote-debugging.md). Umístění EXE ve vzdáleném počítači je zadána vlastnost výstupní cesta na kartě sestavení. Umístění musí být ke sdílení adresář ve vzdáleném počítači.|  
|**Ladění nespravovaného kódu**|Umožňuje ladění volání do nativního kódu (nespravovaný) Win32 ze spravované aplikace. Tato akce nemá stejný účinek jako výběr Mixed pro typ ladicí program v [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projektu.|  
|**Ladění SQL serveru**|Umožňuje ladění objektů databáze systému SQL Server.|  
  
### <a name="compile-tab-press-advanced-compile-options-button"></a>Kompilace karta: stiskněte tlačítko Upřesnit možnosti kompilace  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Povolit optimalizace**|Tuto možnost byste měli zaškrtnutí. Optimalizace způsobí, že kód, který je ve skutečnosti spuštěný se liší od zdrojového kódu zobrazená v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a proto znesnadňuje ladění. Pokud kód je optimalizovaná, nebudou se symboly načíst ve výchozím nastavení při ladění s pouze můj kód.|  
|**Generovat ladicí informace**|Definované ve výchozím nastavení ladění a vydání verze, toto nastavení (ekvivalentní kompilátoru možnost/Debug) vytvoří informace o ladění v čase vytvoření buildu. Ladicí program používá tyto informace zobrazit názvy proměnných a další informace ve formě užitečné při ladění. Pokud je váš program bez těchto informací, bude funkce ladicího programu omezené. Další informace najdete v tématu [/debug](/dotnet/visual-basic/reference/command-line-compiler/debug).|  
|**Definování ladění konstanta**|Definování tento symbol umožňuje podmíněné kompilace funkce výstup z [Debug – třída](/dotnet/api/system.diagnostics.debug). S Tento symbol definované, metody třídy ladění generovat výstup do [výstup – okno](../ide/reference/output-window.md). Bez tento symbol nejsou kompilovány metody třídy ladění a nevygeneruje žádný výstup. Tento symbol by měl být definována v ladicí verze a není definována ve verzi. Definování tento symbol v prodejní verzi vytvoří nepotřebné kód, který váš program zpomalí.|  
|**Definování trasování konstanta**|Definování tento symbol umožňuje podmíněné kompilace funkce výstup z [Trasovací třída](/dotnet/api/system.diagnostics.trace.aspx). S Tento symbol definované, metody třídy trasování generovat výstup do [výstup – okno](../ide/reference/output-window.md). Bez tento symbol nejsou kompilovány metody třídy trasování a nevygeneruje žádný výstup trasování. Ve výchozím nastavení pro ladění a vydání verze je definována tento symbol.|  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)