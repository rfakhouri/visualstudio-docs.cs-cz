---
title: Přidat novou položku – příkaz
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6a73bd7008e0058fe984fcb708c92c2bd983d427
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919369"
---
# <a name="add-new-item-command"></a>Přidat novou položku – příkaz
Přidá novou položku řešení, jako je například htm, CSS, txt nebo sada rámců do aktuálního řešení a otevře jej.

## <a name="syntax"></a>Syntaxe

```cmd
File.AddNewItem [filename] [/t:templatename] [/e:editorname]
```

## <a name="arguments"></a>Arguments
`filename`\
Volitelné. Cesta a název souboru položky, která se má přidat do řešení

## <a name="switches"></a>Přepínače
parametr`templatename`\
Volitelné. Určuje typ souboru, který se má vytvořit. Pokud není zadán žádný název šablony, je ve výchozím nastavení vytvořen textový soubor.

Syntaxe/t:`templatename` argument odráží informace, které se nacházejí v dialogovém okně **Přidat novou položku řešení** . Je nutné zadat celou kategorii, za kterou následuje typ souboru, oddělení názvu kategorie od typu souboru zpětným lomítkem (`\`) a uzavřením celého řetězce v uvozovkách.

Pokud například chcete vytvořit nový textový soubor, zadejte do argumentu/t:`templatename` následující text.

```cmd
/t:"General\Style Sheet"
```

/e`editorname`\
Volitelné. Název editoru, ve kterém bude soubor otevřen. Je-li zadán argument, ale není zadán žádný název editoru, zobrazí se dialogové okno **otevřít v** .

Syntaxe/e:`editorname` argument používá názvy editoru tak, jak se zobrazí v **dialogovém okně Otevřít v aplikaci**uzavřené v uvozovkách.

Chcete-li například otevřít šablonu stylů v editoru zdrojového kódu, zadejte následující příkaz pro parametr/e:`editorname` .

```cmd
/e:"Source Code (text) Editor"
```

## <a name="example"></a>Příklad
Tento příklad přidá novou položku řešení MyHTMLpg do aktuálního řešení.

```cmd
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"
```

## <a name="see-also"></a>Viz také

- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
- [Příkazové okno](../../ide/reference/command-window.md)
- [Pole Najít/příkaz](../../ide/find-command-box.md)
- [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)