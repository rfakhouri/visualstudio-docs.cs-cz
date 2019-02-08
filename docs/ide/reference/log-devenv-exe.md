---
title: -Log (devenv.exe)
ms.date: 12/12/2018
ms.topic: reference
helpviewer_keywords:
- Devenv, /Log switch
- Log switch [devenv.exe]
- /Log Devenv switch
ms.assetid: ae23c4ae-2376-4fe3-b8d2-81d34e61c8ba
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b2e11cb36176aec94528019cdd19bb5fa86c92b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907214"
---
# <a name="log-devenvexe"></a>/Log (devenv.exe)

Zaznamená veškerou aktivitu do souboru protokolu pro řešení potíží. Tento soubor se zobrazí poté, co jste volat `devenv /log` alespoň jednou. Ve výchozím nastavení soubor protokolu je umístěn zde:

**%APPDATA%\\Microsoft\\VisualStudio\\**\<Version\>**\\ActivityLog.xml**

kde \<verze\> je verze sady Visual Studio. Můžete ale zadat jiný název a cesta k souboru.

## <a name="syntax"></a>Syntaxe

```shell
devenv /Log NameOfLogFile
```

## <a name="arguments"></a>Arguments

- *NameOfLogFile*

  Povinný parametr. Úplná cesta a název souboru protokolu uložte.

## <a name="remarks"></a>Poznámky

Tento přepínač musí být uvedeny na konci příkazového řádku po všech ostatních přepínačích.

Protokol je zapsán pouze pro všechny instance sady Visual Studio, které jste otevřeli pomocí `/Log` přepnout.

## <a name="example"></a>Příklad

Tento příklad přesměruje protokolování, aby se `MyVSLog.xml` souboru do domovského adresáře uživatele.

```shell
devenv /log "%USERPROFILE%\MyVSLog.xml"
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)