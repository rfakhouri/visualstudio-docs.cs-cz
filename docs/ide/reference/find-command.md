---
title: Najít – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf891b87de6e4e836aa4a710b3c5638db9e23919
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53965691"
---
# <a name="find-command"></a>Najít – příkaz
Hledá v souborech pomocí některé podsady z možností, které jsou k dispozici na **najít v souborech** karty **najít a nahradit** okna.

## <a name="syntax"></a>Syntaxe

```cmd
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]
```

## <a name="arguments"></a>Arguments
 `findwhat` Povinné. Text tak, aby odpovídaly.

## <a name="switches"></a>Přepínače
 /Case nebo /c volitelné. Odpovídá dojde pouze v případě, že velká a malá písmena přesně odpovídá platformám zadaným v `findwhat` argument.

 / DOC nebo /d volitelné. Vyhledá aktuálním dokumentu. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 /markall nebo /m – volitelné. Umístí obrázek na každém řádku, který obsahuje shodu hledání v rámci aktuálního dokumentu.

 /Open nebo /o volitelné. Vyhledá všechny otevřené dokumenty, jako by byly jeden dokument. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 / Options nebo /t volitelné. Zobrazí seznam aktuální nastavení možnosti hledání a nebude provádět vyhledávání.

 /proc nebo /p volitelné. Hledá aktuální proceduře. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 / Reset nebo /e volitelné. Vrátí možnosti hledání na jejich výchozí nastavení a nebude provádět vyhledávání.

 /sel nebo /s volitelné. Vyhledá pouze aktuální výběr. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.

 /Up nebo /u volitelné. Vyhledávání z aktuálního umístění v souboru směrem k začátku souboru. Ve výchozím nastavení začne hledání na aktuální pozici v souboru a hledání na konci souboru.

 /Regex nebo /r volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzorů textu spíše než literálními znaky. Úplný seznam znaky regulárního výrazu, naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).

 /Wild nebo /l volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.

 lze nebo /w volitelné. Vyhledá pouze celá slova.

## <a name="example"></a>Příklad
 Tento příklad vyhledá velká a malá písmena pro slovo "somestring" v aktuálně vybrané části kódu.

```cmd
>Edit.Find somestring /sel /case
```

## <a name="see-also"></a>Viz také

- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)