---
title: -DoNotLoadProjects (devenv.exe)
ms.date: 03/11/2019
ms.topic: reference
helpviewer_keywords:
- Devenv, /DoNotLoadProjects switch
- /DoNotLoadProjects Devenv switch
- DoNotLoadProjects Devenv switch
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91c4da26d202e1a23ff70a7c655f64fd6c05a340
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57875080"
---
# <a name="donotloadprojects-devenvexe"></a>/ DoNotLoadProjects (devenv.exe)

Otevře zadaný řešení bez načtení jakýchkoli projektů.

## <a name="syntax"></a>Syntaxe

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>Arguments

- *SolutionName*

  Povinný parametr. Úplná cesta a název řešení otevřít.

## <a name="example"></a>Příklad

Příklad otevře řešení za MySln.sln bez načtení jakýchkoli projektů.

```shell
devenv /donotloadprojects MySln.sln

```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
