---
title: -NoSplash (devenv.exe)
ms.date: 12/10/2018
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /NoSplash switch
- /NoSplash Devenv switch
- NoSplash Devenv switch
author: DennisLee-DennisLee
ms.author: v-dele
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9a1e8118faa743398271fb282a2603aab5fcd76b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62950651"
---
# <a name="nosplash-devenvexe"></a>/ NoSplash (devenv.exe)

Zabrání se zobrazuje na úvodní obrazovce.

## <a name="syntax"></a>Syntaxe

```shell
devenv /NoSplash [File1[ FileN]...]
```

## <a name="arguments"></a>Arguments

- *File1*

  Volitelné. Soubor otevřete v existující instanci sady Visual Studio. Pokud neexistuje žádná instance sady Visual Studio, se vytvoří novou instanci se zjednodušeným rozložením okna a otevře se nástroj *File1* v nové instanci.

- *FileN*

  Volitelné. Nejméně jeden další soubor otevřete v existující instanci sady Visual Studio.

## <a name="remarks"></a>Poznámky

Tento přepínač se skryje možnost úvodní obrazovka. Přitom tento přepínač způsobí, že má být zobrazen na úvodní obrazovce. Pokud chcete prozkoumat úvodní obrazovka další (například ke kontrole VSPackage ikona produktu), použijte [/úvodní](../../extensibility/devenv-command-line-switches-for-vspackage-development.md) přepnout.

`/NoSplash` Přepínač je možné kombinovat s jinými přepínači, jako například [/Run](run-devenv-exe.md) nebo [/DebugExe](debugexe-devenv-exe.md).

## <a name="example"></a>Příklad

Všechny tři z příkladů otevření rozhraní IDE bez zobrazení úvodní obrazovka. V druhém příkladu také zkompiluje zadaný řešení a spustí připravené spustitelný soubor. Třetí příklad otevře zvolený spustitelný soubor pro ladění v rozhraní IDE.

```shell
devenv /nosplash

devenv /nosplash /run MySolution.sln

devenv /nosplash /debugexe MySolution.exe
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [Přepínače příkazového řádku nástroje DEVENV pro vývoj rozšíření VSPackage](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
