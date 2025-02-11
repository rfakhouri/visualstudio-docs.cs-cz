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
ms.openlocfilehash: 95edb5098d73e8fccb47f9f059473394afe5f542
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919113"
---
# <a name="list-registers-command"></a>Listovat registry – příkaz
Zobrazí hodnotu vybraných registrů a umožňuje upravit seznam registrů, které se mají zobrazit.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]
[/Watch [{register|registerGroup}...]]
[/Unwatch [{register|registerGroup}...]]
```

## <a name="switches"></a>Přepínače
/Display [{`register`&#124;`registerGroup`}...]

Zobrazí hodnoty zadaného `register` nebo `registerGroup`. Pokud není zadán `registerGroup` , nebojezadán,zobrazísevýchozíseznamregistrů.`register` Pokud není zadán žádný přepínač, chování je stejné. Příklad:

`Debug.ListRegisters /Display eax`

je ekvivalentem

`Debug.ListRegisters eax`

/List

Zobrazí všechny skupiny registrů v seznamu.

/Watch [{`register`&#124;`registerGroup`}...]

Přidá do seznamu jednu `register` nebo `registerGroup` více hodnot nebo.

/Unwatch [{`register`&#124;`registerGroup`}...]

Odebere ze seznamu jednu `register` nebo `registerGroup` více hodnot nebo.

## <a name="remarks"></a>Poznámky
Alias `r` lze použít `Debug.ListRegisters`místo.

## <a name="example"></a>Příklad
Tento příklad používá `Debug.ListRegisters` alias `r` k zobrazení hodnot skupiny `Flags`registrů.

```cmd
r /Display Flags
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Základy ladění: Okno Registry](../../debugger/debugging-basics-registers-window.md)
- [Postupy: Použití okna Registry](../../debugger/how-to-use-the-registers-window.md)