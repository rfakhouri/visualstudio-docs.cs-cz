---
title: Nastavit základ – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.setradix
helpviewer_keywords:
- Set Radix command
- Debug.SetRadix command
ms.assetid: 6ffd1554-7530-4da4-b5f5-e276a5034f3b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f23e2492a183dcae2e2b3cb87e39b08f66a7c2ae
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="set-radix-command"></a>Nastavit základ – příkaz
Nastaví nebo vrátí číselný základní slouží k zobrazení celočíselné hodnoty.

## <a name="syntax"></a>Syntaxe

```
Debug.SetRadix [10 | 16 | hex | dec]
```

## <a name="arguments"></a>Arguments
 `10` nebo `16` nebo `hex` nebo `dec`

 Volitelné. Určuje desetinné číslo (10 nebo dec) nebo v šestnáctkové soustavě (16 nebo šestnáctkových). Pokud je argument vynechán, je aktuální hodnota základ – vrácena.

## <a name="example"></a>Příklad
 Tento příklad nastaví prostředí k zobrazení hodnot celé číslo v šestnáctkovém formátu.

```
>Debug.SetRadix hex
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)