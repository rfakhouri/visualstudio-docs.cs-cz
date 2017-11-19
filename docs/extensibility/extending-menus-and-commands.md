---
title: "Rozšíření nabídek a příkazů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- menus, common tasks
- VSPackages, menu tasks
- .vsct files, common menu tasks
ms.assetid: 7b2be4b9-e3fe-4412-874f-ae72ebc84c4b
caps.latest.revision: "49"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c53f836b6384968bf812ae9ae559a281fda6f13
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="extending-menus-and-commands"></a>Rozšíření nabídek a příkazů
Příkazy jsou způsob přidání akce a procesů pro Visual Studio. Ve většině případů se zobrazí příkazy na nabídek a panelů nástrojů. Šablona projektu VSPackage ukazuje, jak implementovat velmi základní příkaz. Trochu déle, ale stále základní implementaci, najdete v části [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 Další informace o sadě Visual Studio příkazy, nabídek a panelů nástrojů najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Příkazy, nabídek a panelů nástrojů jsou definovány v souboru .vsct, který je součástí VSPackage projekty. Může najít informace o prostředí Visual Studio IDE a soubor .vsct v [jak VSPackages přidat prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Následující témata popisují, jak přidat různé druhy příkazy, nabídek a panelů nástrojů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přidání nabídky na panelu nabídek Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)  
 Vysvětluje, jak přidat nabídku na začátek řádku nabídek v sadě Visual Studio.  
  
 [Vazba klávesové zkratky pro položky nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
 Vysvětluje, jak přidat klávesové zkratky (například CTRL + 3) na položku nabídky.  
  
 [Přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md)  
 Popisuje postup přidání podnabídky do hlavní nabídky.  
  
 [Přidání většina nedávno používá seznamu podnabídky](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md)  
 Vysvětluje, jak přidat seznam naposledy použitých.  
  
 [Vytváření opakovaně použitelných skupin tlačítek](../extensibility/creating-reusable-groups-of-buttons.md)  
 Popisuje, jak seskupit položky příkaz tak, aby jejich zahrnutí do více nabídek.  
  
 [Přidávání ikon na příkazy nabídky](../extensibility/adding-icons-to-menu-commands.md)  
 Popisuje postup přidání ikonu k příkazu na panelu nástrojů a nabídky.  
  
 [Změna Text příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md)  
 Popisuje použití `TextChanges` příznaku pro povolení položku nabídky se musí změnit dynamicky.  
  
 [Změna vzhledu příkazu](../extensibility/changing-the-appearance-of-a-command.md)  
 Popisuje, jak dynamicky povolit nebo zakázat příkaz.  
  
 [Aktualizace uživatelského rozhraní](../extensibility/updating-the-user-interface.md)  
 Popisuje, jak chcete vynutit aktualizaci uživatelského rozhraní tak, aby odrážela nedávné změny.  
  
 [Lokalizace příkazy nabídky](../extensibility/localizing-menu-commands.md)  
 Vysvětluje, jak k lokalizaci příkazy nabídky.  
  
## <a name="related-sections"></a>Související oddíly