---
title: Rychlé kukátko – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.quickwatch
helpviewer_keywords:
- Quick Watch command
- Debug.Quickwatch command
ms.assetid: 9670ac3a-8f2f-4874-974d-cb87d3b0cde1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5e45a6c63cb1f886c1440b93d58f944458f61290
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62811697"
---
# <a name="quick-watch-command"></a>Rychlé kukátko – příkaz
Zobrazí zadaný nebo vybraný text v poli výraz [QuickWatch](../../debugger/watch-and-quickwatch-windows.md) okna. Toto dialogové okno můžete použít k výpočtu aktuální hodnotu proměnné nebo výrazu rozpoznávaných ladicí program nebo obsah registru. Kromě toho můžete změnit hodnotu kterékoli proměnné nekonstantní nebo obsah jakékoli registru.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.QuickWatchq [text]
```

## <a name="arguments"></a>Arguments
 `text`

 Volitelné. Text, který má přidat **QuickWatch** dialogové okno.

## <a name="remarks"></a>Poznámky
 Pokud `text` je tento parametr vynechán, aktuálně vybraného textu nebo word na pozici kurzoru se přidá do okna kukátka.

## <a name="example"></a>Příklad

```cmd
>Debug.QuickWatch
```

## <a name="see-also"></a>Viz také

- [Nastavení sledování u proměnných pomocí kukátko a Rychlé kukátko Windows v sadě Visual Studio](../../debugger/watch-and-quickwatch-windows.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)