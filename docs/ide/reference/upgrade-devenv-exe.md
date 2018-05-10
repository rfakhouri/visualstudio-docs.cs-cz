---
title: -Upgradu (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /upgrade Devenv switch
- Devenv, /upgrade switch
- upgrade Devenv switch
ms.assetid: 3468045c-5cc9-4157-9a9d-622452145d27
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 25fe5a4e75ddf349210a936f47d99c94ec70c240
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="upgrade-devenvexe"></a>/Upgrade (devenv.exe)
Aktualizuje soubor řešení a všechny jeho soubory projektu, nebo zadaný na aktuální soubor projektu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] formátech pro tyto soubory.

## <a name="syntax"></a>Syntaxe

```cmd
devenv SolutionFile | ProjectFile /upgrade
```

## <a name="arguments"></a>Arguments
 `SolutionFile`

 Vyžaduje, pokud provádíte upgrade celé řešení a jeho projekty. Cesta a název souboru, řešení. Můžete zadat pouze název souboru řešení, nebo úplnou cestu a název souboru řešení. Pokud složka nebo soubor s názvem ještě neexistuje, bude vytvořen.

 `ProjectFile`

 Vyžaduje, pokud provádíte upgrade jedné projektu. Cesta a název souboru projektu v rámci řešení. Můžete zadat jenom název souboru projektu, nebo úplnou cestu a název souboru projektu. Pokud složka nebo soubor s názvem ještě neexistuje, bude vytvořen.

## <a name="remarks"></a>Poznámky
 Zálohy jsou automaticky vytvořili a zkopírovali do adresář s názvem Zálohování, který je vytvořen v aktuálním adresáři.

 Projekty nebo řízenou zdroj řešení musí být rezervován, než může být upgradována.

 Pomocí `/upgrade` přepínač nespustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Výsledky upgradu můžete se zobrazí v sestavě upgradu pro jazyk vývoj řešení nebo projektu. Vrátí se žádné informace o chybě nebo využití. Další informace o upgrade projektů v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], najdete v části [Port, migrace a Upgrade projektů sady Visual Studio](../../porting/port-migrate-and-upgrade-visual-studio-projects.md).

## <a name="example"></a>Příklad
 Tento příklad upgraduje soubor řešení s názvem "MyProject.sln" do výchozí složky pro [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] řešení.

```cmd
devenv "MyProject.sln" /upgrade
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)