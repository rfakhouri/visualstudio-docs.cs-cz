---
title: Listovat registry – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: 1113f7a4e1a61e6fe2954dfe8d98b9b2c52e6732
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="list-registers-command"></a>Listovat registry – příkaz
Zobrazí hodnotu vybrané zaregistruje a umožňuje upravit seznam registruje zobrazit.

## <a name="syntax"></a>Syntaxe

```
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]
[/Watch [{register|registerGroup}...]]
[/Unwatch [{register|registerGroup}...]]
```

## <a name="switches"></a>Přepínače
 / Zobrazení [{`register`&#124;`registerGroup`}...]

 Zobrazí hodnoty zadaného `register` nebo `registerGroup`. Pokud žádné `register` nebo `registerGroup` je zadán, zobrazí se výchozí seznam Registry. Pokud není zadán žádný přepínač, chování je stejné. Příklad:

 `Debug.ListRegisters /Display eax`

 je ekvivalentem

 `Debug.ListRegisters eax`

 Nebo jejich výpisu

 Zobrazí všechny skupiny registru v seznamu.

 Nebo si pusťte [{`register`&#124;`registerGroup`}...]

 Přidá jeden nebo více `register` nebo `registerGroup` hodnoty do seznamu.

 / Unwatch [{`register`&#124;`registerGroup`}...]

 Odebere jeden nebo více `register` nebo `registerGroup` hodnoty ze seznamu.

## <a name="remarks"></a>Poznámky
 Alias `r` lze místě `Debug.ListRegisters`.

## <a name="example"></a>Příklad
 Tento příklad používá `Debug.ListRegisters` alias `r` k zobrazení hodnot registrace skupiny `Flags`.

```
r /Display Flags
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Základní informace k ladění: Okno registrů](../../debugger/debugging-basics-registers-window.md)
- [Postupy: použití okna registry](../../debugger/how-to-use-the-registers-window.md)