---
title: Spustit – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.start
helpviewer_keywords:
- Start command
- Debug.Start command
ms.assetid: dc4e4aa2-b0ab-4e00-92db-6dc3058ddc21
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1e5ade7d02882633504ac5615ee751b2533adde
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="start-command"></a>Spustit – příkaz
Zahájí ladění spouštěný projekt.

## <a name="syntax"></a>Syntaxe

```
Debug.Start [address]
```

## <a name="arguments"></a>Arguments
 `address`

 Volitelné. Adresa, kdy program pozastaví spuštění, podobně jako zarážky ve zdrojovém kódu. Tento argument platí pouze v režimu ladění.

## <a name="remarks"></a>Poznámky
 **Spustit** příkaz po provedení provede operaci RunToCursor na zadanou adresu.

## <a name="example"></a>Příklad
 Tento příkaz spustí ladicího programu a ignoruje všechny výjimky, které dojít.

```
>Debug.Start
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)