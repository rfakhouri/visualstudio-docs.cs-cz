---
title: Otevřít projekt – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.openproject
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6663ef73f87ea0fa80eb16a3deef6765265882db
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="open-project-command"></a>Otevřít projekt – příkaz
Otevře existující projekt.

## <a name="syntax"></a>Syntaxe

```cmd
File.OpenProject filename
```

## <a name="arguments"></a>Arguments
 `filename`

 Požadováno. Úplné a cesta k souboru název projektu otevřete.

 Syntaxe `filename` argument vyžaduje, aby cesty obsahující mezery, použijte uvozovky.

## <a name="remarks"></a>Poznámky
 Automatické doplňování, pokusí se najít správnou cestu a název souboru při psaní.

 Tento příkaz není k dispozici při ladění.

## <a name="example"></a>Příklad
 Otevře se v tomto příkladu [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projektu, Test1.

```cmd
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)