---
title: -Protokolu (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3373f1e1a23ae0373a9c49a39a924398ebe143e0
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí po jste jste volali metodu `devenv /log` alespoň jednou. Ve výchozím nastavení je soubor protokolu:

 *Data aplikací %* \Microsoft\VisualStudio\\*verze*\ActivityLog.xml

 kde *verze* je verzi sady Visual Studio. Ale můžete určit jiný název a cesta k souboru.

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /log Path\NameOfLogFile
```

## <a name="remarks"></a>Poznámky
 Tento přepínač musí být uvedeny na konci příkazového řádku po všech ostatních přepínačích.

 Protokol je zapsán pro všechny instance sady Visual Studio, který jste volat pomocí přepínače/log. Ho nebude protokolu instancí sady Visual Studio, která jste volána bez přepínač.

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)