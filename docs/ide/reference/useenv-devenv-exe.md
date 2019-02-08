---
title: -UseEnv (devenv.exe)
ms.date: 01/10/2019
ms.topic: reference
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 37326bbe44eed15a562f0d28c01eac02973a2487
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55918894"
---
# <a name="useenv-devenvexe"></a>/UseEnv (devenv.exe)

Visual Studio spustí a načte určité proměnné prostředí pro kompilaci.

> [!NOTE]
> Tento přepínač je nainstalován se sadou **vývoj desktopových aplikací pomocí C++** pracovního vytížení.

## <a name="syntax"></a>Syntaxe

```shell
devenv /UseEnv {SolutionName|ProjectName}
```

## <a name="arguments"></a>Arguments

- *SolutionName*

  Úplná cesta a název souboru řešení.

- *ProjectName*

  Úplná cesta a název souboru projektu.

## <a name="remarks"></a>Poznámky

Visual Studio IDE ve vlastnostech projektu má vliv na tento přepínač **adresáře VC ++**. Pokud zadáte `/UseEnv` přepnout, **adresáře VC ++** uzlu se zobrazuje hodnoty pro CESTU, INCLUDE, LIBPATH a LIB proměnné prostředí. (Také zobrazuje hodnoty pro **adresáře zdrojových souborů** a **vyloučit adresáře**.) V opačném případě uzlu nahrazuje proměnné prostředí s pěti hodnot directory: **Adresáře spustitelných souborů**, **adresáře souborů k zahrnutí**, **odkazovat na adresáře**, **adresáře knihoven**, a **knihoven WinRT Adresáře**.

> [!TIP]
> Přístup k vlastnostem projektu tak, že kliknete pravým tlačítkem projekt jazyka C++ a vyberete **vlastnosti**. V **stránky vlastností** dialogu **vlastnosti konfigurace** a potom **adresáře VC ++**.

Když se tento přepínač je zadat název projektu, nástroj zobrazí proměnné prostředí pro všechny projekty v řešení nadřazeného projektu.

## <a name="example"></a>Příklad

Následující příklad spustí Visual Studio a načte proměnné prostředí na stránkách vlastností `MySolution` řešení.

```shell
devenv.exe /useenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln"
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [VC ++ Directories Property Page (Windows)](/cpp/ide/vcpp-directories-property-page)
