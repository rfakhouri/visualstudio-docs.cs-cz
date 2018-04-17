---
title: Nahradit v souborech – příkaz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- edit.replaceinfiles
helpviewer_keywords:
- Edit.ReplaceInFiles command
- Replace In Files command
- ReplaceInFiles command
ms.assetid: f116066a-4f65-4f2c-94ef-12cbd8cfb598
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fcf12ba2c439e9ecb77aeecf47e7fe4fc535b4aa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="replace-in-files-command"></a>Nahradit v souborech – příkaz
Nahradí text v souborech pomocí podmnožinu dostupných v možnostech **nahradit v souborech** kartě **najít a nahradit** okno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.ReplaceinFiles findwhat replacewith [/all] [/case]  
[/ext:extensions] [/keep] [/lookin:searchpath] [/options] [/regex]  
[/reset] [/stop] [/sub] [/text2] [/wild] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Požadováno. Text tak, aby odpovídaly.  
  
 `replacewith`  
 Požadováno. Text nahrazen odpovídající text.  
  
## <a name="switches"></a>Přepínače  
 / all nebo /  
 Volitelné. Nahradí všechny výskyty hledaný text Nahrazovací text.  
  
 /Case nebo /c  
 Volitelné. Odpovídá dojít pouze v případě, kdy velká a malá písmena přesně shodovat platformám zadaným v `findwhat` argument.  
  
 /ext: `extensions`  
 Volitelné. Určuje příponám souborů pro soubory, které chcete vyhledávat.  
  
 /Keep nebo /k  
 Volitelné. Určuje, že všechny změněné soubory jsou ponechány otevřené.  
  
 /lookin: `searchpath`  
 Volitelné. Adresář pro vyhledávání. Pokud cesta obsahuje mezery, uzavřete celý cesty do uvozovek.  
  
 / Options nebo/t.  
 Volitelné. Zobrazí seznam aktuální nastavení možnosti Najít a nebude provádět vyhledávání.  
  
 /Regex nebo /r  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzory text místo literálové znaky. Úplný seznam regulárního výrazu znaky, najdete v části [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 / Reset nebo /e  
 Volitelné. Vrátí možnosti Najít obnoveno výchozí nastavení a nebude provádět vyhledávání.  
  
 / stop  
 Volitelné. Aktuální operace vyhledávání zastaví, pokud je v průběhu. Nahraďte ignoruje všechny další argumenty při `/stop` byla zadána. Třeba zastavit aktuální nahrazení by zadáte následující:  
  
```  
>Edit.ReplaceinFiles /stop  
```  
  
 / Sub nebo /s  
 Volitelné. Vyhledá podsložky v adresáři zadaném v /lookin:`searchpath` argument.  
  
 /Text2 nebo /2  
 Volitelné. Zobrazí výsledky náhrada v **najít 2 výsledky** okno.  
  
 /Wild nebo/l  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.  
  
 lze nebo /w  
 Volitelné. Vyhledá jenom celá slova.  
  
## <a name="example"></a>Příklad  
 Tento příklad hledá `btnCancel` a nahradí ji s `btnReset` v .cls všechny soubory umístěné ve složce "Moje projektů sady visual studio" a zobrazí informace o nahrazení v **najít 2 výsledky** okno.  
  
```  
>Edit.ReplaceinFiles btnCancel btnReset /lookin:"c:/my visual studio projects" /ext:.cls /text2  
```  
  
## <a name="see-also"></a>Viz také  
 [Hledání a nahrazení textu](../../ide/finding-and-replacing-text.md)   
 [Nahradit v souborech](../../ide/replace-in-files.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)