---
title: Otevřít řešení – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.opensolution
helpviewer_keywords:
- Open Solution command
- File.OpenSolution command
ms.assetid: 61de76c8-69d7-4cdb-b605-e132f45d05d9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 652305e6d5d360169645e7801e788b39b8982400
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="open-solution-command"></a>Otevřít řešení – příkaz
Otevře se do stávajícího řešení zavřít všechny otevřené řešení.

## <a name="syntax"></a>Syntaxe

```
File.OpenSolution filename
```

## <a name="arguments"></a>Arguments
 `Filename`

 Požadováno. Úplné a cesta k souboru název řešení otevřete.

 Syntaxe `filename` argument vyžaduje, aby cesty obsahující mezery, použijte uvozovky.

## <a name="remarks"></a>Poznámky
 Automatické doplňování, pokusí se najít správnou cestu a název souboru při psaní.

## <a name="example"></a>Příklad
 Tento příklad otevře řešení, Test1.sln.

```
>File.OpenSolution "c:\MySolutions\Test1\Test1.sln"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)