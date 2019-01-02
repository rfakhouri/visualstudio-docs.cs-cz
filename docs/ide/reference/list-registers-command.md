---
title: Listovat registry – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 942ab10a1d660ea5e33ca2cb679e4655bd6b3fbc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53959960"
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
- [Základní informace o ladění: Registr – okno](../../debugger/debugging-basics-registers-window.md)
- [Postupy: Použití okna registry](../../debugger/how-to-use-the-registers-window.md)