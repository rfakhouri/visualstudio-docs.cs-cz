---
title: Nastavit aktuální proces
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Debug.SetCurrentProcess command
- Set Current Process command
ms.assetid: 1e016ebd-aadd-411f-a606-03bf69d3f8aa
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f139e204fe24b105c467f9698b78c1764521706c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54977132"
---
# <a name="set-current-process"></a>Nastavit aktuální proces
Nastavujte určený proces jako aktivní proces v ladicím programu.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.SetCurrentProcess index
```

## <a name="arguments"></a>Arguments
 `index`

 Povinný parametr. Index procesu.

## <a name="remarks"></a>Poznámky
 Můžete se připojit k více procesům při ladění, ale pouze jeden proces je v daném okamžiku aktivní v ladicím programu. Můžete použít `SetCurrentProcess` příkaz pro nastavení aktivního procesu.

## <a name="example"></a>Příklad

```cmd
>Debug.SetCurrentProcess 1
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)