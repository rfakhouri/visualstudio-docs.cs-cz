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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 83e79829caea30ece2c427d851b68d74bf9c586e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54943036"
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