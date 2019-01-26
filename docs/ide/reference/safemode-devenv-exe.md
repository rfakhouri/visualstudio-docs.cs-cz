---
title: -SafeMode (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b794c80768990a3abac85d3ea3b93699f3b220dd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54970432"
---
# <a name="safemode-devenvexe"></a>/SafeMode (devenv.exe)

Spustí v nouzovém režimu, načítají se jenom výchozí prostředí a služby Visual Studio.

## <a name="syntax"></a>Syntaxe

```shell
devenv /SafeMode
```

## <a name="remarks"></a>Poznámky

Tento přepínač brání načtení při spuštění sady Visual Studio, umožní stabilní provádění všech rozšíření VSPackages třetích stran.

## <a name="example"></a>Příklad

Následující příklad spustí Visual Studio v nouzovém režimu.

```shell
devenv /safemode
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)