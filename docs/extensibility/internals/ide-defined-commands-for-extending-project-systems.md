---
title: Příkazy definované prostředím IDE pro rozšíření systémů projektů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, project systems
- project systems, environment-defined commands
ms.assetid: 0e33b8e9-16fa-4400-a941-e92d56120e7e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 26f5ee29a52546e7f2111189f54d64c160a94cea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62860343"
---
# <a name="ide-defined-commands-for-extending-project-systems"></a>Příkazy definované prostředím IDE pro rozšíření systémů projektů
Pokud chcete rozšíření systémů projektů, můžete použít příkazy a příkaz skupiny poskytované [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí.

 Příkaz položky, které jsou obzvláště užitečné pro rozšíření systémů projektů naleznete v následujících částech.

## <a name="command-menus"></a>Příkaz nabídky
 V následující tabulce jsou uvedeny příkaz nabídky, které jsou užitečné umístění všechny základní příkazy, které vyvolat rozšíření projektu.

|Příkaz nabídky|Popis|
|------------------|-----------------|
|IDM_VS_MENU_PROJECT|**Projektu** nabídek nejvyšší úrovně.|
|IDM_VS_TOOL_PROJWIN|**Průzkumníka řešení** nástrojů.|

## <a name="shortcut-menus"></a>Používání místních nabídek
 V následující tabulce jsou uvedeny používání místních nabídek, které se vztahují při výběru jednoho uzlu v **Průzkumníka řešení**, nebo pokud existuje více homogenní výběrů v **Průzkumníka řešení**, což je při všechny vybrané uzly jsou stejného typu.

|Místní nabídky|Popis|
|-------------------|-----------------|
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_PROJNODE>|Použije, když je vybrán uzel projektu.|
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_ITEMNODE>|Platí, když je vybrán soubor.|
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_FOLDERNODE>|Platí, když je vybrána složka.|
|IDM_VS_CTXT_WEBREFFOLDER|Platí, pokud je vybrána složka webového odkazu.|
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_REFERENCEROOT>|Platí, pokud je vybrána kořenový uzel odkazů nazývají "Odkazy".|
|<xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_REFERENCE>|Platí, pokud odkaz na uzly jsou vybrány. patří mezi ně sestavení, COM a pouze odkazy projektu. Nezahrnuje webových odkazů.|

 Následující tabulka uvádí používání místních nabídek, které se vztahují při výběru v **Průzkumníku řešení** zahrnuje více hierarchií

|Místní nabídky|Popis|
|-------------------|-----------------|
|IDM_VS_CTXT_XPROJ_SLNPROJ|Použije aktuální výběr obsahuje uzel řešení a kořenové uzly projektu.|
|IDM_VS_CTXT_XPROJ_SLNITEM|Použije aktuální výběr obsahuje uzel a projekt položky řešení.|
|IDM_VS_CTXT_XPROJ_MULTIPROJ|Platí, když se skládá z několika kořenové uzly projektu pouze aktuální výběr.|
|IDM_VS_CTXT_XPROJ_PROJITEM|Použije aktuální výběr obsahuje kombinaci kořenových uzlů projektu a položky projektu. Kromě toho výběr může obsahovat uzel řešení.|
|IDM_VS_CTXT_XPROJ_MULTIITEM|Použije aktuální výběr obsahuje položky projektu z více projektů v řešení nebo když jsou vybrané položky různých typů ve stejném projektu.|

## <a name="command-groups"></a>Pro skupinu příkazů
 V následující tabulce jsou uvedeny příkaz skupiny, které můžete použít při rozšíření projektů, a můžete přistupovat prostřednictvím <xref:Microsoft.VisualStudio.Shell.VsMenus.IDM_VS_CTXT_PROJNODE> nabídku.

|Skupinu příkazů|Popis|
|-------------------|-----------------|
|IDG_VS_CTXT_PROJECT_BUILD|Příkazy pro vytváření, nové sestavení a nasazení projektu.|
|IDG_VS_CTXT_COMPILELINK|Příkazy pro kompilování a propojování projektu.|
|IDG_VS_CTXT_PROJECT_CONFIG|Příkazy, které nastavení konfigurace projektu a pořadí sestavení.|
|IDG_VS_CTXT_PROJECT_ADD|Příkazy, které přidat položky do projektu.|
|IDG_VS_CTXT_PROJECT_START|Příkazy, které nastavte projekt po spuštění přidružené klávesu F5.|
|IDG_VS_CTXT_PROJECT_SAVE|Příkazy pro uložení položek projektu.|
|IDG_VS_CTXT_PROJECT_DEBUG|Příkazy pro ladění.|
|IDG_VS_CTXT_PROJECT_SCC|Příkazy pro správu zdrojového kódu.|
|IDG_VS_CTXT_PROJECT_TRANSFER|Příkazy pro vyjmutí, operace kopírování a vkládání.|
|IDG_VS_CTXT_PROJECT_PROPERTIES|Příkazy, které poskytují přístup k **vlastnosti projektu** dialogové okno.|

## <a name="see-also"></a>Viz také
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)
- [Vytváření znovu použitelných skupin tlačítek](../../extensibility/creating-reusable-groups-of-buttons.md)