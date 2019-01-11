---
title: -Rozdíly (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /Diff switch
- /Diff Devenv switch
- Diff Devenv switch
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cfe0fcdb039b4c7b234f3f43e6ce5741d96f5e9c
ms.sourcegitcommit: 01185dadd2fa1f9a040d2a366869f1a5e1d18e0f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/11/2019
ms.locfileid: "54227444"
---
# <a name="diff-devenvexe"></a>/ Diff (devenv.exe)

Porovná dva soubory. Rozdíly jsou zobrazeny v speciální okně aplikace Visual Studio.

## <a name="syntax"></a>Syntaxe

```shell
devenv /Diff SourceFile TargetFile [SourceDisplayName [TargetDisplayName]]
```

## <a name="arguments"></a>Arguments

- *zdrojový soubor*

  Povinný parametr. Úplná cesta a název prvního souboru, který se má porovnat.

- *Cílovýsoubor*

  Povinný parametr. Úplná cesta a název druhý soubor, který se má porovnat.

- *SourceDisplayName*

  Volitelné. Zobrazovaný název prvního souboru.

- *TargetDisplayName*

  Volitelné. Zobrazovaný název druhý soubor.
    
## <a name="remarks"></a>Poznámky

Pokud instanci integrovaného vývojového prostředí je už otevřená, porovnání souboru se zobrazí na kartě v aktuálním prostředí IDE.

## <a name="example"></a>Příklad

První příklad porovná dva soubory beze změny zobrazovaného jména. Druhý příklad porovná soubory během změny i zobrazovaného jména. Příklady třetí a čtvrtá porovnat dva soubory, ale použít alias pouze první soubor nebo druhý soubor.

```shell
devenv /diff File1.txt File2.txt

devenv /diff File1.txt File2.txt FirstAlias "Second Alias"

devenv /diff File1.txt File2.txt "File One"

devenv /diff File1.txt File2.txt "" FileTwo
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
