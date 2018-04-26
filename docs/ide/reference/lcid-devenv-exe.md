---
title: -LCID (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /LCID switch
- locale IDs
- /l Devenv switch
- LCID devenv switch
- /lcid Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 04c67b1b7d581a7e4b9d4309bfe432bf2a3298e4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
Nastaví výchozí jazyk používaný pro text, měny a dalších hodnot v rámci integrované vývojové prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```
devenv {/LCID|/l} LocaleID
```

## <a name="arguments"></a>Arguments
 `LocaleID` Vyžaduje se. LCID (ID národního prostředí) jazyk, který zadáte.

## <a name="remarks"></a>Poznámky
 Načte IDE a nastaví výchozí přirozeného jazyka pro prostředí. Tato změna se mezi relacemi trvalé a odrážejí na **mezinárodní nastavení** podokně **prostředí** možnosti v **možnosti** dialogového okna v prostředí IDE.

 Pokud zadaný jazyk není k dispozici v systému uživatele, přepínač LCID je ignorován.

 Následující tabulka uvádí identifikátor LCID jazyky nepodporuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

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
 Tento příklad načte IDE s řetězci anglické prostředky.

```
devenv /LCID 1033
```

## <a name="see-also"></a>Viz také

- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
- [Mezinárodní nastavení, prostředí, dialogové okno Možnosti](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)