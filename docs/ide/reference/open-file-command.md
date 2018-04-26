---
title: Otevřít soubor – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
ms.openlocfilehash: fd75d32021f2dd3f6ac1ef76772ea30376ea1b8a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="open-file-command"></a>Otevřít soubor – příkaz
Otevře existující soubor a umožňuje vám určit editoru.

## <a name="syntax"></a>Syntaxe

```
File.OpenFile filename [/e:editorname]
```

## <a name="arguments"></a>Arguments
 `filename`

 Požadováno. Úplné nebo částečné cestu a název soubor otevřete. Cesty obsahujících mezery musí být uzavřena v uvozovkách.

## <a name="switches"></a>Přepínače
 / e:`editorname`

 Volitelné. Název editoru, ve kterém bude soubor otevřít. Pokud je argument zadaný ale zadaný žádný název editoru, **otevřít v** zobrazí se dialogové okno.

 / E:`editorname` argument syntaxe používá názvy editor, jak se zobrazují v dialogovém okně Otevřít s, uzavřena v uvozovkách.

 Například by k otevření souboru v editoru zdrojového kódu, zadejte následující pro / e:`editorname` argument.

```
/e:"Source Code (text) Editor"
```

## <a name="remarks"></a>Poznámky
 Při zadávání cestu automatické doplňování pokusí se najít správnou cestu a název souboru.

## <a name="example"></a>Příklad
 Tento příklad otevře soubor styl "Test1.css" v editoru zdrojového kódu.

```
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Příkazové podokno](../../ide/reference/immediate-window.md)
- [Pole najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)