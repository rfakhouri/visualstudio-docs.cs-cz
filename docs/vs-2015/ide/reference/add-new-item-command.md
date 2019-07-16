---
title: Přidat novou položku příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0ba7820bfa6df7273f170b2222d6a55e685e445e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203695"
---
# <a name="add-new-item-command"></a>Přidat novou položku – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Přidá novou položku řešení, jako je například htm, CSS, txt nebo sada rámců do aktuálního řešení a otevře jej.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.AddNewItem [filename] [/t:templatename] [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Volitelné. Název a cesta k souboru položky pro přidání do řešení.  
  
## <a name="switches"></a>Přepínače  
 /t: `templatename`  
 Volitelné. Určuje typ souboru, který se má vytvořit. Pokud je zadaný žádný název šablony, se ve výchozím nastavení vytvoří textový soubor.  
  
 T:`templatename` syntaxí argumentů odráží informace nacházející se v **přidat novou položku řešení** dialogové okno. Je nutné zadat úplnou kategorii a potom podle typu souboru, oddělení název kategorie z typ souboru je zpětným lomítkem (`\`) a vnější celý řetězec v uvozovkách.  
  
 Například by pokud chcete vytvořit nový textový soubor, zadejte následující t:`templatename` argument.  
  
```  
/t:"General\Style Sheet"  
```  
  
 /e: `editorname`  
 Volitelné. Název editoru, ve kterém chcete soubor otevřít. Pokud je zadán argument, ale žádný editor název je zadán, **otevřít v** zobrazí se dialogové okno.  
  
 / E:`editorname` syntaxí argumentů používá názvy editoru, jak se objeví v **otevřít s dialogové okno**, uzavřené v uvozovkách.  
  
 Chcete-li otevřít šablony stylů v editoru zdrojového kódu, by například zadejte následující pro / e:`editorname` argument.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad přidá novou položku řešení, MyHTMLpg, do aktuálního řešení.  
  
```  
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
