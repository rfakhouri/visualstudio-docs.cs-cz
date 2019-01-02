---
title: Kukátko – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: ccc9c6af2a87502c2b651e91f7d935ffc7ae3474
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964478"
---
# <a name="watch-command"></a>Kukátko – příkaz
Vytvoří a otevře zadanou instanci **Watch** okna. Můžete použít **Watch** okna k výpočtu hodnoty proměnných, výrazů a registry, chcete-li tyto hodnoty upravit a uložit výsledky.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.Watch[index]
```

## <a name="arguments"></a>Arguments
 `index`

 Povinný parametr. Číslo instance okna kukátka.

## <a name="remarks"></a>Poznámky
 `index` Musí být celé číslo. Platné hodnoty jsou 1, 2, 3 nebo 4.

## <a name="example"></a>Příklad

```cmd
>Debug.Watch1
```

## <a name="see-also"></a>Viz také

- [Okna automatických a místních hodnot](../../debugger/autos-and-locals-windows.md)
- [Nastavení sledování u proměnných pomocí kukátko a Rychlé kukátko Windows v sadě Visual Studio](../../debugger/watch-and-quickwatch-windows.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)