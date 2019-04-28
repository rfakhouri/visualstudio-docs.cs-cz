---
title: -Upgrade (devenv.exe)
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0fa2e2eaa583f7da0437907fdaa3e7af2fe4a0e2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62789300"
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)

Aktualizuje soubor řešení a všechny jeho soubory projektu nebo souboru projektu zadána na aktuální formáty sady Visual Studio pro tyto soubory.

## <a name="syntax"></a>Syntaxe

```shell
devenv {SolutionFile|ProjectFile} /Upgrade [/Out OutputFilename]
```

## <a name="arguments"></a>Arguments

- *SolutionFile*

  Povinné, pokud upgradujete celé řešení a jeho projekty. Cesta a název souboru řešení. Můžete zadat pouze název souboru řešení nebo úplnou cestu a název souboru řešení. Pokud složka nebo soubor s názvem ještě neexistuje, vytvoří se.

- *ProjectFile*

  Povinné, pokud upgradujete jeden projekt. Cesta a název souboru projektu v rámci řešení. Můžete zadat pouze název souboru projektu nebo úplnou cestu a název souboru projektu. Pokud složka nebo soubor s názvem ještě neexistuje, vytvoří se.

- `/Out` *OutputFilename*

  Volitelné. Název souboru, který chcete odeslat nástroj výstupního. Pokud soubor již existuje, nástroj připojil výstupu na konci souboru.

## <a name="remarks"></a>Poznámky

Zálohy jsou automaticky vytvořeny a zkopírován do adresáře s názvem Zálohování, který je vytvořen v aktuálním adresáři.

Řešení se spravovanými zdroji nebo projekty musí být rezervován dříve, než je možné upgradovat.

Použití `/Upgrade` neotevře přepínače sady Visual Studio. Výsledky upgradu lze zobrazit v sestavě upgradu pro vývojový jazyk řešení nebo projektu. Vrátí se žádné informace o chybě nebo použití. Další informace o upgradu projektů v sadě Visual Studio najdete v tématu [Port, migrace a Upgrade projektů sady Visual Studio](../../porting/port-migrate-and-upgrade-visual-studio-projects.md).

## <a name="example"></a>Příklad

V tomto příkladu provede upgrade souboru řešení s názvem "MyProject.sln".

```shell
devenv "%USERPROFILE%\source\repos\MyProject\MyProject.sln" /upgrade
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)