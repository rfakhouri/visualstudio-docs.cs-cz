---
title: Přidat novou položku – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8c094e30c9491783733e49901fb297c36c1e94f9
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53952469"
---
# <a name="add-new-item-command"></a>Přidat novou položku – příkaz
Přidá novou položku řešení, jako je například htm, CSS, txt nebo sada rámců do aktuálního řešení a otevře jej.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddNewItem [filename] [/t:templatename] [/e:editorname]
```

## <a name="arguments"></a>Arguments
 `filename` Volitelné. Název a cesta k souboru položky pro přidání do řešení.

## <a name="switches"></a>Přepínače
 t: `templatename` Volitelné. Určuje typ souboru, který se má vytvořit. Pokud je zadaný žádný název šablony, se ve výchozím nastavení vytvoří textový soubor.

 T:`templatename` syntaxí argumentů odráží informace nacházející se v **přidat novou položku řešení** dialogové okno. Je nutné zadat úplnou kategorii a potom podle typu souboru, oddělení název kategorie z typ souboru je zpětným lomítkem (`\`) a vnější celý řetězec v uvozovkách.

 Například by pokud chcete vytvořit nový textový soubor, zadejte následující t:`templatename` argument.

```cmd
/t:"General\Style Sheet"
```

 / e: `editorname` Volitelné. Název editoru, ve kterém chcete soubor otevřít. Pokud je zadán argument, ale žádný editor název je zadán, **otevřít v** zobrazí se dialogové okno.

 / E:`editorname` syntaxí argumentů používá názvy editoru, jak se objeví v **otevřít s dialogové okno**, uzavřené v uvozovkách.

 Chcete-li otevřít šablony stylů v editoru zdrojového kódu, by například zadejte následující pro / e:`editorname` argument.

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Příklad
 Tento příklad přidá novou položku řešení, MyHTMLpg, do aktuálního řešení.

```cmd
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)