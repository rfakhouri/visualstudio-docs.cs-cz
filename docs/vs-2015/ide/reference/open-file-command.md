---
title: Otevřít soubor – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e870b15355da86b8654511cab932f792323446b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199059"
---
# <a name="open-file-command"></a>Otevřít soubor – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Otevře existující soubor a umožňuje určit editor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Poznámky  
 Co zadáte cestu, automatické dokončování pokusí se najít správnou cestu a název souboru.  
  
## <a name="example"></a>Příklad  
 Tento příklad otevře soubor style "Test1.css" v editoru zdrojového kódu.  
  
```  
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Příkazové podokno](../../ide/reference/immediate-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
