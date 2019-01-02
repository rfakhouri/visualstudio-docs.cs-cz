---
title: -Log (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: b0d2e6af25b4e0acc4aad88c33861e9d22a775b4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53846123"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)
Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí poté, co jste volat `devenv /log` alespoň jednou. Ve výchozím nastavení je soubor protokolu:

 *% APPDATA %* \Microsoft\VisualStudio\\*verze*\ActivityLog.xml

 kde *verze* je verze sady Visual Studio. Můžete ale zadat jiný název a cesta k souboru.

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /log Path\NameOfLogFile
```

## <a name="remarks"></a>Poznámky
 Tento přepínač musí být uvedeny na konci příkazového řádku po všech ostatních přepínačích.

 Protokol je zapsán pro všechny instance sady Visual Studio, které jste voláno s přepínačem/log. To není protokolu instance sady Visual Studio, který jste vyvolán bez přepínače.

## <a name="see-also"></a>Viz také

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)