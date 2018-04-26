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
ms.openlocfilehash: 93d3e4323638d40f003247a2c5bd35c812cc1c69
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí po jste jste volali metodu `devenv /log` alespoň jednou. Ve výchozím nastavení je soubor protokolu:

 *Data aplikací %* \Microsoft\VisualStudio\\*verze*\ActivityLog.xml

 kde *verze* je verzi sady Visual Studio. Ale můžete určit jiný název a cesta k souboru.

## <a name="syntax"></a>Syntaxe

```
Devenv /log Path\NameOfLogFile
```

## <a name="remarks"></a>Poznámky
 Tento přepínač musí být uvedeny na konci příkazového řádku po všech ostatních přepínačích.

 Protokol je zapsán pro všechny instance sady Visual Studio, který jste volat pomocí přepínače/log. Ho nebude protokolu instancí sady Visual Studio, která jste volána bez přepínač.

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)