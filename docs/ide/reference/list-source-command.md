---
title: Listovat zdroj – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5348bd2533a10d98732911a6b7af5410e8ffe42
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55031627"
---
# <a name="list-source-command"></a>Listovat zdroj – příkaz
Zobrazí zadané řádky zdrojového kódu.

## <a name="syntax"></a>Syntaxe

```
Debug.ListSource [/Count:number] [/Current] [/File:filename]
[/Line:number] [/ShowLineNumbers:yes|no]
```

## <a name="switches"></a>Přepínače
 / Počet:`number`

 Volitelné. Určuje počet řádků k zobrazení.

 Nebo aktuální

 Volitelné. Zobrazí aktuální řádek.

 / Souboru:`filename`

 Volitelné. Cesta k souboru, který má zobrazit. Pokud není zadán žádný název souboru, příkaz zobrazuje zdrojový kód pro řádek aktuální příkaz.

 / Řádek:`number`

 Volitelné. Zobrazí konkrétní řádek určený číslem.

 /ShowLineNumbers:`yes|no`

 Volitelné. Určuje, jestli se mají zobrazovat čísla řádků.

## <a name="example"></a>Příklad
 V tomto příkladu obsahuje zdrojový kód z řádek 4 souboru Form1.vb, s čísly řádků viditelná.

```
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)