---
title: Kukátko – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.watch
helpviewer_keywords:
- Watch command
- Debug.Watch command
ms.assetid: aa02e647-d9f5-4905-a651-52a8df595795
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 97fe1c6865b8934d2c0329547e98323c75bf3ec0
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="watch-command"></a>Kukátko – příkaz
Vytvoří a otevře zadanou instanci systému **sledovat** okno. Můžete použít **sledovat** okno k výpočtu hodnot proměnných, výrazy a registrů, chcete-li upravit tyto hodnoty a uložte výsledky.

## <a name="syntax"></a>Syntaxe

```
Debug.Watch[index]
```

## <a name="arguments"></a>Arguments
 `index`

 Požadováno. Číslo instance okně Sledování.

## <a name="remarks"></a>Poznámky
 `index` Musí být celé číslo. Platné hodnoty jsou 1, 2, 3 nebo 4.

## <a name="example"></a>Příklad

```
>Debug.Watch1
```

## <a name="see-also"></a>Viz také

- [Automatické hodnoty a místní hodnoty – Windows](../../debugger/autos-and-locals-windows.md)
- [Nastavovat sledování na proměnné pomocí sledování a QuickWatch Windows v sadě Visual Studio](../../debugger/watch-and-quickwatch-windows.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)