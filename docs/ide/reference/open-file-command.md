---
title: Otevřít soubor – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b5ade09e52db37b64f2bbd36af6f7f9dd67f3c89
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53902627"
---
# <a name="open-file-command"></a>Příkaz pro otevření souboru

Otevře existující soubor a umožňuje určit editor.

## <a name="syntax"></a>Syntaxe

```cmd
File.OpenFile filename [/e:editorname]
```

## <a name="arguments"></a>Arguments

`filename`

Povinný parametr. Celý nebo jeho část cestu a název soubor otevřete. Cesty obsahující mezery, musí být uzavřen v uvozovkách.

## <a name="switches"></a>Přepínače

/ e:`editorname`

Volitelné. Název editoru, ve kterém chcete soubor otevřít. Pokud je zadán argument, ale žádný editor název je zadán, **otevřít v** zobrazí se dialogové okno.

/ E:`editorname` argument syntaxe používá názvy editoru, jak se objeví v dialogovém okně Otevřít s, do uvozovek.

Například by pro otevření souboru v editoru zdrojového kódu, zadejte následující pro / e:`editorname` argument.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Poznámky

Co zadáte cestu, automatické dokončování pokusí se najít správnou cestu a název souboru.

## <a name="example"></a>Příklad

Tento příklad otevře soubor style "Test1.css" v editoru zdrojového kódu.

```cmd
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Viz také:

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Okno příkazového řádku](../../ide/reference/command-window.md)
- [Příkazové podokno](../../ide/reference/immediate-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Visual Studio aliasy příkazů](../../ide/reference/visual-studio-command-aliases.md)