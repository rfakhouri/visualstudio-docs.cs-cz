---
title: Identifikátory GUID a ID nabídky sady Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- visual studio menus
- visual studio groups
- id
- existing menus
- guid
- menus
ms.assetid: 84639d86-dd21-4b35-9988-6bb654162488
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 163f7b81295468a69cfb28959f608a21f94a4a99
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134211"
---
# <a name="guids-and-ids-of-visual-studio-menus"></a>Identifikátory GUID a ID nabídky sady Visual Studio
Toto téma se zobrazí hodnoty GUID a ID nabídky a skupin v řádku nabídek Visual Studio. Tyto hodnoty jsou definovány v .vsct soubory, které jsou nainstalovány v rámci sady Visual Studio SDK. Další informace najdete v tématu [IDE-Defined příkazy, nabídky a skupiny](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
 Další informace o tom, jak pracovat s objekty integrované vývojové prostředí (IDE), které jsou definovány v souborech .vsct najdete v tématu [rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).  
  
 Nabídky a skupin v panelu nabídek Visual Studio použít identifikátor GUID `guidSHLMainMenu`. V nabídce panelu samotné má ID `IDM_VS_TOOL_MAINMENU`.  
  
## <a name="groups-on-the-visual-studio-menu-bar"></a>Skupiny v řádku nabídek Visual Studio  
 Přidat nabídku na panelu nabídek, nastavte jednu z těchto skupin jako svůj nadřazený uzel.  
  
|Skupina|ID|  
|-----------|--------|  
|Soubor nebo úpravy/zobrazení|IDG_VS_MM_FILEEDITVIEW|  
|Refaktoring|IDG_VS_MM_REFACTORING:|  
|Projekt|IDG_VS_MM_PROJECT|  
|Sestavení|IDG_VS_MM_BUILDDEBUGRUN|  
|Formát nebo nástroje|IDG_VS_MM_TOOLSADDINS|  
|Okno/Help nebo komunity|IDG_VS_MM_WINDOWHELP|  
|Doplňky|IDG_VS_MM_MACROS|  
|FullScreenBar|IDG_VS_MM_FULLSCREENBAR|  
  
## <a name="menus-on-the-visual-studio-menu-bar"></a>Nabídky v řádku nabídek Visual Studio  
 Přidat skupinu do existující sady Visual Studio nabídky, nastavte jednu z následujících nabídek jako svůj nadřazený uzel. Dílčích nejsou zahrnuté v tomto seznamu.  
  
|Nabídka|ID|  
|----------|--------|  
|Soubor|IDM_VS_MENU_FILE|  
|Upravit|IDM_VS_MENU_EDIT|  
|Zobrazit|IDM_VS_MENU_VIEW|  
|Refaktorovat|IDM_VS_MENU_REFACTORING|  
|Projekt|IDM_VS_MENU_PROJECT|  
|Sestavení|IDM_VS_MENU_BUILD|  
|Formát|IDM_VS_MENU_FORMAT|  
|Nástroje|IDM_VS_MENU_TOOLS|  
|Okno|IDM_VS_MENU_WINDOW|  
|Doplňky|IDM_VS_MENU_ADDINS|  
|Komunita|IDM_VS_MENU_COMMUNITY|  
|Nápověda|IDM_VS_MENU_HELP|  
  
## <a name="groups-on-visual-studio-menus"></a>Skupiny v sadě Visual Studio nabídky  
 Následující seznamy shrnují skupiny, které sestup přímo z nabídky na panelu nabídek Visual Studio. Nejrychlejší způsob, jak přidat příkaz k nabídce sady Visual Studio je nastavit jednu z těchto skupin jako nadřazená položka. Skupiny, které sestup z dílčích se nezobrazí v této části.  
  
### <a name="file-menu-groups"></a>Skupiny nabídek souboru  
  
|Skupina|ID|  
|-----------|--------|  
|Nový nebo otevřít|IDG_VS_FILE_FILE|  
|Přidejte|IDG_VS_FILE_ADD|  
|Řešení|IDG_VS_FILE_SOLUTION|  
|Různé|IDG_VS_FILE_MISC|  
|Uložit|IDG_VS_FILE_SAVE|  
|přejmenování|IDG_VS_FILE_RENAME|  
|Prohlížeč|IDG_VS_FILE_BROWSER|  
|Tisk|IDG_VS_FILE_PRINT|  
|Naposledy použité|IDG_VS_FILE_MRU|  
|Přesunutí|IDG_VS_FILE_MOVE|  
|Ukončit|IDG_VS_FILE_EXIT|  
  
### <a name="edit-menu-groups"></a>Upravit skupiny nabídek  
  
|Skupina|ID|  
|-----------|--------|  
|Vrátit/opakovat|IDG_VS_EDIT_UNDOREDO|  
|Vyjímání, kopírování a vkládání|IDG_VS_EDIT_CUTCOPY|  
|Vyberte|IDG_VS_EDIT_SELECT|  
|Goto – příkaz|IDG_VS_EDIT_GOTO|  
|Najít|IDG_VS_EDIT_FIND|  
|Objekty|IDG_VS_EDIT_OBJECTS|  
|Příkazy OLE|IDG_VS_EDIT_OLEVERBS|  
|Příkaz také|IDG_VS_EDIT_COMMANDWELL|  
  
### <a name="refactor-menu-groups"></a>Refaktorovat skupiny nabídek  
  
|Skupina|ID|  
|-----------|--------|  
|Běžné|IDG_REFACTORING_COMMON|  
|Upřesnit|IDG_REFACTORING_ADVANCED|  
  
### <a name="view-menu-groups"></a>Zobrazení skupiny nabídek  
  
|Skupina|ID|  
|-----------|--------|  
|Kód formuláře|IDG_VS_VIEW_FORMCODE|  
|Prohlížeč|IDG_VS_VIEW_BROWSER|  
|Definujte zobrazení|IDG_VS_VIEW_DEFINEVIEWS|  
|Windows|IDG_VS_VIEW_WINDOWS|  
|Architekti Windows|IDG_VS_VIEW_ARCH_WINDOWS|  
|Organizace Windows|IDG_VS_VIEW_ORG_WINDOWS|  
|Prohlížeč kódu|IDG_VS_VIEW_CODEBROWSENAV_WINDOWS|  
|Dev Windows|IDG_VS_VIEW_DEV_WINDOWS|  
|Panely nástrojů|IDG_VS_VIEW_TOOLBARS|  
|Symboly|IDG_VS_VIEW_SYMBOLNAVIGATE|  
|Přejděte|IDG_VS_VIEW_NAVIGATE|  
|Malého přejděte.|IDG_VS_VIEW_SMALLNAVIGATE|  
|prohlížeč objektů|IDG_VS_VIEW_OBJBRWSR|  
|Příkaz také|IDG_VS_VIEW_COMMANDWELL|  
|Stránky vlastností|IDG_VS_VIEW_PROPPAGES|  
|Aktualizace|IDG_VS_VIEW_REFRESH|  
  
### <a name="project-menu-groups"></a>Skupiny nabídek projektu  
  
|Skupina|ID|  
|-----------|--------|  
|Různé přidat|IDG_VS_PROJ_MISCADD|  
|Přidejte|IDG_VS_PROJ_ADD|  
|Folder|IDG_VS_PROJ_FOLDER|  
|Uvolnění nebo opětovného načtení|IDG_VS_PROJ_UNLOADRELOAD|  
|Odkaz|IDG_VS_PROJ_REFERENCE|  
|Možnosti|IDG_VS_PROJ_OPTIONS|  
|Nastavení|IDG_VS_PROJ_SETTINGS|  
  
### <a name="build-menu-groups"></a>Vytvoření skupiny nabídek  
  
|Skupina|ID|  
|-----------|--------|  
|Řešení|IDG_VS_BUILD_SOLUTION|  
|Výběr|IDG_VS_BUILD_SELECTION|  
|Optimalizace na základě profilu|IDG_VS_PGO_SELECTION|  
|Různé|IDG_VS_BUILD_MISC|  
|Zrušit|IDG_VS_BUILD_CANCEL|  
  
### <a name="tools-menu-groups"></a>Skupiny nabídek nástroje  
  
|Skupina|ID|  
|-----------|--------|  
|Příkazový řádek|IDG_VS_TOOLS_CMDLINE|  
|Fragmenty kódu|IDG_VS_TOOLS_SNIPPETS|  
|Část objektu|IDG_VS_TOOLS_OBJSUBSET|  
|Možnosti|IDG_VS_TOOLS_OPTIONS|  
|Ostatní 2|IDG_VS_TOOLS_OTHER2|  
|Externí nástroje|IDG_VS_TOOLS_EXT_TOOLS|  
|Externí přizpůsobení|IDG_VS_TOOLS_EXT_CUST|  
  
### <a name="window-menu-groups"></a>Okno skupiny nabídek  
  
|Skupina|ID|  
|-----------|--------|  
|Nový|IDG_VS_WINDOW_NEW|  
|Ukotvení nebo zavřít.|IDG_VS_DOCKCLOSE|  
|Ukotvení či skrýt|IDG_VS_DOCKHIDE|  
|Uspořádat|IDG_VS_WINDOW_ARRANGE|  
|Navigace|IDG_VS_WINDOW_NAVIGATION|  
|Seznam|IDG_VS_WINDOW_LIST|  
  
### <a name="help-menu-groups"></a>Skupiny nabídek nápovědy  
  
|Skupina|ID|  
|-----------|--------|  
|Ukázky kódu|IDG_VS_HELP_SAMPLES|  
|Podpora|IDG_VS_HELP_SUPPORT|  
|O produktu|IDG_VS_HELP_ABOUT|  
  
## <a name="submenus-of-visual-studio-menus"></a>Dílčích nabídek sady Visual Studio  
 U následující hierarchie zobrazuje dílčích, které jsou spojeny s nabídkami v řádku nabídek Visual Studio. Protože pouze skupiny může mít jako svůj nadřazený uzel nabídky, každý dílčí musí sestup ze skupiny v nabídce, místo přímo z nabídky. Další informace o vztahu mezi nabídek, skupin a dílčích najdete v tématu [přidání podnabídky do nabídky](../../extensibility/adding-a-submenu-to-a-menu.md).  
  
> [!NOTE]
>  Názvy nabídek v řádku nabídek Visual Studio nejsou zobrazeny samostatně v této hierarchii vzhledem k tomu, že lze odvodit z zásady vytváření názvů pro skupiny v prostředí IDE, následujícím způsobem: IDG_VS_*název nabídky*_*název skupiny*.  
  
|Nadřazené skupiny|Dílčí|Podřízené skupiny|  
|------------------|-------------|------------------|  
|IDG_VS_FILE_FILE|IDM_VS_CSCD_NEW|IDG_VS_FILE_NEW_CASCADE|  
||IDM_VS_CSCD_OPEN|IDG_VS_FILE_OPENP_CASCADE|  
|||IDG_VS_FILE_OPENF_CASCADE|  
|IDG_VS_FILE_ADD|IDM_VS_CSCD_ADD|IDG_VS_FILE_ADD_PROJECT_NEW|  
|||IDG_VS_FILE_ADD_PROJECT_EXI|  
|IDG_VS_FILE_MRU|IDM_VS_CSCD_FILEMRU|IDG_VS_FILE_FMRU_CASCADE|  
||IDM_VS_CSCD_PROJMRU|IDG_VS_FILE_PMRU_CASCADE|  
|IDG_VS_FILE_MOVE|IDM_VS_CSCD_MOVETOPRJ|IDG_VS_FILE_MOVE_CASCADE|  
|||IDG_VS_FILE_MOVE_PICKER|  
|IDG_VS_VIEW_DEV_WINDOWS|IDM_VS_CSCD_FINDRESULTS|IDG_VS_WNDO_FINDRESULTS|  
||IDM_VS_CSCD_WINDOWS|IDG_VS_VIEW_CALLBROWSER|  
|||IDG_VS_WNDO_OTRWNDWS1... 6|  
|||IDG_VS_WNDO_WINDOWS2|  
|IDG_VS_VIEW_TOOLBARS|IDM_VS_CSCD_COMMANDBARS||  
|IDG_VS_EDIT_GOTO|IDM_VS_EDITOR_FIND_MENU||  
|IDG_VS_EDIT_OBJECTS|IDM_VS_CSCD_MNUDES|IDG_VS_MNUDES_INSERT|  
|||IDG_VS_MNUDES_EDITNAMES|  
||IDM_VS_CSCD_OLEVERBS|IDG_VS_EDIT_OLEVERBS|  
|IDG_VS_BUILD_SELECTION|IDM_VS_CSCD_BUILD|IDG_VS_BUILD_CASCADE|  
|||IDG_VS_BUILD_PROJPICKER|  
||IDM_VS_CSCD_REBUILD|IDG_VS_REBUILD_CASCADE|  
|||IDG_VS_REBUILD_PROJPICKER|  
||IDM_VS_CSCD_PROJONLY|IDG_VS_PROJONLY_CASCADE|  
||IDM_VS_CSCD_CLEAN|IDG_VS_CLEAN_CASCADE|  
|||IDG_VS_CLEAN_PROJPICKER|  
||IDM_VS_CSCD_DEPLOY|IDG_VS_DEPLOY_CASCADE|  
|||IDG_VS_DEPLOY_PROJPICKER|  
|IDG_VS_PGO_SELECTION|IDM_VS_CSCD_PGO_BUILD|IDG_VS_PGO_BUILD_CASCADE_BUILD|  
|||IDG_VS_PGO_BUILD_CASCADE_RUN|  
  
## <a name="see-also"></a>Viz také  
 [Identifikátory panelů nástrojů Visual Studio a identifikátory GUID](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)   
 [Identifikátory příkazů sady Visual Studio a identifikátory GUID](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)   
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)