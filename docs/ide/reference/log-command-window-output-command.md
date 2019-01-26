---
title: Protokolovat výstup příkazového okna – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f582b4a2017985f6fcd1961c6da3899b3faa0180
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958807"
---
# <a name="log-command-window-output-command"></a>Protokolovat výstup příkazového okna – příkaz
Zkopíruje všechny vstup a výstup z **příkaz** okna do souboru.

## <a name="syntax"></a>Syntaxe

```cmd
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]
```

## <a name="arguments"></a>Arguments
 `filename`

 Volitelné. Název souboru protokolu. Ve výchozím nastavení je soubor vytvořen ve složce profilu uživatele. Pokud název souboru již existuje, protokol je připojen na konec existující soubor. Pokud není určen žádný soubor, poslední zadaný soubor se používá. Pokud neexistuje žádný předchozí soubor je vytvořen výchozí soubor protokolu, volá cmdline.log.

> [!TIP]
> Chcete-li změnit umístění pro uložení souboru protokolu, zadejte úplnou cestu souboru, ohraničená uvozovkami, pokud cesta obsahuje mezery.


## <a name="switches"></a>Přepínače
 /on

 Volitelné. Spuštění protokolu **příkaz** okno v zadaném souboru a přidá soubor s novými informacemi.

 / vypnuto

 Volitelné. V protokolu se zastaví **příkaz** okna.

 / overwrite

 Volitelné. Pokud soubor zadaný v `filename` argument odpovídá existující soubor, soubor se přepíše.

## <a name="remarks"></a>Poznámky
 Pokud není určen žádný soubor, vytvoří se soubor cmdline.log ve výchozím nastavení. Ve výchozím nastavení je alias pro tento příkaz protokolu.

## <a name="examples"></a>Příklady
 Tento příklad vytvoří nový soubor protokolu, cmdlog a spustí příkaz protokolu.

```cmd
>Tools.LogCommandWindowOutput cmdlog
```

 Tento příklad zastaví protokolování příkazy.

```cmd
>Tools.LogCommandWindowOutput /off
```

 Tento příklad pokračuje v protokolování příkazy v předchozích souboru protokolu.

```cmd
>Tools.LogCommandWindowOutput /on
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)