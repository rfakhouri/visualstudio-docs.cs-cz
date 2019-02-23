---
title: Rozšiřování nabídek a příkazů | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, common tasks
- VSPackages, menu tasks
- .vsct files, common menu tasks
ms.assetid: 7b2be4b9-e3fe-4412-874f-ae72ebc84c4b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c8f8d98525f1038b4a50dcaa5ca6237bd4c0f7b5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709262"
---
# <a name="extend-menus-and-commands"></a>Rozšíření nabídek a příkazů
Příkazy představují způsob, jak přidat akce a procesů pro Visual Studio. Ve většině případů se zobrazí příkazy nabídky nebo panely nástrojů. Šablona projektu VSPackage ukazuje, jak implementovat velmi základní příkaz. O něco déle, ale stále základní implementaci, najdete v části [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md).

 Další informace o sadě Visual Studio příkazy, nabídky a panely nástrojů, naleznete v tématu [příkazy, nabídky a panely nástrojů](../extensibility/internals/commands-menus-and-toolbars.md).

 Příkazy, nabídky a panely nástrojů, které jsou definovány v *.vsct* souboru, který je součástí balíčku VSPackage projekty. Může najít informace o integrovaném vývojovém prostředí sady Visual Studio a *.vsct* ve [jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../extensibility/internals/how-vspackages-add-user-interface-elements.md).

 Následující témata popisují, jak přidat různé druhy příkazy, nabídky a panely nástrojů.

## <a name="in-this-section"></a>V tomto oddílu
- [Přidání nabídky na řádku nabídek sady Visual Studio](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md) vysvětluje, jak přidat nabídku na horním řádku nabídek sady Visual Studio.

- [Vytvoření vazby klávesové zkratky a položkami nabídky](../extensibility/binding-keyboard-shortcuts-to-menu-items.md) vysvětluje, jak přidat klávesovou zkratku (například CTRL + 3) pro položku nabídky.

- [Přidání podnabídky do nabídky](../extensibility/adding-a-submenu-to-a-menu.md) vysvětluje postup přidání podnabídky do hlavní nabídky.

- [Přidat seznam naposledy použité do podnabídky](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md) vysvětluje, jak přidat seznamu naposledy použitých.

- [Vytváření znovu použitelných skupin tlačítek](../extensibility/creating-reusable-groups-of-buttons.md) popisuje, jak seskupit položky příkazu, takže je jde zahrnout do více nabídek.

- [Přidání ikon k příkazům nabídky](../extensibility/adding-icons-to-menu-commands.md) popisuje, jak přidat ikonu příkaz na panelu nástrojů a nabídky.

- [Změna textu příkazu nabídky](../extensibility/changing-the-text-of-a-menu-command.md) popisuje použití `TextChanges` příznaku pro povolení položku nabídky dynamicky změnit.

- [Změna vzhledu příkazu](../extensibility/changing-the-appearance-of-a-command.md) popisuje, jak dynamicky povolit nebo zakázat příkaz.

- [Aktualizace uživatelského rozhraní](../extensibility/updating-the-user-interface.md) popisuje, jak vynutit aktualizaci uživatelského rozhraní tak, aby odrážely nejnovější změny.

- [Lokalizace příkazů nabídky](../extensibility/localizing-menu-commands.md) vysvětluje, jak lokalizace příkazů nabídky.