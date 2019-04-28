---
title: Cesta k symbolu – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.symbolpath
helpviewer_keywords:
- symbol path command
- Debug.SymbolPath command
- SymbolPath command
ms.assetid: b697ef2d-3f5d-40df-b113-7068a5bec0d4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 23a7a59ca23dc444bcdc714ade2fce5bedb87e8c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945125"
---
# <a name="symbol-path-command"></a>Cesta k symbolu – příkaz
Nastaví seznam adresářů pro ladicí program pro hledání symbolů.

## <a name="syntax"></a>Syntaxe

```
Debug.SymbolPath pathname1;pathname2;... pathnameN
```

## <a name="arguments"></a>Arguments
 `pathname`

 Volitelné. Středníkem oddělený seznam cest ladicího programu pro hledání symbolů.

## <a name="remarks"></a>Poznámky
 Pokud ne `pathname` není zadán, příkaz vypíše aktuální cesty symbolů.

## <a name="example"></a>Příklad
 V tomto příkladu přidá dvě cesty do seznamu adresářů symbolů.

```
Debug.SymbolPath C:\Symbol Path 1;C:\Symbol Path 2
```

## <a name="example"></a>Příklad
 Tento příklad zobrazuje seznam oddělený středníkem aktuálních cest symbolu.

```
Debug.SymbolPath
```

## <a name="see-also"></a>Viz také

- [Příkazové okno](../../ide/reference/command-window.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)