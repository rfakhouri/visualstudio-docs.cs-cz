---
title: Najít – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a4f20be9aafaa6002ba329b7dd14c132dbfcab70
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="find-command"></a>Najít – příkaz
Vyhledá soubory pomocí podmnožinu dostupných na možnostech **hledání v souborech** kartě **najít a nahradit** okno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]   
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Požadováno. Text tak, aby odpovídaly.  
  
## <a name="switches"></a>Přepínače  
 /Case nebo /c  
 Volitelné. Odpovídá dojít pouze v případě, že velká a malá písmena přesně shodovat s uvedenými v `findwhat` argument.  
  
 / DOC nebo/d  
 Volitelné. Vyhledá aktuálním dokumentu. Zadat pouze jeden z oborů dostupných vyhledávání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 /markall nebo/m  
 Volitelné. Umístí obrázek na každý řádek, který obsahuje shoda vyhledávání v aktuálním dokumentu.  
  
 /Open nebo /o  
 Volitelné. Vyhledá všechny otevřené dokumenty, jako kdyby byly jeden dokument. Zadat pouze jeden z oborů dostupných vyhledávání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 / Options nebo/t.  
 Volitelné. Zobrazí seznam aktuální nastavení možnosti Najít a nebude provádět vyhledávání.  
  
 /proc nebo /p  
 Volitelné. Vyhledá pouze aktuální procedury. Zadat pouze jeden z oborů dostupných vyhledávání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 / Reset nebo /e  
 Volitelné. Vrátí možnosti Najít obnoveno výchozí nastavení a nebude provádět vyhledávání.  
  
 /sel nebo /s  
 Volitelné. Vyhledá pouze aktuální výběr. Zadat pouze jeden z oborů dostupných vyhledávání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 /Up nebo /u  
 Volitelné. Vyhledávání z aktuálního umístění v souboru zpět na začátek souboru. Ve výchozím nastavení začne hledání v aktuální umístění v souboru a hledání na konci souboru.  
  
 /Regex nebo /r  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzory text místo literálové znaky. Úplný seznam regulárního výrazu znaky, najdete v části [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /Wild nebo/l  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.  
  
 lze nebo /w  
 Volitelné. Vyhledá jenom celá slova.  
  
## <a name="example"></a>Příklad  
 Tento příklad provede malá a velká písmena vyhledejte slovo "somestring" v aktuálně vybraném části kódu.  
  
```  
>Edit.Find somestring /sel /case  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)