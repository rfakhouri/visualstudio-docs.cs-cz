---
title: Protokolovat výstup příkazového okna – příkaz
ms.date: 11/04/2016
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
ms.openlocfilehash: 588c5e39f8b6b6a89de1636bd45036b21d392d33
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55930529"
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