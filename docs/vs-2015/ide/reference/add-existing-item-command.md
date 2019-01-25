---
title: Příkaz Přidat existující položku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- project.addexistingitem
helpviewer_keywords:
- File.AddExistingItem command
- Add Existing Item command
ms.assetid: 41f56131-d4c7-4f81-83b7-bdac713ea870
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7686c4db4984188a4f8c4a52343f1386e9edd909
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797834"
---
# <a name="add-existing-item-command"></a>Přidat existující položku – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
Přidá existující soubor do aktuálního řešení a otevře jej.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
File.AddExistingItem filename [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Povinný parametr. Úplná cesta a název souboru, s rozšířením položky pro přidání do aktuálního řešení. Pokud cesta k souboru nebo název souboru obsahuje mezery, uzavřete do uvozovek celou cestu.  
  
## <a name="switches"></a>Přepínače  
 /e: `editorname`  
 Volitelné. Název editoru, ve kterém chcete soubor otevřít. Pokud je zadán argument, ale žádný editor název je zadán, **otevřít v** zobrazí se dialogové okno.  
  
 / E:`editorname` syntaxí argumentů používá názvy editoru, jak se objeví v **otevřít s dialogové okno**, uzavřené v uvozovkách. Chcete-li otevřít šablony stylů v editoru zdrojového kódu, by například zadejte následující pro / e:`editorname` argument.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Poznámky  
 Automatického doplňování pokusí se najít správnou cestu a název souboru během psaní.  
  
## <a name="example"></a>Příklad  
 Tento příklad přidá soubor Form1.frm, do aktuálního řešení.  
  
```  
>File.AddExistingItem "C:\public\solution files\Form1.frm"  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
