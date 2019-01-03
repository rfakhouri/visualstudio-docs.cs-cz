---
title: Nahradit – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- edit.replace
helpviewer_keywords:
- Edit.Replace command
- Replace command
ms.assetid: a15767f1-5a3d-44f5-8c77-7b0f1157f340
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b058b57897c369b4f7cc54b849d9abea3a1b6b15
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53989228"
---
# <a name="replace-command"></a>Nahradit – příkaz
Nahradí text v souborech pomocí některé podsady z možností, které jsou k dispozici na **nahradit v souborech** karty **najít a nahradit** okna.

## <a name="syntax"></a>Syntaxe

```
Edit.Replace findwhat replacewith [/all] [/case]
[/doc|/proc|/open|/sel] [/hidden] [/options] [/reset] [/up]
[/wild|/regex] [/word]
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

 / DOC nebo /d

 Volitelné. Vyhledá aktuálním dokumentu. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 / skrytý nebo/h

 Volitelné. Vyhledá skryté a sbalený text, například metadata ovládacího prvku návrhu, skryté oblasti osnovy dokumentu, nebo sbalené třídy nebo metody.

 /Open nebo /o

 Volitelné. Vyhledá všechny otevřené dokumenty, jako by byly jeden dokument. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 / Options nebo /t

 Volitelné. Zobrazí seznam aktuální nastavení možnosti hledání a nebude provádět vyhledávání.

 /proc nebo /p

 Volitelné. Hledá aktuální proceduře. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 /Regex nebo/r

 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzorů textu spíše než literálními znaky. Úplný seznam znaky regulárního výrazu, naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).

 / Reset nebo /e

 Volitelné. Vrátí možnosti hledání na jejich výchozí nastavení a nebude provádět vyhledávání.

 /sel nebo /s

 Volitelné. Vyhledá pouze aktuální výběr. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 /Up nebo /u

 Volitelné. Vyhledávání z aktuálního umístění v souboru směrem k začátku souboru. Ve výchozím nastavení začne hledání na aktuální pozici v souboru a ve spodní části souboru zálohy.

 /Wild nebo/l

 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.

 lze nebo /w

 Volitelné. Vyhledá pouze celá slova.

## <a name="example"></a>Příklad
 Tento příklad nahrazuje `btnSend` s `btnSubmit` ve všech otevřených dokumentech.

```
>Edit.Replace btnSend btnSubmit /open
```

## <a name="see-also"></a>Viz také

- [Hledání a nahrazení textu](../../ide/finding-and-replacing-text.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)