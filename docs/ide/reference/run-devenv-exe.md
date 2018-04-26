---
title: -Spustit (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /run Devenv
- run Devenv switch
- applications [Visual Studio], running
- /r Devenv switch
- Devenv, /run switch
- r Devenv switch (/r)
ms.assetid: b1f22f9d-39a5-4918-8a2a-4b5c1e872665
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b784b794945363afb2ea8955b5ad1bde96c36528
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="run-devenvexe"></a>/Run (devenv.exe)
Zkompiluje a spustí na zadaný projekt nebo řešení.

## <a name="syntax"></a>Syntaxe

```
devenv {/run|/r} {SolutionName|ProjectName}
```

## <a name="arguments"></a>Arguments
 `SolutionName`

 Požadováno. Úplná cesta a název souboru, řešení.

 `ProjectName`

 Požadováno. Úplná cesta a název souboru projektu.

## <a name="remarks"></a>Poznámky
 Zkompiluje a spustí na zadaný projekt nebo řešení podle nastavení zadaných pro konfiguraci aktivním řešení. Tento přepínač spustí integrované vývojové prostředí (IDE) a zůstane aktivní po projekt nebo řešení dokončení běhu.

-   Uzavřete řetězců, které obsahují mezery v uvozovkách.

-   Souhrnné informace, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.

## <a name="example"></a>Příklad
 Tento příklad spustí řešení `MySolution` pomocí konfigurace aktivní nasazení.

```
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [/ Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)