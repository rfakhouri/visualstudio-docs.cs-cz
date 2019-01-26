---
title: -DebugExe (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
- debugging executables
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a93a582af62ed0eac8cdc0f5da55ac7bda555152
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55008969"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)

Otevře zadaný spustitelný soubor k ladění.

## <a name="syntax"></a>Syntaxe

```shell
devenv /DebugExe ExecutableFile
```

## <a name="arguments"></a>Arguments

- *ExecutableFile*

  Povinný parametr. Název a cesta k souboru `.exe` souboru. Pokud `.exe` soubor nebyl nalezen nebo pokud neexistuje, nezobrazí žádné upozornění ani chyby, a sady Visual Studio spustí běžným způsobem.

## <a name="remarks"></a>Poznámky

Všechny řetězce po *ExecutableFile* parametru jsou předány do tohoto souboru jako argumenty.

## <a name="example"></a>Příklad

Následující příklad otevře soubor `MyApplication.exe` pro ladění.

```shell
devenv /debugexe MyApplication.exe
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)