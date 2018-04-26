---
title: Tisk – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7cf241ec0a9ff849b52761a241e84a15d287bb88
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="print-command"></a>Tisk – příkaz
Vyhodnotí výraz nebo zobrazí zadaný text.

## <a name="syntax"></a>Syntaxe

```
Debug.Print text
```

## <a name="arguments"></a>Arguments
 `text`

 Požadováno. Výraz k vyhodnocení nebo zobrazený text.

## <a name="remarks"></a>Poznámky
 Otazník (?) můžete použít jako alias pro tento příkaz. Tak například příkaz

```
>Debug.Print expA
```

 je také možné zapsat

```
>? expA
```

 Obě verze tento příkaz vrátí aktuální hodnotu výrazu `expA`.

## <a name="example"></a>Příklad

```
>Debug.Print varA
```

## <a name="see-also"></a>Viz také

- [Příkaz Ohodnotit příkaz](../../ide/reference/evaluate-statement-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)