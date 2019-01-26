---
title: otevřít projekt – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- file.openproject
- file.opensolution
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14ca6ed2f9a3e21d641f9d5dbe83234066886164
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55010165"
---
# <a name="open-project-command"></a>Otevřít projekt – příkaz

Otevře existující projekt nebo řešení.

## <a name="syntax"></a>Syntaxe

```cmd
File.OpenProject filename
```

## <a name="arguments"></a>Arguments

`filename`

Povinný parametr. Úplnou cestu a název souboru název projektu nebo řešení mohlo být otevřeno.

> [!NOTE]
> Syntaxe `filename` argument vyžaduje, aby cesty, které obsahují mezery, použijte uvozovky.

## <a name="remarks"></a>Poznámky

Automatické dokončování, pokusí se najít správnou cestu a název souboru během psaní.

Tento příkaz není k dispozici při ladění.

## <a name="example"></a>Příklad

Následující příklad otevře projekt jazyka Visual Basic **Test1**:

```cmd
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"
```

## <a name="see-also"></a>Viz také:

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Okno příkazového řádku](../../ide/reference/command-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Visual Studio aliasy příkazů](../../ide/reference/visual-studio-command-aliases.md)