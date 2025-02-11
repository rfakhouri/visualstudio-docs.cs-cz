---
title: Příkazové okno
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.CommandWindow
helpviewer_keywords:
- IDE, Command window
- Mark mode in Command window
- Command window
- Command mode in Command window
- IDE Command window
ms.assetid: 48711628-1909-4713-a73e-d7b714c77f8a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fe707d82354a8c947dfa89a7323b41a489d0fa8
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919298"
---
# <a name="command-window"></a>Příkazové okno
**Příkazové** okno se používá ke spouštění příkazů nebo aliasů přímo v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaném vývojovém prostředí (IDE). Příkazy nabídky a příkazy, které se nezobrazí v žádné nabídce, můžete spustit. Chcete-li zobrazit **příkazové** okno, zvolte možnost **Další okna** v nabídce **zobrazení** a vyberte **příkazová okna**.

## <a name="displaying-the-values-of-variables"></a>Zobrazení hodnot proměnných
Chcete-li zjistit hodnotu proměnné `varA`, použijte [příkaz Print](../../ide/reference/print-command.md):

```cmd
>Debug.Print varA
```

Otazník (?) je alias pro `Debug.Print`, takže tento příkaz lze také zapsat:

```cmd
>? varA
```

Obě verze tohoto příkazu vrátí hodnotu proměnné `varA`.

## <a name="entering-commands"></a>Zadávání příkazů
Symbol větší než (`>`) se zobrazí na levém okraji okno příkaz jako výzva pro nové řádky. Pomocí kláves Šipka nahoru a šipka dolů můžete procházet předchozí vydané příkazy.

|Úloha|Řešení|Příklad|
|----------|--------------|-------------|
|Vyhodnotit výraz.|Předtvářte výraz s otazníkem (`?`).|`? myvar`|
|Přepněte do příkazového podokna.|Zadejte `immed` do okna bez znaménka větší než (>).|`immed`|
|Přepněte zpět na okno Příkaz z příkazového podokna.|Do `cmd` okna zadejte.|`>cmd`|

Následující klávesové zkratky vám pomůžou s navigací v režimu příkazu.

|Akce|Umístění kurzoru|KeyBinding teprve|
|------------| - |----------------|
|Procházení seznamu dříve zadaných příkazů|Vstupní řádek|ŠIPKA NAHORU & ŠIPKA DOLŮ|
|Posuňte se do okna.|Obsah okno Příkaz|CTRL + ŠIPKA NAHORU|
|Posuňte se dolů na okno.|Obsah okno Příkaz|Šipka dolů nebo CTRL + šipka dolů|

> [!TIP]
> Můžete zkopírovat celý nebo celý předchozí příkaz na vstupní řádek tak, že ho posunete, zvýrazníte jeho část nebo jeho část a potom stisknete klávesu ENTER.

## <a name="mark-mode"></a>Režim označení
Když kliknete na libovolný předchozí řádek v **příkazovém** okně, automaticky se posune do režimu označení. To vám umožní vybrat, upravit a zkopírovat text předchozích příkazů jako v libovolném textovém editoru a vložit je do aktuálního řádku.

## <a name="the-equals--sign"></a>Symbol rovná se (=)
Okno použité k zadání `EvaluateStatement` příkazu určuje, zda je znak rovná se (=) interpretován jako operátor porovnání nebo jako operátor přiřazení.

V **příkazovém** okně je znak rovná se (=) interpretován jako operátor porovnání. V **příkazovém** okně nemůžete použít operátory přiřazení. Takže pokud `varA` se například hodnoty proměnných `varB` liší, pak příkaz `>Debug.EvaluateStatement(varA=varB)` vrátí hodnotu `False`.

V **příkazovém podokně** je naopak znak rovná se (=) interpretován jako operátor přiřazení. Například příkaz `>Debug.EvaluateStatement(varA=varB)` přiřadí proměnné `varA` hodnotu proměnné `varB`.

## <a name="parameters-switches-and-values"></a>Parametry, přepínače a hodnoty
Některé [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] příkazy mají požadované a nepovinné argumenty, přepínače a hodnoty. Určitá pravidla platí při obchodování s takovými příkazy. V následujícím příkladu je k dispozici příklad bohatých příkazů k objasnění terminologie.

```cmd
Edit.ReplaceInFiles /case /pattern:regex var[1-3]+ oldpar
```

V tomto příkladu

- `Edit.ReplaceInFiles`je příkaz

- `/case`a `/pattern:regex` jsou přepínače (před znakem lomítka [/])

- `regex`je hodnota `/pattern` přepínače `/case` ; přepínač nemá žádnou hodnotu.

- `var[1-3]+`a `oldpar` jsou parametry

    > [!NOTE]
    > Všechny příkazy, parametry, přepínače nebo hodnoty, které obsahují mezery, musí mít na obou stranách dvojité uvozovky.

Pozice přepínačů a parametrů lze volně měnit na příkazovém řádku s výjimkou příkazu [Shell](../../ide/reference/shell-command.md) , který vyžaduje jeho přepínače a parametry v určitém pořadí.

Skoro každý přepínač podporovaný příkazem má dvě formy: krátký tvar (jeden znak) a dlouhý tvar. Do skupiny lze sloučit více přepínačů s krátkým tvarem. Například `/p /g /m` může být vyjádřena Alternativně jako `/pgm`.

Pokud jsou zkrácené přepínače kombinovány do skupiny a zadány hodnoty, tato hodnota se vztahuje na každý přepínač. Například je `/pgm:123` rovno `/p:123 /g:123 /m:123`. Pokud některý z přepínačů ve skupině nepřijímá hodnotu, dojde k chybě.

## <a name="escape-characters"></a>Řídicí znaky
Znak stříšky (^) na příkazovém řádku znamená, že znak bezprostředně za ním je interpretován doslova, nikoli jako řídicí znak. To slouží k vložení uvozovek ("), mezer, úvodních lomítek, střížek nebo jakýmikoli literálními znaky parametru nebo hodnotě switch s výjimkou názvů switchů. Například

```cmd
>Edit.Find ^^t /regex
```

Stříška funguje stejně, ať už se jedná o vnitřní nebo vnější uvozovky. Pokud poslední znak na řádku stříška, je ignorován. Zde uvedený příklad ukazuje, jak vyhledat vzor "^ t".

## <a name="use-quotes-for-path-names-with-spaces"></a>Použití uvozovek pro názvy cest s mezerami
Pokud například chcete otevřít soubor, který obsahuje cestu obsahující mezery, je nutné umístit dvojité uvozovky kolem cesty nebo segmentu cesty, který obsahuje mezery: **C:\\"Program Files"** nebo **"C:\Program Files"** .

## <a name="see-also"></a>Viz také

- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)