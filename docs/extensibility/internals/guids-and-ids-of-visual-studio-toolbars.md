---
title: "Identifikátory panelů nástrojů Visual Studio a identifikátory GUID | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- visual studio groups
- toolbars
- visual studio toolbar
- id
- toolgar group
- tool window toolbar
- guid
ms.assetid: c9cacd57-9225-450f-a9ac-cbf3168ea844
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: bbb14818cebb35f703ec6f5ade084d96ac383d6a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="guids-and-ids-of-visual-studio-toolbars"></a>Identifikátory panelů nástrojů Visual Studio a identifikátory GUID
Toto téma uvádí hodnoty GUID a ID panelů nástrojů, které jsou zahrnuté v sadě Visual Studio integrované vývojové prostředí (IDE) a skupiny obsahují. Tyto hodnoty jsou definovány v .vsct soubory, které jsou nainstalovány v rámci sady Visual Studio SDK. Další informace najdete v tématu [IDE-Defined příkazy, nabídky a skupiny](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
> [!NOTE]
>  Množství dostupné pro Visual Studio panely nástrojů nejsou definované sadě Visual Studio a jejich identifikátoru GUID a ID hodnoty nejsou veřejná. Toto téma uvádí jenom panely nástrojů, které jsou definovány v souborech .vsct Visual Studio SDK.  
  
 Další informace o tom, jak pracovat s objekty IDE, které jsou definovány v souborech .vsct najdete v tématu [rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).  
  
 Výchozí panely nástrojů poskytovaných Visual Studio IDE použít identifikátor GUID `guidSHLMainMenu`, pokud pomocí syntaxe GUID:ID uvedeno jinak.  
  
## <a name="ide-toolbars"></a>Panely nástrojů rozhraní IDE  
 Visual Studio IDE jsou poskytovány následující panely nástrojů. Panely nástrojů lze zobrazit výběrem na **panely nástrojů** podnabídce **nástroje** nabídky. Panely nástrojů v systému windows nástroj nejsou zahrnuté v této části.  
  
 Pouze skupiny, můžete sestup přímo z panely nástrojů. Přidat skupinu, nastavte jeho nadřazený identifikátor GUID a ID panelu nástrojů. K přidání tlačítka na panel nástrojů, nastavte jeho nadřazený objekt do skupiny na panelu nástrojů.  
  
|Panel nástrojů|ID|  
|-------------|--------|  
|Standard|IDM_VS_TOOL_STANDARD|  
|Sestavení|IDM_VS_TOOL_BUILD|  
|Textový editor|IDM_VS_TOOL_TEXTEDITOR|  
|Ladit|guidVSDebugGroup:IDM_DEBUG_TOOLBAR|  
|Ladění umístění|guidVSDebugGroup:IDM_DEBUG_CONTEXT_TOOLBAR|  
  
### <a name="special-toolbars"></a>Speciální panely nástrojů  
 Panely nástrojů jsou definovaná sadou Visual Studio IDE, ale sloužit specializované funkce a není hostitelem příkaz skupiny.  
  
|Panel nástrojů|ID|  
|-------------|--------|  
|Příkaz Přidat|IDM_VS_TOOL_ADDCOMMAND|  
|Nedefinovaná|IDM_VS_TOOL_UNDEFINED|  
|XML schéma|IDM_VS_TOOL_SCHEMA|  
|XML Data|IDM_VS_TOOL_DATA|  
  
## <a name="groups-on-the-ide-toolbars"></a>Skupiny na panely nástrojů rozhraní IDE  
 Přidání tlačítka na standardním panelu nástrojů, nastavte jednu z následujících skupin jako svůj nadřazený uzel. Skupiny jsou seřazené podle nadřazené panelu nástrojů.  
  
### <a name="standard-toolbar-groups"></a>Skupiny standardním panelu nástrojů  
  
|Název|ID|  
|----------|--------|  
|Uložit a otevřít|IDG_VS_TOOLSB_SAVEOPEN|  
|Vyjmout/Kopírovat|IDG_VS_TOOLSB_CUTCOPY|  
|Vrátit/opakovat|IDG_VS_TOOLSB_UNDOREDO|  
|Spustit nebo sestavení|IDG_VS_TOOLSB_RUNBUILD|  
|Hledat|IDG_VS_TOOLSB_SEARCH|  
|Windows|IDG_VS_TOOLSB_WINDOWS|  
|Nové Windows|IDG_VS_TOOLSB_NEWWINDOWS|  
|Načíst nebo uložit|IDG_VS_WINDOWUI_LOADSAVE|  
|Měřidla|IDG_VS_TOOLSB_GAUGE|  
  
### <a name="build-toolbar-groups"></a>Vytvoření skupiny panelu nástrojů  
  
|Název|ID|  
|----------|--------|  
|Panelu sestavení|IDG_VS_BUILDBAR|  
|Zrušit|IDG_VS_BUILD_CANCEL|  
  
### <a name="text-editor-toolbar-groups"></a>Skupiny textového editoru panelu nástrojů  
  
|Název|ID|  
|----------|--------|  
|Dokončení|IDM_VS_TOOL_TEXTEDITOR|  
|Odsazení|IDG_VS_EDITTOOLBAR_INDENT|  
|Komentář|IDG_VS_EDITTOOLBAR_COMMENT|  
|Záložky|IDG_VS_EDITTOOLBAR_TEMPBOOKMARKS|  
  
### <a name="debug-toolbar-groups"></a>Ladění skupiny panelu nástrojů  
  
|Název|ID|  
|----------|--------|  
|Spuštění|IDM_DEBUG_TOOLBAR|  
|Krokování s|IDG_DEBUG_TOOLBAR_STEPPING|  
|Sledování|IDG_DEBUG_TOOLBAR_WATCH|  
|Windows|IDG_DEBUG_TOOLBAR_WINDOWS|  
  
### <a name="debug-location-toolbar-groups"></a>Ladění skupiny umístění panelu nástrojů  
  
|Název|ID|  
|----------|--------|  
|Ladění umístění|IDG_DEBUG_CONTEXT_TOOLBAR|  
  
## <a name="tool-window-toolbars"></a>Nástroj panely nástrojů  
 Panely nástrojů může vyskytovat přímo v prostředí IDE nebo v panelech nástrojů, jako **Průzkumníku řešení**. Protože nástroj windows nejsou definovány v souborech .vsct, nástroj panely nástrojů nemají definované nadřazené položky. Místo toho jsou umístěny v kódu. V následující tabulce jsou uvedeny panely nástrojů, které se zobrazují v systému windows nástroj v prostředí IDE a příkaz skupiny, které obsahují.  
  
> [!NOTE]
>  Panely nástrojů a skupiny použít identifikátor GUID `guidSHLMainMenu`, pokud pomocí syntaxe GUID:ID uvedeno jinak. Kde je identifikátor GUID je zadán pro panel nástrojů, platí také pro skupiny, které sestup tohoto panelu nástrojů.  
  
|Okno nástroje|Panel nástrojů|Skupiny|  
|-----------------|-------------|------------|  
|Průzkumník řešení|IDM_VS_TOOL_PROJWIN|IDG_VS_PROJ_TOOLBAR1... 5|  
|Průzkumník serveru|guid_SE_MenuGroup:IDM_SE_TOOLBAR_SERVEREXPLORER|IDG_SE_TOOLBAR_REFRESH|  
|Vlastnosti|IDM_VS_TOOL_PROPERTIES|IDG_VS_PROPERTIES_SORT<br /><br /> IDG_VS_PROPERTIES_PAGES|  
|zobrazení tříd|IDM_VS_TOOL_CLASSVIEW|IDG_VS_CLASSVIEW_FOLDERS<br /><br /> IDG_VS_CLASSVIEW_SEARCH<br /><br /> IDG_VS_CLASSVIEW_SETTINGS|  
|zobrazení tříd|IDM_VS_TOOL_CLASSVIEW_GO|IDG_VS_CLASSVIEW_SEARCH2|  
|prohlížeč objektů|IDM_VS_TOOL_OBJBROWSER|IDG_VS_OBJBROWSER_SUBSETS<br /><br /> IDG_VS_OBJBROWSER_SEARCH<br /><br /> IDG_VS_OBJBROWSER_ADDREFERENCE<br /><br /> IDG_VS_OBJBROWSER_BROWSERSETTINGS|  
|prohlížeč objektů|IDM_VS_TOOL_OBJECT_BROWSER_GO|IDG_VS_OBJBROWSER_SEARCH2|  
|Výstup|IDM_VS_TOOL_OUTPUTWINDOW|IDG_VS_OUTPUTWINDOW_SELECT<br /><br /> IDG_VS_OUTPUTWINDOW_GOTO<br /><br /> IDG_VS_OUTPUTWINDOW_NEXTPREV<br /><br /> IDG_VS_OUTPUTWINDOW_CLEAR<br /><br /> IDG_VS_OUTPUTWINDOW_WORDWRAP|  
|hledání a nahrazování|IDM_VS_TOOL_UNIFIEDFIND|IDG_VS_FINDTAB<br /><br /> IDG_VS_REPLACETAB|  
|Najít výsledky 1|IDM_VS_TOOL_FINDRESULTS1|IDG_VS_FINDRESULTS1_GOTO<br /><br /> IDG_VS_FINDRESULTS1_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS1_CLEAR<br /><br /> IDG_VS_FINDRESULTS1_STOPFIND|  
|Najít výsledky 2|IDM_VS_TOOL_FINDRESULTS2|IDG_VS_FINDRESULTS2_GOTO<br /><br /> IDG_VS_FINDRESULTS2_NEXTPREV<br /><br /> IDG_VS_FINDRESULTS2_CLEAR<br /><br /> IDG_VS_FINDRESULTS2_STOPFIND|  
|fragment kódu|IDM_VS_TOOL_SNIPPETMENUS|IDG_VS_SNIPPET_REPL<br /><br /> IDG_VS_SNIPPET_REF<br /><br /> IDG_VS_SNIPPET_PROP|  
|Záložky|IDM_VS_TOOL_BOOKMARKWIND|IDG_VS_BWNEWFOLDER<br /><br /> IDG_VS_BWNEXTBM<br /><br /> IDG_VS_BWNEXTBMF<br /><br /> IDG_VS_BWENABLE<br /><br /> IDG_VS_BWDELETE|  
|Seznam úloh|IDM_VS_TOOL_TASKLIST|IDG_VS_TASKLIST_PROVIDERLIST|  
|Úlohy uživatele|IDM_VS_TOOL_USERTASKS|IDG_VS_TASKLIST_PROVIDERLIST<br /><br /> IDG_VS_USERTASKS_EDIT|  
|Seznam chyb|IDM_VS_TOOL_ERRORLIST|IDG_VS_ERRORLIST_ERRORGROUP<br /><br /> IDG_VS_ERRORLIST_WARNINGGROUP<br /><br /> IDG_VS_ERRORLIST_MESSAGEGROUP|  
|Volání prohlížeče|IDM_VS_TOOL_CALLBROWSER1... 16|IDG_VS_TOOLBAR_CALLBROWSER1_ACTIONS<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_TYPE<br /><br /> IDG_VS_TOOLBAR_CALLBROWSER1_CBSETTINGS|  
|Zarážky|guidVSDebugGroup:IDM_BREAKPOINTS_WINDOW_TOOLBAR|IDG_BREAKPOINTS_WINDOW_NEW<br /><br /> IDG_BREAKPOINTS_WINDOW_DELETE<br /><br /> IDG_BREAKPOINTS_WINDOW_ALL<br /><br /> IDG_BREAKPOINTS_WINDOW_VIEW<br /><br /> IDG_BREAKPOINTS_WINDOW_EDIT<br /><br /> IDG_BREAKPOINTS_WINDOW_COLUMNS|  
|Zpětný překlad|guidVSDebugGroup:IDM_DISASM_WINDOW_TOOLBAR|IDG_DISASM_WINDOW_TOOLBAR|  
|Paměť 1 – 4|guidVSDebugGroup:IDM_MEMORY_WINDOW_TOOLBAR1... 4|IDG_MEMORY_EXPRESSION1... 4<br /><br /> IDG_MEMORY_COLUMNS1... 4|  
|Procesy|guidVSDebugGroup:IDM_ATTACHED_PROCS_TOOLBAR|IDG_ATTACHED_PROCS_EXECCNTRL IDG_ATTACHED_PROCS_STEPPING<br /><br /> IDG_ATTACHED_PROCS_EXECCNTRL2<br /><br /> IDG_ATTACHED_PROCS_ATTACH<br /><br /> IDG_ATTACHED_PROCS_COLUMNS|  
  
## <a name="see-also"></a>Viz také  
 [Přidávání řadiče nabídky na panelu nástrojů](../../extensibility/adding-a-menu-controller-to-a-toolbar.md)   
 [Přidávání panelů nástrojů do okno nástroje](../../extensibility/adding-a-toolbar-to-a-tool-window.md)   
 [Identifikátory GUID a ID nabídek sady Visual Studio](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)