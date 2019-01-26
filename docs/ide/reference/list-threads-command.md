---
title: Listovat vlákna – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.listthreads
helpviewer_keywords:
- ListThreads command
- list threads command
- Debug.ListThreads command
ms.assetid: 34b665c0-d46f-4c1a-a066-b678eba5ac54
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8f4d8706b41448289e5e653ee431ba56fb7d957f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031497"
---
# <a name="list-threads-command"></a>Listovat vlákna – příkaz
Zobrazí seznam vláken v aktuálním programu.

## <a name="syntax"></a>Syntaxe

```
Debug.ListThreads [index]
```

## <a name="arguments"></a>Arguments
 `index`

 Volitelné. Vybere vlákno podle jejich indexu bude aktuální vlákno.

## <a name="remarks"></a>Poznámky
 -Li zadána, `index` argument označí vláknu označený jako aktuální vlákno. Hvězdička (*) se zobrazí v seznamu vedle aktuální vlákno.

## <a name="example"></a>Příklad

```
>Debug.ListThreads
```

## <a name="see-also"></a>Viz také

- [Příkaz Listovat zásobník volání](../../ide/reference/list-call-stack-command.md)
- [Příkaz Zobrazit zpětný překlad](../../ide/reference/list-disassembly-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)