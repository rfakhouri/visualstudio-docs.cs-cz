---
title: -UseEnv (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- VC.Project.UseEnvVars.ExcludePath
- VC.Project.UseEnvVars.LibraryPath
- VC.Project.UseEnvVars.SourcePath
- VC.Project.UseEnvVars.Include
- VC.Project.UseEnvVars.Path
- VC.Project.UseEnvVars.ReferencePath
helpviewer_keywords:
- UseEnv switch
- /UseEnv Devenv switch
- Devenv, /UseEnv
ms.assetid: 2dd14603-a61b-42d2-ba31-427a0ee8a799
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fd76e44b2e503bd7b444e83bb9a64abceeaa561
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="useenv-devenvexe"></a>/UseEnv (devenv.exe)

Spuštění sady Visual Studio a načte proměnné prostředí do **adresáře VC ++** dialogové okno.

> [!NOTE]
> Tento přepínač. je nainstalovaná se systémem **vývoj aplikací s jazykem C++** zatížení.

## <a name="syntax"></a>Syntaxe

```shell
Devenv /useenv
```

## <a name="example"></a>Příklad

V následujícím příkladu spustí Visual Studio a načte proměnné prostředí do **adresáře VC ++** dialogové okno.

```shell
Devenv.exe /useenv
```

## <a name="see-also"></a>Viz také

* [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)