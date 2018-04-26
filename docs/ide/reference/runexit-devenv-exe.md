---
title: -Runexit (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- runexit Devenv switch
- Devenv, /runexit switch
- /runexit Devenv switch
ms.assetid: bfc94875-5fc0-4110-b961-d59c0b403790
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e2ce262b219b46d543389ac6a8ae8d71466419f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="runexit-devenvexe"></a>/Runexit (devenv.exe)
Zkompiluje a běží na zadaný projekt nebo řešení a poté uzavře integrované vývojové prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```
devenv /runexit {SolutionName|ProjectName}
```

## <a name="arguments"></a>Arguments
 `SolutionName`

 Požadováno. Úplná cesta a název souboru, řešení.

 `ProjectName`

 Požadováno. Úplná cesta a název souboru projektu.

## <a name="remarks"></a>Poznámky
 Zkompiluje a spustí na zadaný projekt nebo řešení podle nastavení zadaných pro konfiguraci aktivním řešení. Tento přepínač minimalizuje IDE při projekt nebo řešení běží a toto okno zavře IDE po projekt nebo řešení dokončení běhu.

-   Uzavřete řetězců, které obsahují mezery v uvozovkách.

-   Souhrnné informace, včetně chyb, můžete zobrazit v **příkaz** okno, nebo v jakékoli souboru protokolu zadaný `/out` přepínače.

## <a name="example"></a>Příklad
 Tento příklad spustí řešení `MySolution` v minimalizovaném okně IDE pomocí konfigurace aktivní nasazení a poté uzavře rozhraní IDE.

```
devenv /runexit "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln"
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [Nebo spusťte (devenv.exe)](../../ide/reference/run-devenv-exe.md)
- [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)