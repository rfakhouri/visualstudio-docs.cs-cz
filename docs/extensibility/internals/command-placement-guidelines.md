---
title: Příkaz pokyny pro umístění | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, small command sets
- small command sets
- command sets
ms.assetid: 63b3478e-e08a-420b-a0ec-76767e0cb289
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f4cc3dfa8aaeba01709ae74ca9a1d9d54f3c1743
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342115"
---
# <a name="command-placement-guidelines"></a>Pokyny pro umístění příkazu
Osvědčené postupy pro umístění příkazů v prostředí integrovaného vývojového (prostředí IDE) sady Visual Studio se liší v závislosti na velikosti sadu příkazů. Příkazy jsou definovány a umístěn podle informací v *.vsct* soubory.

## <a name="best-practices-for-all-command-sets"></a>Osvědčené postupy pro všechny sady příkazů
 Pro každou sadu příkazů postupujte podle následujících pokynů:

- Příprava grafu příkazovou strukturu předem. Identifikujte příkazy, pole se seznamem, skupiny příkazů a nabídek, které se použijí ve více než jedné oblasti.

- Příkazy, které se zobrazí ve stejné skupině by měl mít relace.

- Skupiny, které obsahují pouze jeden příkaz jsou přijatelné.

- Balíčky, neměli byste přidávat řadu příkazů na stávající nabídky sady Visual Studio. Místo toho by měl vytvořit nabídky a podnabídky k hostování nových příkazů.

- Když vložíte příkaz na existující nabídky, název příkazu tak, aby objasnili její účel a nebudete se zaměňovat s existující příkazy.

## <a name="best-practices-for-small-command-sets"></a>Osvědčené postupy pro malé příkaz sady
 Pokud vyvíjíte VSPackage, která má jen několik příkazů, také postupujte podle těchto pokynů:

- Pokud je to možné, použijte [nadřazené](../../extensibility/parent-element.md) prvek příkaz, pole se seznamem, skupině nebo nabídce podřízené jeho umístění do příslušné skupiny.

- Tyto skupiny přiřadíte nabídky zobrazí sady VSPackage.

- Aktivita nadřazená aktivitě podřízené nabídky nebo příkazu musí být [skupiny](../../extensibility/group-element.md) elementu. Přiřadit příkazů a nabídek podřízené skupiny a přiřaďte skupiny k nadřazené nabídky.

- V dalších skupinách můžete umístit příkaz tak, že přidáte [commandplacements –](../../extensibility/commandplacements-element.md) sekce prvku po definici příkazu a následným přidáním do `CommandPlacements` element [commandplacement –](../../extensibility/commandplacement-element.md) – element pro každou další skupiny.

## <a name="best-practices-for-large-command-sets"></a>Osvědčené postupy pro příkaz velké sady
 Pokud vaše VSPackage mnoho příkazů, které se zobrazí v několika kontextech, také dodržujte následující pokyny:

- Ujistěte se, nabídek, skupiny a příkazy svým nadřazenosti. To znamená, nepřiřazujte `Parent` element v definici položky.

- Použití `CommandPlacement` prvek položky `CommandPlacements` části elementu uvést nabídek, skupiny a příkazy do své nadřazené nabídky a skupiny.

- V `CommandPlacements` sekce prvku položky, která naplní dané nabídky nebo skupiny by měl nacházet mezi sebou. To pomáhá čitelnost a umožňuje `Priority` snadněji určit pořadí.

## <a name="see-also"></a>Viz také:
- [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Soubory tabulky (.vsct) příkaz pro Visual Studio](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)