---
title: Tisk – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.print
helpviewer_keywords:
- Debug.Print command
- Print method
- Print command
ms.assetid: 0412d381-590a-483f-bab4-6e1cca095645
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1677e05668b8681976447ef9ee401624d82bdd9a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54939826"
---
# <a name="print-command"></a>Tisk – příkaz
Vyhodnotí výraz a zobrazí zadaný text.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.Print text
```

## <a name="arguments"></a>Arguments
 `text`

 Povinný parametr. Výraz k vyhodnocení nebo text k zobrazení.

## <a name="remarks"></a>Poznámky
 Otazník (?) můžete použít jako alias pro tento příkaz. Ano například příkaz

```cmd
>Debug.Print expA
```

 lze také zapsat

```cmd
>? expA
```

 Obě verze tohoto příkazu vrátí aktuální hodnotu výrazu `expA`.

## <a name="example"></a>Příklad

```cmd
>Debug.Print varA
```

## <a name="see-also"></a>Viz také

- [Příkaz Ohodnotit příkaz](../../ide/reference/evaluate-statement-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)