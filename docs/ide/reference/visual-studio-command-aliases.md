---
title: "Aliasy příkazů sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aliases, Visual Studio commands
- Visual Studio, commands
- predefined command aliases
- commands, aliases
- Visual Studio commands
- pre-defined command aliases
- command aliases
ms.assetid: de8bb378-8c1c-4087-a9a5-537fa8314c19
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 48e849df1cb918682176befa25c688fe7b436460
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-command-aliases"></a>Aliasy příkazů sady Visual Studio
Aliasy umožňují pro zadání příkazu do **najít/příkaz** pole nebo **příkaz** okno zkrácením text potřebné k provedení příkazu. Například místo zadávání `>File.OpenFile` zobrazíte **otevření souboru** dialogové okno, můžete použít předdefinované alias `>of`.  
  
 Typ `alias` v **příkaz**okna zobrazte seznam aktuální aliasy a jejich definice. Typ `>cls` vymazat obsah **příkaz** okno. Pokud chcete zobrazit alias pro konkrétní příkaz, zadejte `alias <command name>`.  
  
 Můžete snadno vytvořit svůj vlastní alias pro jednu příkazy sady Visual Studio (s nebo bez argumentů). Příklad syntaxe pro aliasy `File.NewFile MyFile.txt` je `alias MyAlias File.NewFile MyFile.txt`. Můžete odstranit jedním z vaše aliasy s`alias <alias name> /delete`  
  
 Následující tabulka obsahuje seznam předdefinované aliasy příkazů sady Visual Studio. Některé názvy příkazů mít více než jeden předem definovaný alias. Kliknutím na odkazy pro názvy příkazů níže zobrazíte podrobné témat, která vysvětlují správnou syntaxi, argumentů a přepínačů pro tyto příkazy.  
  
