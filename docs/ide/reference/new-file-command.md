---
title: "Nový soubor – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ad7f0232a4e08c134a7dffcc3d10a2180e235717
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="new-file-command"></a>Nový soubor – příkaz
Vytvoří nový soubor a otevře ji. Soubor se zobrazí ve složce různé soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.NewFile [filename] [/t:templatename] [/editor:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Volitelné. Název souboru. Pokud je zadaný název je zadaný výchozí název. Pokud je uvedený název žádné šablony, se vytvoří textový soubor.  
  
## <a name="switches"></a>Přepínače  
 / t:`templatename`  
 Volitelné. Určuje typ souboru, který se má vytvořit.  
  
 / T:`templatename` argument syntaxe zrcadlí informace nalezené v dialogovém okně Nový soubor. Zadejte název kategorie, za nímž následuje zpětné lomítko (`\`) a šablonu název a uzavřete celý řetězec v uvozovkách.  
  
 Chcete-li například vytvořit nový [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] zdrojový soubor, zadali byste následující pro / t:`templatename` argument.  
  
```  
/t:"Visual C++\C++ File (.cpp)"  
```  
  
 V předchozím příkladu označuje, že šablona souboru C++ je umístěn v kategorii Visual C++ v **nový soubor** dialogové okno.  
  
 / e:`editorname`  
 Volitelné. Název editoru, ve kterém bude soubor otevřít. Pokud je argument zadaný ale zadaný žádný název editoru, **otevřít v** zobrazí se dialogové okno.  
  
 / E:`editorname` argument syntaxe používá názvy editor, jak se zobrazují v dialogovém okně Otevřít s, uzavřena v uvozovkách.  
  
 Například by k otevření souboru v editoru zdrojového kódu, zadejte následující pro / e:`editorname` argument.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="example"></a>Příklad  
 Tento příklad vytvoří novou webovou stránku "test1.htm" a otevře v editoru zdrojového kódu.  
  
```  
>File.NewFile test1 /t:"General\HTML Page" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Příkazové podokno](../../ide/reference/immediate-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)