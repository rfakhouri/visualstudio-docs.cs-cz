---
title: Rozšiřování nabídek a příkazů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- menus, common tasks
- VSPackages, menu tasks
- .vsct files, common menu tasks
ms.assetid: 7b2be4b9-e3fe-4412-874f-ae72ebc84c4b
caps.latest.revision: 50
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 20ec62586f9a725c1a33da60986d3c8729f0e402
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49260998"
---
# <a name="extending-menus-and-commands"></a>Rozšiřování nabídek a příkazů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Příkazy představují způsob, jak přidat akce a procesů pro Visual Studio. Ve většině případů se zobrazí příkazy nabídky nebo panely nástrojů. Šablona projektu VSPackage ukazuje, jak implementovat velmi základní příkaz. O něco déle, ale stále základní implementaci, najdete v části [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
 Další informace o sadě Visual Studio příkazy, nabídky a panely nástrojů, naleznete v tématu [příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Příkazy, nabídky a panely nástrojů jsou definovány v souboru .vsct, která je součástí balíčku VSPackage projekty. Můžete najít informace o integrovaném vývojovém prostředí sady Visual Studio a v souboru .vsct [jak balíčky VSPackages přidat prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md).  
  
 Následující témata popisují, jak přidat různé druhy příkazy, nabídky a panely nástrojů.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přidání nabídky do řádku nabídek v sadě Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)  
 Vysvětluje, jak přidat nabídku na začátek řádku nabídek sady Visual Studio.  
  
 [Vytváření vazeb mezi klávesovými zkratkami a položkami nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)  
 Vysvětluje, jak přidat klávesovou zkratku (například CTRL + 3) pro položku nabídky.  
  
 [Přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md)  
 Vysvětluje postup přidání podnabídky do hlavní nabídky.  
  
 [Přidání seznamu Naposledy použité do podnabídky](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md)  
 Vysvětluje, jak přidat seznamu naposledy použitých.  
  
 [Vytváření znovu použitelných skupin tlačítek](../extensibility/creating-reusable-groups-of-buttons.md)  
 Popisuje, jak seskupit položky příkazu, takže je jde zahrnout do více nabídek.  
  
 [Přidávání ikon k příkazům nabídky](../extensibility/adding-icons-to-menu-commands.md)  
 Popisuje, jak přidat ikonu příkaz na panelu nástrojů a nabídky.  
  
 [Změna textu příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md)  
 Popisuje použití `TextChanges` příznaku pro povolení položku nabídky dynamicky změnit.  
  
 [Změna vzhledu příkazu](../extensibility/changing-the-appearance-of-a-command.md)  
 Popisuje, jak dynamicky povolit nebo zakázat příkaz.  
  
 [Aktualizace uživatelského rozhraní](../extensibility/updating-the-user-interface.md)  
 Popisuje, jak vynutit aktualizaci uživatelského rozhraní tak, aby odrážely nejnovější změny.  
  
 [Lokalizace příkazů nabídky](../extensibility/localizing-menu-commands.md)  
 Vysvětluje, jak lokalizace příkazů nabídky.  
  
## <a name="related-sections"></a>Související oddíly

