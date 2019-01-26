---
title: Přejít na – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fad99d77c7dc086e3e83f25b9ffea08fe60d914b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55012453"
---
# <a name="go-to-command"></a>Přejít na – příkaz
Přesune kurzor na zadaný řádek.

## <a name="syntax"></a>Syntaxe

```cmd
Edit.GoTo [linenumber]
```

## <a name="arguments"></a>Arguments
 `linenumber`

 Volitelné. Celé číslo představující číslo řádku, přejděte na.

## <a name="remarks"></a>Poznámky
 Číslování řádků začíná u jedné. Pokud hodnota `linenumber` je menší než 1, první řádek zobrazí. Pokud hodnota `linenumber` je větší než počet poslední řádek zobrazí poslední řádek.

 Pokud hodnotu `linenumber` není zadán, **přejít na řádek** zobrazí dialogové okno.

 Alias pro tento příkaz je GoToLn.

## <a name="example"></a>Příklad

```cmd
>Edit.GoTo 125
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)