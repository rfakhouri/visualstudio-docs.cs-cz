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
ms.workload: vssdk
ms.openlocfilehash: 815aac693686dc59d6934b00fb456c3a1afce72c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extending-menus-and-commands"></a>Rozšíření nabídek a příkazů
Příkazy jsou způsob přidání akce a procesů pro Visual Studio. Ve většině případů se zobrazí příkazy na nabídek a panelů nástrojů. Šablona projektu VSPackage ukazuje, jak implementovat velmi základní příkaz. Trochu déle, ale stále základní implementaci, najdete v části [vytvoření rozšíření pomocí příkazu v nabídce](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 Další informace o sadě Visual Studio příkazy, nabídek a panelů nástrojů najdete v tématu [příkazy, nabídek a panelů nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Příkazy, nabídek a panelů nástrojů jsou definovány v souboru .vsct, který je součástí VSPackage projekty. Může najít informace o prostředí Visual Studio IDE a soubor .vsct v [jak VSPackages přidat prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Následující témata popisují, jak přidat různé druhy příkazy, nabídek a panelů nástrojů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přidání nabídky do řádku nabídek v sadě Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)  
 Vysvětluje, jak přidat nabídku na začátek řádku nabídek v sadě Visual Studio.  
  
 [Vytváření vazeb mezi klávesovými zkratkami a položkami nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
 Vysvětluje, jak přidat klávesové zkratky (například CTRL + 3) na položku nabídky.  
  
 [Přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md)  
 Popisuje postup přidání podnabídky do hlavní nabídky.  
  
 [Přidání seznamu Naposledy použité do podnabídky](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md)  
 Vysvětluje, jak přidat seznam naposledy použitých.  
  
 [Vytváření znovu použitelných skupin tlačítek](../extensibility/creating-reusable-groups-of-buttons.md)  
 Popisuje, jak seskupit položky příkaz tak, aby jejich zahrnutí do více nabídek.  
  
 [Přidávání ikon k příkazům nabídky](../extensibility/adding-icons-to-menu-commands.md)  
 Popisuje postup přidání ikonu k příkazu na panelu nástrojů a nabídky.  
  
 [Změna textu příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md)  
 Popisuje použití `TextChanges` příznaku pro povolení položku nabídky se musí změnit dynamicky.  
  
 [Změna vzhledu příkazu](../extensibility/changing-the-appearance-of-a-command.md)  
 Popisuje, jak dynamicky povolit nebo zakázat příkaz.  
  
 [Aktualizace uživatelského rozhraní](../extensibility/updating-the-user-interface.md)  
 Popisuje, jak chcete vynutit aktualizaci uživatelského rozhraní tak, aby odrážela nedávné změny.  
  
 [Lokalizace příkazů nabídky](../extensibility/localizing-menu-commands.md)  
 Vysvětluje, jak k lokalizaci příkazy nabídky.  
  
## <a name="related-sections"></a>Související oddíly