---
title: Listovat zásobník volání – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listcallstack
helpviewer_keywords:
- list call stack command
- Debug.ListCallStack command
ms.assetid: a8b20bf2-81d2-4069-aea8-23e6b15b4347
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e5fb8bd8b0f0f550e6fa1253f778895af0472be
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="list-call-stack-command"></a>Listovat zásobník volání – příkaz
Zobrazí aktuální zásobníku volání.

## <a name="syntax"></a>Syntaxe

```
Debug.ListCallStack [/Count:number] [/ShowTypes:yes|no]
[/ShowNames:yes|no] [/ShowValues:yes|no] [/ShowModule:yes|no]
[/ShowLineOffset:yes|no] [/ShowByteOffset:yes|no]
[/ShowLanguage:yes|no] [/IncludeCallsAcrossThreads:yes|no]
[/ShowExternalCode:yes|no] [Thread:n] [index]
```

## <a name="arguments"></a>Arguments
 `index` Volitelný parametr. Nastaví aktuální rámec zásobníku a zobrazí žádný výstup.

## <a name="switches"></a>Přepínače
 Každý přepínač lze vyvolat pomocí jeho dokončení formuláře nebo zkrácené formě.

 / Počet:`number` [nebo] / c:`number`

 Volitelné. Maximální počet zásobníky volání k zobrazení. Výchozí hodnota neomezená.

 / ShowTypes:`yes` &#124; `no` [nebo] / t:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit typy parametrů. Výchozí hodnota je `yes`.

 / ShowNames:`yes` &#124; `no` [nebo] / n:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit názvy parametrů. Výchozí hodnota je `yes`.

 / ShowValues:`yes` &#124; `no` [nebo] / v:`yes`&#124;`no`

 Volitelné. Určuje, jestli se mají zobrazovat hodnoty parametrů. Výchozí hodnota je `yes`.

 / ShowModule:`yes` &#124; `no` [nebo] / m:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit na název modulu. Výchozí hodnota je `yes`.

 / ShowLineOffset:`yes` &#124; `no` [nebo] /#:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit posun řádku. Výchozí hodnota je `no`.

 / ShowByteOffset:`yes` &#124; `no` [nebo] / b:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit posun bajtů. Výchozí hodnota je `no`.

 / ShowLanguage:`yes` &#124; `no` [nebo] l:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit jazyk. Výchozí hodnota je `no`.

 / IncludeCallsAcrossThreads:`yes` &#124; `no` [nebo] / i:`yes`&#124;`no`

 Volitelné. Určuje, jestli zahrnují volání do nebo z jiných vláken. Výchozí hodnota je `no`.

 / ShowExternalCode:`yes`&#124;`no`

 Volitelné. Určuje, jestli se má zobrazit pouze můj kód pro zásobník volání. Když pouze můj kód je vypnutý, zobrazí se všechny bez uživatelského kódu. Pokud pouze můj kód na, zobrazí se jiný uživatelský kód jako `[external]` ve výstupu zásobník volání.

 Přístup z více vláken:`n`

 Volitelné. Zobrazí zásobník volání pro přístup z více vláken `n`. Pokud není zadaný žádný přístup z více vláken, zobrazuje zásobník volání pro aktuální vlákno.

## <a name="remarks"></a>Poznámky
 Změny provedené v přepínači nebo argumenty platí pro budoucí volání tohoto příkazu. Pokud vydáte Debug.ListCallStackby sám sebe, zobrazí se celý zásobník volání. Pokud například zadáte index,

```
Debug.ListCallStack 2
```

 aktuální rámec zásobníku bude nastavena na tomto snímku (v tomto případě druhý snímek).

 Je také možné zapsat tento příkaz pomocí jeho předem definovaný alias kb. Například můžete zadat

```
kb 2
```

 nastavit aktuální rámec zásobníku na druhý rámečku.

## <a name="example"></a>Příklad

```
>Debug.CallStack /Count:4 /ShowTypes:yes
```

## <a name="see-also"></a>Viz také

- [Příkaz Zobrazit zpětný překlad](../../ide/reference/list-disassembly-command.md)
- [Příkaz Listovat vlákna](../../ide/reference/list-threads-command.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)