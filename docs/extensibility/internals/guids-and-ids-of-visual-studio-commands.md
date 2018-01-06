---
title: "Identifikátory příkazů sady Visual Studio a identifikátory GUID | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands
- id
- command placement
- visual studio command
- guid
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 44ae5ff7e9095d6c88d753342da30983b30b7364
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="guids-and-ids-of-visual-studio-commands"></a>Identifikátory příkazů sady Visual Studio a identifikátory GUID
Hodnoty GUID a ID příkazů zahrnuté v sadě Visual Studio integrované vývojové prostředí (IDE) jsou definovány v .vsct soubory, které jsou nainstalovány v rámci sady Visual Studio SDK. Další informace najdete v tématu [IDE-Defined příkazy, nabídky a skupiny](../../extensibility/internals/ide-defined-commands-menus-and-groups.md).  
  
 Další informace o tom, jak pracovat s objekty IDE, které jsou definovány v souborech .vsct najdete v tématu [rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).  
  
## <a name="finding-a-command-definition"></a>Hledání definice příkazu  
 Vzhledem k sadě Visual Studio definuje více než tisíc příkazy, je nepraktické všechny tady je seznam. Místo toho použijte následující postup najít definici příkazu.  
  
#### <a name="to-locate-a-command-definition"></a>Vyhledat definice příkazu  
  
1.  V sadě Visual Studio, otevřete následující soubory v *cesta instalace Visual Studio SDK*\VisualStudioIntegration\Common\Inc\ složky: SharedCmdDef.vsct, ShellCmdDef.vsct, VsDbgCmdUsed.vsct, Venusmenu.vsct.  
  
     Většina příkazů sady Visual Studio jsou definovány v SharedCmdDef.vsct a ShellCmdDef.vsct. VsDbgCmdUsed.vsct definuje příkazy, které se týkají ladicího programu a Venusmenu.vsct definuje příkazy, které jsou specifické pro vývoj webů.  
  
2.  Pokud je příkaz položku nabídky, poznamenejte si přesný text položky nabídky. Pokud je příkaz tlačítka na panelu nástrojů, poznamenejte si text popisku, který se zobrazí při přesunutí ukazatele myši na jeho.  
  
3.  Stisknutím kláves CTRL + F otevřete **najít** dialogové okno.  
  
4.  V **najít** zadejte text, který jste si poznamenali v kroku 2.  
  
5.  Ověřte, že **všechny otevřené dokumenty** se zobrazí v **Hledat v** pole.  
  
6.  Klikněte na tlačítko **najít další** tlačítko dokud text je vybraný v `<Strings>` části [Button Element](../../extensibility/button-element.md).  
  
     `<Button>` Element, který se zobrazí v příkazu je definice příkazu.  
  
 Nalezený příkaz definice můžete vložit kopii příkaz na jinou nabídku nebo panel nástrojů tak, že vytvoříte [CommandPlacement Element](../../extensibility/commandplacement-element.md) má stejné `guid` a `id` hodnoty jako příkaz. Další informace najdete v tématu [vytváření skupin opakovaně použitelného z tlačítka](../../extensibility/creating-reusable-groups-of-buttons.md).  
  
### <a name="special-cases"></a>Zvláštní případy  
 V následujících případech nabídky text nebo text popisku nemusí přesně odpovídat co je v definici příkazu.  
  
-   Položky nabídky, které obsahují znak podtržený, například **tiskových** příkaz na **souboru** nabídky, ve kterém je podtržený P.  
  
     Znaky, které jsou uvozená znakem 'a' v názvech položek nabídky se zobrazí jako podtržené. Ale .vsct soubory jsou zapsány v XML, který používá znak 'a' označíte, speciální znaky a vyžaduje, aby ampersand, které se mají zobrazit musí být vypsány jako&amp;'. Proto v souboru .vsct **P**tisknout příkazu se zobrazí jako "&amp;tiskových '.  
  
-   Příkazy, které mají dynamický text, například **Uložit** *aktuální Filename*a dynamicky generované položky nabídky, jako je například položek na **naposledy použitých souborů** seznamu.  
  
     Neexistuje žádný spolehlivý způsob, jak hledat na dynamický text. Místo toho najít skupinu, který je hostitelem požadovaného příkazu v součinnosti s [identifikátory GUID a ID nástroje Visual Studio nabídek](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) nebo [identifikátory GUID a ID nástroje Visual Studio panelů nástrojů](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)a vyhledávání na ID této skupiny. Pokud definice příkazu neobsahuje skupinu jako jeho [nadřazený Element](../../extensibility/parent-element.md), vyhledejte SharedCmdPlace.vsct a ShellCmdPlace.vsct (nebo VsDbgCmdPlace.vsct pro příkazů ladicího programu) `<CommandPlacement>` element, který nastaví nadřazeného tohoto příkaz. AndVsDbgCmdPlace.vsct SharedCmdPlace.vsct, ShellCmdPlace.vsct, jsou v *cesta instalace Visual Studio SDK*\VisualStudioIntegration\Common\Inc\ složky.  
  
## <a name="see-also"></a>Viz také  
 [MenuCommands Vs. OleMenuCommands](../../extensibility/menucommands-vs-olemenucommands.md)   
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [XML schéma VSCT – referenční informace](../../extensibility/vsct-xml-schema-reference.md)