---
title: Seznam úkolů, prostředí, dialogové okno Možnosti
ms.date: 03/28/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.Task_List
- VS.ToolsOptionsPages.Environment.TaskList
- VS.Environment.Task List
helpviewer_keywords:
- Token List
- tokens
- icons, in Task List
- Task List, customizing environment
- Options dialog box, Task List environment
- exclamation points
- comments, comment tasks in Task List
- tokens, and the Task List
- Task List, comment tasks
ms.assetid: 88327e04-fa3e-48db-995b-ad89e0dc4ed2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b2fc59a2f04dc30ef8b052e93fc6ffdf030e054
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945024"
---
# <a name="options-dialog-box-environment--task-list"></a>Dialogové okno Možnosti: Prostředí \> seznamu úloh

Tato stránka možností umožňuje přidat, odstranit a změnit tokeny komentáře, které generují **seznamu úkolů** připomenutí. Chcete-li zobrazit tato nastavení, vyberte **možnosti** z **nástroje** nabídky, rozbalte **prostředí** složky a zvolte **seznamu úkolů**.

## <a name="task-list-tokens"></a>Tokeny seznamu úkolů

Při vložení komentář do svého kódu, jejichž text začíná s tokenem od **Token seznam**, **seznamu úkolů** komentáře jako nová položka se zobrazí pokaždé, když je soubor otevřen pro úpravy. Klikněte na tlačítko **seznamu úkolů** položky můžete přejít přímo na řádku komentáře v kódu. Další informace najdete v tématu [pomocí seznamu úkolů](../../ide/using-the-task-list.md).

Token List\
Zobrazí seznam tokenů a umožňuje přidat nebo odebrat vlastní tokeny. Tokeny komentáře jsou malá a velká písmena v C# a C++, ale ne v jazyce Visual Basic.

> [!NOTE]
> Pokud nezadáte požadovaný token přesně tak, jak se zobrazí v seznamu tokenů, úkolu komentář se nezobrazí v **seznamu úkolů**.

Priority\
Nastaví prioritu úlohy, které používají vybraný token (nízká, normální nebo vysoká). Komentáře k úkolu, které začínají s tímto tokenem jsou automaticky přiřazeny určené priority v **seznamu úkolů**.

Name\
Zadejte řetězec tokenu tady a pak klikněte na tlačítko **přidat** přidat řetězec do seznam tokenů.

Add\
Povolený při zadání nového **název**. Klikněte na tlačítko Přidat nový řetězec tokenu pomocí zadaných hodnot **název** a **Priority** pole.

Delete\
Kliknutím můžete odstranit vybraný token v seznamu tokenů. Nelze odstranit výchozí token komentář.

Change\
Kliknutím provést změny existujícího tokenu pomocí zadaných hodnot **název** a **Priority** pole.

> [!NOTE]
> Nelze přejmenovat nebo odstranit výchozí token komentář, ale můžete změnit jeho úroveň priority.

## <a name="see-also"></a>Viz také:

- [Používání seznamu úkolů](../../ide/using-the-task-list.md)
- [Nastavení záložek v kódu](../../ide/setting-bookmarks-in-code.md)
- [Prostředí, dialogové okno Možnosti](../../ide/reference/environment-options-dialog-box.md)