---
title: "Přidání nové položky příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: project.addnewitem
helpviewer_keywords:
- Add New Item command
- File.AddNewItem command
ms.assetid: 63b7df32-db83-463b-bbe7-7ff011fe5298
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ef0373d148d386d0b725d74ea639f1b8b0719cc3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="add-new-item-command"></a>Přidat novou položku – příkaz
Přidá novou položku řešení, například .htm, .css, txt nebo rámců k aktuálnímu řešení a otevře ji.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.AddNewItem [filename] [/t:templatename] [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Volitelné. Název a cesta k souboru položka k přidání do řešení.  
  
## <a name="switches"></a>Přepínače  
 / t:`templatename`  
 Volitelné. Určuje typ souboru, který se má vytvořit. Pokud je zadán žádný název šablony, je ve výchozím nastavení vytvořen textový soubor.  
  
 / T:`templatename` syntaxí argumentů zrcadlí informace nalezené v **přidat novou položku řešení** dialogové okno. Je nutné zadat úplný kategorie následovaný typem souboru, oddělení název kategorie z typu souboru zpětným lomítkem (`\`) a uzavření celý řetězec v uvozovkách.  
  
 Chcete-li vytvořit nový textový soubor, by například zadejte následující pro / t:`templatename` argument.  
  
```  
/t:"General\Style Sheet"  
```  
  
 / e:`editorname`  
 Volitelné. Název editoru, ve kterém bude soubor otevřít. Pokud je argument zadaný ale zadaný žádný název editoru, **otevřít v** zobrazí se dialogové okno.  
  
 / E:`editorname` syntaxí argumentů používá názvy editor, jak se zobrazují v **otevřete se dialogové okno**, uzavřené v uvozovkách.  
  
 Chcete-li otevřít šablony stylů v editoru zdrojového kódu, by například zadejte následující pro / e:`editorname` argument.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad přidá novou položku řešení, MyHTMLpg, k aktuálnímu řešení.  
  
```  
>File.AddNewItem MyHTMLpg /t:"General\HTML Page"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)