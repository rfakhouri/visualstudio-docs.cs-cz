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
ms.openlocfilehash: de757e7022339b11f6d7c04ea7315abf685da24c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63428044"
---
# <a name="donotloadprojects-devenvexe"></a>/ DoNotLoadProjects (devenv.exe)

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
