---
title: Nový soubor – příkaz | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- file.newfile
helpviewer_keywords:
- File.NewFile command
- New File command
ms.assetid: 767868d6-a525-425b-a43b-2198f636ab6b
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0e925cee55f0e2c79a02a208a5d792339e6fd86e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672560"
---
# <a name="new-file-command"></a>Nový soubor – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [nový soubor – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/new-file-command).  
  
  
Vytvoří nový soubor a otevře jej. Soubor se zobrazí ve složce ostatní soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.NewFile [filename] [/t:templatename] [/editor:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Volitelné. Název souboru. Pokud je zadaný žádný název, výchozí název zadán. Pokud je uvedený žádný název šablony, se vytvoří textový soubor.  
  
## <a name="switches"></a>Přepínače  
 t:`templatename`  
 Volitelné. Určuje typ souboru, který se má vytvořit.  
  
 T:`templatename` argument syntaxe odráží informace nacházející se v dialogovém okně Nový soubor. Zadejte název kategorie, za nímž následuje zpětné lomítko (`\`) a šablony, zadejte název a uzavřete celý řetězec v uvozovkách.  
  
 Například vytvořte novou [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] zdrojového souboru, zadali byste následující t:`templatename` argument.  
  
```  
/t:"Visual C++\C++ File (.cpp)"  
```  
  
 Výše uvedený příklad určuje, že soubor C++ šablona se nachází v kategorii Visual C++ v **nový soubor** dialogové okno.  
  
 / e:`editorname`  
 Volitelné. Název editoru, ve kterém chcete soubor otevřít. Pokud je zadán argument, ale žádný editor název je zadán, **otevřít v** zobrazí se dialogové okno.  
  
 / E:`editorname` argument syntaxe používá názvy editoru, jak se objeví v dialogovém okně Otevřít s, do uvozovek.  
  
 Například by pro otevření souboru v editoru zdrojového kódu, zadejte následující pro / e:`editorname` argument.  
  
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
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Příkazové podokno](../../ide/reference/immediate-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)



