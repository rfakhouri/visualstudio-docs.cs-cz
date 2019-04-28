---
title: Spustit – příkaz
ms.date: 11/04/2016
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
ms.openlocfilehash: 1f7488353cd4c64b0afca27060c364a1f9ddc6f8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62950440"
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