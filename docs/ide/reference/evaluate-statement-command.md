---
title: Ohodnotit příkaz – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.evaluatestatement
helpviewer_keywords:
- Debug.EvaluateStatement command
- Evaluate Statement command
ms.assetid: 032039bc-9477-4f93-9b9d-66d4be0e90f4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b0be6e57c0c741420006d20c0945b9b8c8b77d51
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53864122"
---
# <a name="evaluate-statement-command"></a>Ohodnotit příkaz – příkaz
Vyhodnotí a zobrazí daný příkaz.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.EvaluateStatement text
```

## <a name="arguments"></a>Arguments
 `text` Povinné. Příkaz k vyhodnocení.

## <a name="remarks"></a>Poznámky
 V okně použité ke vstupu **EvaluateStatement** příkaz určuje, zda je znak rovná se (=) interpretován jako porovnávací operátor nebo jako operátor přiřazení.

 V **příkaz** okně znak rovná se (=) interpretován jako operátor porovnání. Tak například, pokud hodnoty proměnných `a` a `b` jsou odlišné, pak příkaz

```cmd
>Debug.EvaluateStatement(a=b)
```

 Vrátí hodnotu `false`.

 V **okamžité** okna, naopak znak rovná se (=) interpretován jako operátor přiřazení. Ano například příkaz

```cmd
>Debug.EvaluateStatement(a=b)
```

 přiřadí proměnné `a` hodnotu proměnné `b`.

## <a name="example"></a>Příklad

```cmd
>Debug.EvaluateStatement(a+b)
```

## <a name="see-also"></a>Viz také

- [Příkaz Tisk](../../ide/reference/print-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)