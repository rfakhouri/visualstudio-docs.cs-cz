---
title: Zobrazit zpětný překlad – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- debug.listdisassembly
helpviewer_keywords:
- Debug.ListDisassembly command
- list disassembly command
ms.assetid: eb363e35-e86a-4121-966f-991210c27e2a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b175c6b7e0fcd145d58318d89707cfd907acb2c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913369"
---
# <a name="list-disassembly-command"></a>Zobrazit zpětný překlad – příkaz
Spustí proces ladění a umožňuje určit způsob zpracování chyb.

## <a name="syntax"></a>Syntaxe

```cmd
Debug.ListDisassembly [/count:number] [/endaddress:expression]
[/codebytes:yes|no] [/source:yes|no] [/symbolnames:yes|no]
[/linenumbers:yes|no]
```

## <a name="switches"></a>Přepínače
 Každý přepínač je možné vyvolat pomocí jeho dokončení formuláře nebo krátký tvar.

 / count: `number` [nebo] sady `number` [nebo] /length: `number` [nebo] l: `number`

 Volitelné. Počet instrukcí pro zobrazení. Výchozí hodnota je 8.

 /endaddress: `expression` [nebo] / e: `expression`

 Volitelné. Adresa, kam chcete zastavit zpětný překlad.

 /codebytes:`yes` &#124; `no` [nebo] /bytes:`yes` &#124; `no` [nebo] / b:`yes`&#124;`no`

 Volitelné. Označuje, zda chcete-li zobrazit kód bajtů. Výchozí hodnota je `no`.

 / source:`yes` &#124; `no` [nebo] / s:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit zdrojový kód. Výchozí hodnota je `no`.

 /symbolnames:`yes` &#124; `no` [nebo] /names:`yes` &#124; `no` [nebo] / n:`yes`&#124;`no`

 Volitelné. Označuje, zda chcete-li zobrazit názvy symbolů. Výchozí hodnota je `yes`.

 [/ linenumbers:`yes`&#124;`no`]

 Volitelné. Umožňuje zobrazení čísla řádků související se zdrojovým kódem. Přepínač/Source musí mít hodnotu `yes` /linenumbers přepínač.

## <a name="example"></a>Příklad

```cmd
>Debug.ListDisassembly
```

## <a name="see-also"></a>Viz také

- [Příkaz Listovat zásobník volání](../../ide/reference/list-call-stack-command.md)
- [Příkaz Listovat vlákna](../../ide/reference/list-threads-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)