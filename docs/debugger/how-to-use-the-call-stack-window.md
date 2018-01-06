---
title: "Zobrazit zásobníku volání v ladicím programu sady Visual Studio | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 04/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.callstack
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
caps.latest.revision: "40"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e10b81ff07b77e2fd6202d2f5fb27392fe8134c2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="view-the-call-stack-and-use-the-call-stack-window-in-the-visual-studio-debugger"></a>Zobrazit zásobník volání a použití okna zásobník volání v ladicím programu sady Visual Studio

Pomocí **zásobníkem volání** okno, můžete zobrazit volání funkce nebo procedury, které jsou aktuálně v zásobníku. **Zásobníkem volání** okno zobrazuje pořadí, ve kterém jsou získávání volat metody a funkce. V zásobníku volání je dobrý způsob, jak prozkoumat a lépe pochopit tok spuštění aplikace.
  
Při [symboly ladění](#bkmk_symbols) nejsou k dispozici pro zásobník volání, jsou součástí **zásobníkem volání** okno nemusí být možné zobrazit správné informace pro tuto část zásobníku volání. Pokud k tomu dojde, zobrazí se následující zápis:  
  
`[Frames below may be incorrect and/or missing, no symbols loaded for name.dll]`

>  [!NOTE]
> **Zásobníkem volání** okno se podobá ladění perspektivy v některé integrovaného vývojového prostředí jako Eclipse. 

> [!NOTE]
>  Dialogová okna a příkazy nabídky, které vidíte může lišit od těch, které tu popsané, v závislosti na aktivním nastavení nebo edici. Chcete-li změnit nastavení, vyberte **nastavení importu a exportu** na **nástroje** nabídky.  V tématu [přizpůsobení integrovaného vývojového prostředí](../ide/personalizing-the-visual-studio-ide.md)
  
## <a name="view-the-call-stack-while-in-the-debugger"></a>Zobrazit zásobníku volání při v ladicím programu 
  
-   Při ladění ve **ladění** nabídce vyberte možnost **Windows > zásobníkem volání**.

 ![Okno zásobník volání](../debugger/media/dbg_basics_callstack_window.png "CallStackWindow")

Žlutá šipka identifikuje rámce zásobníku, kde se aktuálně nachází provádění ukazatele. Ve výchozím nastavení, to je rámce zásobníku, jehož informace se zobrazí ve zdroji, **místní hodnoty –**, **automobily**, **sledovat**, a **zpětný překlad** windows . Pokud chcete změnit na jiný rámec v zásobníku kontextu ladicího programu, můžete to udělat [přepnutí na jiný rámec zásobníku](#bkmk_switch).   
  
## <a name="display-non-user-code-in-the-call-stack-window"></a>Zobrazení kódu neuživatelských v okně zásobník volání  
  
-   Klikněte pravým tlačítkem myši **zásobníkem volání** a vyberte **zobrazit externí kód**.

Kód, který není zobrazena, pokud je kód neuživatelských [pouze můj kód](../debugger/just-my-code.md) je povoleno. Ve spravovaném kódu jsou ve výchozím nastavení skryté rámce bez uživatelského kódu. Následující zápis se zobrazí místo rámce bez uživatelského kódu:  
  
**[\<Externí kód >]**  
  
## <a name="bkmk_switch"></a>Přepnout na jiný rámec zásobníku (Změna kontextu ladicího programu)
  
1.  V **zásobníkem volání** okna, klikněte pravým tlačítkem na rámce zásobníku, jejíž kód a data, která chcete zobrazit.

    Nebo můžete dvakrát kliknout na snímek ve **zásobníkem volání** okna přepnout do vybraného rámce. 
  
2.  Vyberte **přepnout na rámce**.  
  
     Zelenou šipku s složené poškozené databáze se zobrazí vedle rámce zásobníku, který jste vybrali. Provádění ukazatel zůstane v původní rámce, který stále označeno žlutý šipku. Pokud vyberete **krok** nebo **pokračovat** z **ladění** nabídce spuštění bude pokračovat v původní rámečkem, není rámečku, jste vybrali.  
  
## <a name="view-the-source-code-for-a-function-on-the-call-stack"></a>Zobrazení zdrojového kódu pro funkce v zásobníku volání  
  
-   V **zásobníkem volání** okna, klikněte pravým tlačítkem na funkce, jejichž zdrojový kód je chcete zobrazit a vybrat **přejděte do zdrojového kódu**.

## <a name="run-to-a-specific-function-from-the-call-stack-window"></a>Spustit konkrétní funkce v okně zásobník volání  
  
-  V **zásobníkem volání** okně vyberte funkce, klikněte pravým tlačítkem myši a zvolte **spustit ke kurzoru**.  
  
## <a name="set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>Nastavit zarážky místo přechodu volání funkce  
  
-   V tématu [nastavit zarážky v zásobníku volání funkce](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_the_call_stack_window).

## <a name="display-calls-to-or-from-another-thread"></a>Zobrazení volání do nebo z jiného vlákna  
  
-   Klikněte pravým tlačítkem myši **zásobníkem volání** a vyberte **zahrnout další vláken To/From volání**.   
  
## <a name="visually-trace-the-call-stack"></a>Vizuální sledování zásobníku volání  

Pokud používáte Visual Studio Enterprise (pouze), můžete zobrazit map kódu pro zásobníku volání při ladění.

- V **zásobníkem volání** okno, otevřete v místní nabídce. Zvolte **zásobník volání zobrazit na mapě kódu**. (Klávesové: **CTRL** + **SHIFT** + **`**)  
  
    Podrobné informace najdete v tématu [mapování metod v zásobníku volání při ladění](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).

![Zásobník volání zobrazit na mapě kódu](../debugger/media/dbg_basics_show_call_stack_on_code_map.gif "ShowCallStackOnCodeMap")
  
## <a name="view-the-disassembly-code-for-a-function-on-the-call-stack"></a>Zobrazení zpětného překladu kódu pro funkce v zásobníku volání  
  
-   V **zásobníkem volání** okna, klikněte pravým tlačítkem na funkce, jejíž zpětný překlad kódu je chcete zobrazit a vybrat **přejděte k zpětný překlad**.    

## <a name="change-the-optional-information-displayed"></a>Změnit zobrazené volitelné informace  
  
-   Klikněte pravým tlačítkem myši **zásobníkem volání** okno a sadu zrušením zaškrtnutí **zobrazit \<**  *informace, které chcete*  **>** .  
  
## <a name="bkmk_symbols"></a>Zatížení symboly pro modul
V **zásobníkem volání** okně můžete načíst symboly pro kód, který momentálně nemá načíst symboly ladění. Tyto symboly může být rozhraní .NET Framework nebo symboly systému stáhli ze serverů Microsoft veřejné symbol nebo symboly v cestě symbol v počítači, který ladíte.  
  
V tématu [zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
### <a name="to-load-symbols"></a>Načtení symbolů  
  
1.  V **zásobníkem volání** okna, klikněte pravým tlačítkem na rámec zásobníku pro symboly, které nebyly načteny. Rámečku bude nedostupné.  
  
2.  Přejděte na příkaz **zatížení symboly** a pak klikněte na **servery symbolů Microsoft** (Pokud je k dispozici) nebo vyhledejte cestu symbol.  
  
### <a name="to-set-the-symbol-path"></a>Nastavení cesty symbol  
  
1.  V **zásobníkem volání** okně zvolte **Symbol nastavení** z místní nabídky.  
  
     **Možnosti** otevře se dialogové okno a **symboly** zobrazí se stránka.  
  
2.  Klikněte na tlačítko **symbolů nastavení**.  
  
3.  V **možnosti** dialogové okno pole, klikněte na ikonu složky.  
  
     V **symbolů umístění souborů (.pdb)** pole, zobrazí se kurzoru.  
  
4.  Zadejte název cesty adresáře na umístění symbolu v počítači, který ladíte. Pro místní a vzdálené ladění, jde o cestu v místním počítači.
  
5.  Klikněte na tlačítko **OK** zavřete **možnosti** dialogové okno.  
  
## <a name="see-also"></a>Viz také  
 [Smíšený kód a chybějící informace v okně zásobník volání](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Zadání symbolu (.pdb) a zdrojových souborů](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Použití zarážek](../debugger/using-breakpoints.md)