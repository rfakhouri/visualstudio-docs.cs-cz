---
title: Najít v souborech – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- edit.findinfiles
helpviewer_keywords:
- Edit.FindInFiles command
- find in files command
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5549bd0047b38ef8f0dff5fa420d4b5ce0ae4ce9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62790258"
---
# <a name="find-in-files-command"></a>Najít v souborech – příkaz
Hledání souborů pomocí některé podsady z možností, které jsou k dispozici na **najít v souborech** karty **najít a nahradit** okna.

## <a name="syntax"></a>Syntaxe

```cmd
Edit.FindinFiles findwhat [/case] [/ext:extensions]
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]
[/text2] [/wild|/regex] [/word]
```

## <a name="arguments"></a>Arguments
 `findwhat` Povinné. Text tak, aby odpovídaly.

## <a name="switches"></a>Přepínače
 /Case nebo /c volitelné. Odpovídá dojde pouze v případě, že velká a malá písmena přesně odpovídá platformám zadaným v `findwhat` argument.

 /ext: `extensions` Volitelné. Určuje rozšíření souboru pro soubory k prohledání. Pokud není zadán, používá předchozí rozšíření, pokud dříve bylo zadáno.

 /lookin: `searchpath` Volitelné. Adresář pro hledání. Pokud cesta obsahuje mezery, uzavřete do uvozovek celou cestu.

 /Names nebo /n volitelné. Zobrazí seznam názvů souborů, které obsahují shody.

 / Options nebo /t volitelné. Zobrazí seznam aktuální nastavení možnosti hledání a nebude provádět vyhledávání.

 /Regex nebo /r volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzorů textu spíše než literálními znaky. Úplný seznam znaky regulárního výrazu, naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).

 / Reset nebo /e volitelné. Vrátí možnosti hledání na jejich výchozí nastavení a nebude provádět vyhledávání.

 / stop volitelné. Zastaví aktuální operace vyhledávání, pokud je v průběhu. Hledání ignoruje všechny argumenty při `/stop` nebyl zadán. Například chcete-li ukončit aktuální hledání zadáte následující:

```cmd
>Edit.FindinFiles /stop
```

 / Sub nebo /s volitelné. Vyhledá podsložky v adresáři uvedeném na /lookin:`searchpath` argument.

 /Text2 nebo /2 volitelné. Výsledky hledání se zobrazí v okně Najít výsledky 2.

 /Wild nebo /l volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.

 lze nebo /w volitelné. Vyhledá pouze celá slova.

## <a name="example"></a>Příklad
 Tento příklad vyhledá btnCancel ve všech souborech .cls umístěný ve složce "My projektů sady Visual Studio" a zobrazí informace o shodu v okně Najít výsledky 2.

```cmd
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2
```

## <a name="see-also"></a>Viz také

- [Najít v souborech](../../ide/find-in-files.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)