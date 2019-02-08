---
title: -RunExit (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- RunExit Devenv switch
- Devenv, /RunExit switch
- /RunExit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3fa010e72267dadfb1974f7ce8be3b6b9a3e1cff
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936392"
---
# <a name="runexit-devenvexe"></a>/ RunExit (devenv.exe)

Zkompiluje a spustí zadaný projekt nebo řešení a potom jej zavře integrovaného vývojového prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```shell
devenv /RunExit {SolutionName|ProjectName} [/Out OutputFilename]
```

## <a name="arguments"></a>Arguments

- *SolutionName*

  Úplná cesta a název souboru řešení.

- *ProjectName*

  Úplná cesta a název souboru projektu.

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

Zkompiluje a spustí zadaný projekt nebo řešení podle nastavení nakonfigurovaného pro konfiguraci aktivního řešení. Tento přepínač minimalizuje rozhraní IDE při projekt nebo řešení je spustit. Ho ukončí rozhraní IDE po projekt nebo řešení po dokončení jeho běhu.

- Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.

- Souhrnné informace, včetně chyb, lze zobrazit v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/Out` přepnout.

## <a name="example"></a>Příklad

Tento příklad spustí řešení `MySolution` v minimalizovaném okně integrovaného vývojového prostředí pomocí konfigurace aktivního nasazení a poté ukončí rozhraní IDE.

```
devenv /runexit "%USERPROFILE%\source\repos\MySolution\MySolution.sln"
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [Nebo spuštění (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)