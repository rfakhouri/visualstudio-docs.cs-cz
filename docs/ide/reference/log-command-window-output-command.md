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
ms.openlocfilehash: 6ab2dfea4c51ee33407088c208aea351732b8a4a
ms.sourcegitcommit: 9753c7544cec852ca5efd0834e0956d9e53a5734
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67043520"
---
# <a name="log-command-window-output-command"></a>Protokolovat příkaz výstupu příkazového okna

Zkopíruje všechny vstup a výstup z **příkaz** okna do souboru.

## <a name="syntax"></a>Syntaxe

```cmd
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]
```

## <a name="arguments"></a>Arguments

`filename`\
Volitelné. Název souboru protokolu. Ve výchozím nastavení je soubor vytvořen ve složce profilu uživatele. Pokud název souboru již existuje, protokol je připojen na konec existující soubor. Pokud není určen žádný soubor, poslední zadaný soubor se používá. Pokud neexistuje žádný předchozí soubor je vytvořen výchozí soubor protokolu, volá cmdline.log.

> [!TIP]
> Chcete-li změnit umístění pro uložení souboru protokolu, zadejte úplnou cestu souboru, ohraničená uvozovkami, pokud cesta obsahuje mezery.

## <a name="switches"></a>Přepínače

/on\
Volitelné. Spuštění protokolu **příkaz** okno v zadaném souboru a přidá soubor s novými informacemi.

/off\
Volitelné. V protokolu se zastaví **příkaz** okna.

/overwrite\
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

## <a name="see-also"></a>Viz také:

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Okno příkazového řádku](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Visual Studio aliasy příkazů](../../ide/reference/visual-studio-command-aliases.md)