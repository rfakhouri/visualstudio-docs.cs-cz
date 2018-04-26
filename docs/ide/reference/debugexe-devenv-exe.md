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
ms.openlocfilehash: 065648588b51ad6c71ae1a10235da4f096470abe
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="debugexe-devenvexe"></a>/DebugExe (devenv.exe)
Otevře zadaný spustitelný soubor chcete ladit.

## <a name="syntax"></a>Syntaxe

```
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

```
Devenv.exe /debugexe MyApplication.exe
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)