---
title: -LCID (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /L switch
- Devenv, /LCID switch
- locale IDs
- L Devenv switch
- /L Devenv switch
- LCID devenv switch
- /LCID Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 727f9c10d8f2d1eb2e1938821ad0cc0c1ae87b12
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972729"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)

Nastaví výchozí jazyk používaný pro text, měny a jiné hodnoty v rámci rozhraní IDE.

## <a name="syntax"></a>Syntaxe

```shell
devenv {/LCID|/L} LocaleID
```

## <a name="arguments"></a>Arguments

- *LocaleID*

  Povinný parametr. Identifikátor národního prostředí (LCID) jazyk, který zadáte.

## <a name="remarks"></a>Poznámky

Načte integrovaného vývojového prostředí a nastaví výchozí přirozeného jazyka pro prostředí. Tato změna je trvalá mezi relacemi a integrovaného vývojového prostředí se zobrazí tato změna **nástroje** > **možnosti** > **prostředí**  >  **Mezinárodní nastavení** > **jazyk** pole.

Pokud zadaný jazyk není k dispozici ve vašem systému `/LCID` přepínač je ignorován.

V následující tabulce jsou uvedeny LCID jazyků podporovaných v sadě Visual Studio.

|Jazyk|LCID|
|--------------|----------|
|Čínština (zjednodušená)|2052|
|Čínština (tradiční)|1028|
|Angličtina|1033|
|Francouzština|1036|
|Němčina|1031|
|Italština|1040|
|Japonština|1041|
|Korejština|1042|
|Španělština|3082|

## <a name="example"></a>Příklad

Tento příklad načte integrované vývojové prostředí s anglickou prostředky řetězců.

```shell
devenv /LCID 1033
```

## <a name="see-also"></a>Viz také:

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [Mezinárodní nastavení, Prostředí, dialogové okno Možnosti](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)