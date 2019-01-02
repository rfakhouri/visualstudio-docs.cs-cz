---
title: -DebugExe (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /DebugExe switch
- DebugExe switch
- /DebugExe [devenv.exe]
ms.assetid: cd700006-1648-418f-924b-4b1e5c1412ab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 99f256b47125f4e07ca5dc148c4351871389a94b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53889407"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
Otevře zadaný spustitelný soubor k ladění.

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /debugexe ExecutableFile
```

## <a name="arguments"></a>Arguments
 `ExecutableFile`

 Povinný parametr. Název a cesta k souboru .exe.

 Pokud soubor .exe se nenašel nebo neexistuje, je zobrazovat žádná upozornění ani chyby a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí běžným způsobem.

## <a name="remarks"></a>Poznámky
 Všechny řetězce po `ExecutableFile` parametru jsou předány do tohoto souboru jako argumenty.

## <a name="example"></a>Příklad
 Následující příklad otevře soubor `MyApplication.exe` pro ladění.

```cmd
Devenv.exe /debugexe MyApplication.exe
```

## <a name="see-also"></a>Viz také

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)