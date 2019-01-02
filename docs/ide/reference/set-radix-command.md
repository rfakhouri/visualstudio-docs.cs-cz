---
title: Nastavit základ – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 93172b8ed16e2520c060671d12ef0ab35960f6ad
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829405"
---
# <a name="set-radix-command"></a>Nastavit základ – příkaz
Nastaví nebo vrátí číselný základ slouží k zobrazení hodnot typu integer.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.SetRadix [10 | 16 | hex | dec]
```

## <a name="arguments"></a>Arguments
 `10` nebo `16` nebo `hex` nebo `dec`

 Volitelné. Určuje desetinné číslo (10 nebo dec) nebo šestnáctkové číslo (maximálně 16 šestnáctkových). Pokud je argument vynechán, je vrácena aktuální hodnota Číselná soustava.

## <a name="example"></a>Příklad
 V tomto příkladu nastaví prostředí tak, aby zobrazení celočíselné hodnoty v šestnáctkovém formátu.

```cmd
>Debug.SetRadix hex
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)