|Název příkazu|Alias|Úplný název|  
|------------------|-----------|-------------------|  
|[Příkaz Tisk](../../ide/reference/print-command.md)|?|Debug.Print –|  
|[Příkaz Rychlé kukátko](../../ide/reference/quick-watch-command.md)|??|Debug.QuickWatch –|  
|Přidat nový projekt|AddProj|File.AddNewProject|  
|[Příkaz Alias](../../ide/reference/alias-command.md)|Alias|Tools.alias –|  
|Automatické hodnoty – okno|Automatické hodnoty|Debug.Autos|  
|Zarážky – okno|blokovaných.|Debug.Breakpoints|  
|Přepnout zarážku|doporučených postupů|Debug.togglebreakpoint –|  
|okno Zásobník volání|Zásobník volání|Debug.CallStack|  
|Odstranit záložky|ClearBook|Edit.ClearBookmarks|  
|Zavřít|Zavřít|File.Close|  
|Zavřete všechny dokumenty|CloseAll –|Window.CloseAllDocuments|  
|Vymazat vše|specifikací CLS|Edit.ClearAll|  
|Režim příkazu|Cmd|View.CommandWindow|  
|Zobrazení kódu|kód|View.ViewCode|  
|[Příkaz Listovat paměť](../../ide/reference/list-memory-command.md)|d|Debug.listmemory –|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) standardu ANSI|da|Debug.listmemory – /Ansi|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) jeden bajtovém formátu|DB|Debug.listmemory – /Format:OneByte|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) jako ANSI s čtyři bajtovém formátu|řadič domény|Debug.listmemory – /Format:FourBytes /Ansi|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) čtyři bajtovém formátu|dd|Debug.listmemory – /Format:FourBytes|  
|Odstranit knihách online|DelBOL|Edit.DeleteToBOL|  
|Odstranit EOL|DelEOL|Edit.DeleteToEOL|  
|Odstranit vodorovné prázdné znaky|DelHSp|Edit.DeleteHorizontalWhitespace|  
|Návrhář zobrazení|návrhář|View.ViewDesigner|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) formátu Float|DF –|Debug.ListMemory/Format:Float|  
|okno Zpětný překlad|disasm|Debug.Disassembly|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) osm bajtovém formátu|dq –|Debug.listmemory – /Format:EightBytes|  
|[Seznam paměť – příkaz](../../ide/reference/list-memory-command.md) jako kódování Unicode|du|Debug.listmemory – / Unicode|  
|[Příkaz Ohodnotit příkaz](../../ide/reference/evaluate-statement-command.md)|zkušební verze|Debug.evaluatestatement –|  
|Ukončit|Ukončit|File.Exit|  
|Výběr formátu|formát|Edit.FormatSelection|  
|Celoobrazovkový režim|Celá obrazovka|View.FullScreen|  
|[Příkaz Spustit](../../ide/reference/start-command.md)|G|Debug.Start|  
|[Příkaz Přejít na](../../ide/reference/go-to-command.md)|GotoLn|Edit.GoTo|  
|Přejděte do závorek|GotoBrace|Edit.GotoBrace|  
|F1Help|Nápověda|Help.F1Help|  
|Přímý režim|ihned|Tools.ImmediateMode|  
|Vložit soubor jako Text|InsertFile|Edit.InsertFileAsText|  
|[Příkaz Listovat zásobník volání](../../ide/reference/list-call-stack-command.md)|kb|Debug.listcallstack –|  
|Ujistěte se, malá písmena|LCase|Edit.MakeLowercase|  
|Vyjmout řádku|LineCut|Edit.LineCut|  
|Odstranit řádek|LineDel|Edit.LineDelete|  
|Vypsat členy|Vypisovat členy|Edit.ListMembers|  
|Místní hodnoty – okno|Lokální proměnné|Debug.Locals|  
|[Příkaz Okno výstupu příkazů protokolu](../../ide/reference/log-command-window-output-command.md)|Protokolu|Tools.LogCommandWindowOutput|  
|Režim označení příkazového okna|Označit|Tools.CommandWindowMarkMode|  
|Paměť – okno|Memory1 paměti|Debug.Memory1|  
|Paměť – okno 2|Memory2|Debug.Memory2|  
|Paměť – okno 3|Memory3|Debug.Memory3|  
|Paměť – okno 4|Paměť4|Debug.Memory4|  
|[Příkaz Nastavit základ](../../ide/reference/set-radix-command.md)|n|Debug.setradix –|  
|[Příkaz ShowWebBrowser (Zobrazit webový prohlížeč)](../../ide/reference/showwebbrowser-command.md)|přejděte NAV|View.showwebbrowser –|  
|Další záložek|NextBook|Edit.NextBookmark|  
|[Příkaz Nový soubor](../../ide/reference/new-file-command.md)|NF|File.NewFile|  
|Nový projekt|NP NewProj|File.NewProject|  
|[Příkaz Otevřít soubor](../../ide/reference/open-file-command.md)|z Open|File.OpenFile|  
|[Příkaz Otevřít projekt](../../ide/reference/open-project-command.md)|OP|File.OpenProject|  
|Sbalit pro definice a zastavení osnovy|OutlineDefs StopOutlining|Edit.CollapsetoDefinitions|  
|Krok přes|P|Debug.StepOver|  
|Informace o parametrech|ParamInfo|Edit.ParameterInfo|  
|Krok|Kód pr|Debug.StepOut|  
|Předchozí záložek|PrevBook|Edit.PreviousBookmark|  
|Tisk souboru|Tisk|File.Print|  
|Okno vlastností|props|View.PropertiesWindow|  
|Zastavit|q|Debug.StopDebugging|  
|znovu:|znovu:|Edit.Redo|  
|Registr – okno|registr|Debug.Registers|  
|Spustit ke kurzoru|RTC|Debug.RunToCursor|  
|Uložit vybrané položky|Uložit|File.SaveSelectedItems|  
|Uložit vše|SaveAll|File.SaveAll|  
|Uložit jako|Uložit jako|File.SaveSelectedItemsAs|  
|[Příkaz Prostředí](../../ide/reference/shell-command.md)|prostředí|Tools.Shell –|  
|Zastavit najít v souborech|StopFind|Edit.findinfiles – / stop|  
|Swap Ukotvení|SwapAnchor|Edit.SwapAnchor|  
|Krok do|t|Debug.StepInto|  
|Převedení na tabulátory výběr|převedení na tabulátory|Edit.TabifySelection|  
|Tasklist – okno|TaskList|View.TaskList|  
|Vlákna – okno|Vlákna|Debug.Threads|  
|Vedle sebe|TileH|Window.TileHorizontally|  
|Svisle vedle sebe|TileV|Window.TileVertically|  
|Přepnutí záložek|ToggleBook|Edit.ToggleBookmark|  
|Okna nástrojů|sada nástrojů|View.Toolbox|  
|[Příkaz Zobrazit zpětný překlad](../../ide/reference/list-disassembly-command.md)|u|Debug.listdisassembly –|  
|Převést na velká písmena|UCase|Edit.MakeUppercase|  
|vrácení zpět|vrácení zpět|Edit.Undo|  
|Zrušit výběr tabulátory|Zrušit tabulátory|Edit.UntabifySelection|  
|Kukátko – okno|Sledování|Debug.WatchN|  
|Přepnout zalamování řádků|WordWrap|Edit.ToggleWordWrap|  
|Seznam procesů|&#124;|Debug.ListProcesses|  
|[Příkaz Listovat vlákna](../../ide/reference/list-threads-command.md)|~ ~ * tisíc ~\*kb|Debug.listthreads – Debug.ListTheads /AllThreads|  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)