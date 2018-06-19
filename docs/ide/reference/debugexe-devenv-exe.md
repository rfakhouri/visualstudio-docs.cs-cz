---
title: -Debugexe – (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: 07dfcbb6064d0f1043c0621534b953a5f5c63e82
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704951"
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
Otevře zadaný spustitelný soubor chcete ladit.

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /debugexe ExecutableFile
```

## <a name="arguments"></a>Arguments
 `ExecutableFile`

 Požadováno. Název a cesta k souboru .exe.

 Pokud soubor .exe nebyl nalezen nebo pokud neexistuje, je nezobrazí žádná upozornění nebo chyby a [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] spustí běžným způsobem.

## <a name="remarks"></a>Poznámky
 Všechny řetězce následující `ExecutableFile` parametru jsou předány na daný soubor jako argumenty.

## <a name="example"></a>Příklad
 Následující příklad otevře soubor `MyApplication.exe` pro ladění.

```cmd
Devenv.exe /debugexe MyApplication.exe
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)