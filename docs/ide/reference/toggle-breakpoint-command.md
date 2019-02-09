---
title: Přepnout zarážku – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- debug.togglebreakpoint
helpviewer_keywords:
- ToggleBreakpoint command
- Debug.ToggleBreakPoint command
- Toggle Breakpoint command
ms.assetid: d50dfadb-ce79-4d5e-9c09-1cfddd57876d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 214897a0f938d8ea52306b8f605948b38f196111
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55970462"
---
# <a name="toggle-breakpoint-command"></a>Přepnout zarážku – příkaz
V závislosti na jejím aktuálním stavu na aktuální pozici v souboru se změní na zarážku, zapnout nebo vypnout.

## <a name="syntax"></a>Syntaxe

```
Debug.ToggleBreakpoint [text]
```

## <a name="arguments"></a>Arguments
 `text` Volitelné. Pokud je zadán text, na řádku je označena jako pojmenované zarážku. V opačném případě je řádku označena jako nepojmenované zarážky, které je podobné co se stane, když stisknete klávesu F9.

## <a name="example"></a>Příklad
 Následující příklad přepíná aktuální zarážku.

```
>Debug.ToggleBreakpoint
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)