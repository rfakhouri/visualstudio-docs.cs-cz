---
title: Spustit – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0307bc8fef348aa408bf6d4fad53759df61806fb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54962820"
---
# <a name="start-command"></a>Spustit – příkaz
Zahájí projekt po spuštění ladění.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.Start [address]
```

## <a name="arguments"></a>Arguments
 `address`

 Volitelné. Adresa, na kterém program pozastaví provádění kódu, podobně jako na zarážku ve zdrojovém kódu. Tento argument je platná jenom v režimu ladění.

## <a name="remarks"></a>Poznámky
 **Start** při spuštění příkazu provádí operaci RunToCursor na zadanou adresu.

## <a name="example"></a>Příklad
 Tento příklad spustí ladicí program a ignoruje všechny výjimky, ke kterým dochází.

```cmd
>Debug.Start
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)