---
title: Nahradit v souborech – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- edit.replaceinfiles
helpviewer_keywords:
- Edit.ReplaceInFiles command
- Replace In Files command
- ReplaceInFiles command
ms.assetid: f116066a-4f65-4f2c-94ef-12cbd8cfb598
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a87b4dcff0bd626947a0d98822150d03fc7c7059
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945565"
---
# <a name="replace-in-files-command"></a>Nahradit v souborech – příkaz
Nahradí text v souborech pomocí některé podsady z možností, které jsou k dispozici na **nahradit v souborech** karty **najít a nahradit** okna.

## <a name="syntax"></a>Syntaxe

```
Edit.ReplaceinFiles findwhat replacewith [/all] [/case]
[/ext:extensions] [/keep] [/lookin:searchpath] [/options] [/regex]
[/reset] [/stop] [/sub] [/text2] [/wild] [/word]
```

## <a name="arguments"></a>Arguments
 `findwhat`

 Povinný parametr. Text tak, aby odpovídaly.

 `replacewith`

 Povinný parametr. Text, který nahradí odpovídající text.

## <a name="switches"></a>Přepínače
 / all nebo /

 Volitelné. Nahradí všechny výskyty hledaný text Nahrazovací text.

 /Case nebo /c

 Volitelné. Odpovídá dojde pouze v případě, že při velká a malá písmena přesně odpovídá platformám zadaným v `findwhat` argument.

 /ext: `extensions`

 Volitelné. Určuje rozšíření souboru pro soubory k prohledání.

 /Keep nebo /k

 Volitelné. Určuje, že všechny změněné soubory jsou ponechány otevřené.

 /lookin: `searchpath`

 Volitelné. Adresář pro hledání. Pokud cesta obsahuje mezery, uzavřete do uvozovek celou cestu.

 / Options nebo /t

 Volitelné. Zobrazí seznam aktuální nastavení možnosti hledání a nebude provádět vyhledávání.

 /Regex nebo/r

 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzorů textu spíše než literálními znaky. Úplný seznam znaky regulárního výrazu, naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).

 / Reset nebo /e

 Volitelné. Vrátí možnosti hledání na jejich výchozí nastavení a nebude provádět vyhledávání.

 /stop

 Volitelné. Zastaví aktuální operace vyhledávání, pokud je v průběhu. Nahradit ignoruje všechny argumenty při `/stop` nebyl zadán. Třeba zastavit aktuální nahrazení zadáte následující:

```
>Edit.ReplaceinFiles /stop
```

 / Sub nebo /s

 Volitelné. Vyhledá podsložky v adresáři uvedeném na /lookin:`searchpath` argument.

 /Text2 nebo /2

 Volitelné. Zobrazí výsledky v nahrazení **Najít výsledky 2** okna.

 /Wild nebo/l

 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.

 lze nebo /w

 Volitelné. Vyhledá pouze celá slova.

## <a name="example"></a>Příklad
 Tento příklad vyhledá `btnCancel` a nahradí jej s `btnReset` ve všech .cls soubory umístěné ve složce "Moje projekty sady visual studio" a zobrazí informace o nahrazení v **Najít výsledky 2** okna.

```
>Edit.ReplaceinFiles btnCancel btnReset /lookin:"c:/my visual studio projects" /ext:.cls /text2
```

## <a name="see-also"></a>Viz také

- [Hledání a nahrazení textu](../../ide/finding-and-replacing-text.md)
- [Nahradit v souborech](../../ide/replace-in-files.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)