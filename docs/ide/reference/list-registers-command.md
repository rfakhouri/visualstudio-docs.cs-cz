---
title: Listovat registry – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fb1a2361534f167a0b88b3f1b5b38c005915243d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62422962"
---
# <a name="list-registers-command"></a>Listovat registry – příkaz
Zobrazí hodnotu vybraného zaregistruje a vám umožní upravit seznam registrů, které mají zobrazit.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]
[/Watch [{register|registerGroup}...]]
[/Unwatch [{register|registerGroup}...]]
```

## <a name="switches"></a>Přepínače
 / Zobrazit [{`register`&#124;`registerGroup`}...]

 Zobrazí hodnoty zadaného `register` nebo `registerGroup`. Pokud ne `register` nebo `registerGroup` je zadán, zobrazí se výchozí seznam registrů. Pokud není zadán žádný přepínač, chování je stejné. Příklad:

 `Debug.ListRegisters /Display eax`

 je ekvivalentem

 `Debug.ListRegisters eax`

 / List

 Zobrazí všechny registrovat skupiny v seznamu.

 / Sledovat [{`register`&#124;`registerGroup`}...]

 Přidá jednu nebo více `register` nebo `registerGroup` hodnoty do seznamu.

 / Unwatch [{`register`&#124;`registerGroup`}...]

 Odebere jeden nebo více `register` nebo `registerGroup` hodnot v seznamu.

## <a name="remarks"></a>Poznámky
 Alias `r` lze použít místo `Debug.ListRegisters`.

## <a name="example"></a>Příklad
 V tomto příkladu `Debug.ListRegisters` alias `r` k zobrazení hodnot registru skupiny `Flags`.

```cmd
r /Display Flags
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Základy ladění: Okno Registry](../../debugger/debugging-basics-registers-window.md)
- [Postupy: Použití okna Registry](../../debugger/how-to-use-the-registers-window.md)