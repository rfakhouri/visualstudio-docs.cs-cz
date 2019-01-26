---
title: Cesta k symbolu – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 3debe7c0a193cc0dc2c07875ebb32ac45a7741fb
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54949256"
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