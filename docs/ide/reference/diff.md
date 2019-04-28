---
title: -Diff (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- Devenv, /Diff switch
- /Diff Devenv switch
- Diff Devenv switch
ms.assetid: 5377fedb-632a-4e86-a947-7c11c86451e7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2e69435a319a9730af846a912cb3f90a12d4ac8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945780"
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

- *TargetFile*

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
