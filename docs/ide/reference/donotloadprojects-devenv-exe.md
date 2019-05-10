---
title: -DoNotLoadProjects (devenv.exe)
ms.date: 04/30/2019
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
ms.openlocfilehash: a414fde4dee401016e997fa5d6890da2ae8d9d53
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/06/2019
ms.locfileid: "65083936"
---
# <a name="donotloadprojects-devenvexe"></a>/ DoNotLoadProjects (devenv.exe)

**Novinka pro Visual Studio 2019 verze 16.1**

Otevře zadaný řešení bez načtení jakýchkoli projektů. Další informace najdete v tématu [filtrované řešení v sadě Visual Studio](../filtered-solutions.md).

## <a name="syntax"></a>Syntaxe

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>Arguments

*SolutionName*

Povinný parametr. Úplná cesta a název řešení otevřít.

## <a name="example"></a>Příklad

Příklad otevře řešení MySln.sln bez načtení jakýchkoli projektů.

```shell
devenv /donotloadprojects MySln.sln
```

## <a name="see-also"></a>Viz také:

- [Filtrované řešení v sadě Visual Studio](../filtered-solutions.md)
- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
