---
title: Nastavit aktuální rámec zásobníku – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.setcurrentstackframe
helpviewer_keywords:
- Set Current Stack Frame command
- Debug.SetCurrentStackFrame command
ms.assetid: 3dcf52c0-6781-4598-bac2-0094dce67c20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9eea69dc4d2931f66d4c6769667e23bdfb4eecf1
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938282"
---
# <a name="set-current-stack-frame-command"></a>Nastavit aktuální rámec zásobníku – příkaz
Umožňuje nastavit konkrétní rámec zásobníku.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.SetCurrentStackFrame index
```

## <a name="arguments"></a>Arguments
 `index`

 Povinný parametr. Vybere rámec zásobníku podle jejich indexu.

## <a name="example"></a>Příklad

```cmd
>Debug.SetCurrentStackFrame 1
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)