---
title: -LCID (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: f5c3f8633721a4568b81fab31d8fe91a4c33be2f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53852070"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
Nastaví výchozí jazyk používaný pro text, měny a jiné hodnoty v rámci integrovaného vývojového prostředí (IDE).

## <a name="syntax"></a>Syntaxe

```cmd
devenv {/LCID|/l} LocaleID
```

## <a name="arguments"></a>Arguments
 `LocaleID` Povinné. Identifikátor LCID (ID národního prostředí) jazyka, který zadáte.

## <a name="remarks"></a>Poznámky
 Načte integrovaného vývojového prostředí a nastaví výchozí přirozeného jazyka pro prostředí. Tato změna je trvalá mezi relacemi a projeví na **mezinárodní nastavení** podokně **prostředí** možnosti **možnosti** dialogového okna v rozhraní IDE.

 Pokud zadaný jazyk není k dispozici v systému uživatele, přepínač/LCID je ignorován.

 V následující tabulce jsou uvedeny LCID jazyky podporovanými [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].

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

```cmd
devenv /LCID 1033
```

## <a name="see-also"></a>Viz také

- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)
- [Mezinárodní nastavení, Prostředí, dialogové okno Možnosti](../../ide/reference/international-settings-environment-options-dialog-box.md)
- [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)