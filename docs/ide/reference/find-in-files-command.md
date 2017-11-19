---
title: "Najít v souborech – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: edit.findinfiles
helpviewer_keywords:
- Edit.FindInFiles command
- find in files command
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bc4b1d49b80dd449201db003b3a4ad6e54a18a1f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="find-in-files-command"></a>Najít v souborech – příkaz
Hledání souborů pomocí podmnožinu dostupných na možnostech **hledání v souborech** kartě **najít a nahradit** okno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.FindinFiles findwhat [/case] [/ext:extensions]  
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]  
[/text2] [/wild|/regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Požadováno. Text tak, aby odpovídaly.  
  
## <a name="switches"></a>Přepínače  
 /Case nebo /c  
 Volitelné. Odpovídá dojít pouze v případě, že velká a malá písmena přesně shodovat s uvedenými v `findwhat` argument.  
  
 /ext:`extensions`  
 Volitelné. Určuje příponám souborů pro soubory, které chcete vyhledávat. Pokud není zadaný, předchozí rozšíření se používá, pokud jeden jste dřív zadali.  
  
 /lookin:`searchpath`  
 Volitelné. Adresář pro vyhledávání. Pokud cesta obsahuje mezery, uzavřete celý cesty do uvozovek.  
  
 /Names nebo/n  
 Volitelné. Zobrazí seznam názvů souborů, které obsahují položky.  
  
 / Options nebo/t.  
 Volitelné. Zobrazí seznam aktuální nastavení možnosti Najít a nebude provádět vyhledávání.  
  
 /Regex nebo /r  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzory text místo literálové znaky. Úplný seznam regulárního výrazu znaky, najdete v části [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 / Reset nebo /e  
 Volitelné. Vrátí možnosti Najít obnoveno výchozí nastavení a nebude provádět vyhledávání.  
  
 / stop  
 Volitelné. Aktuální operace vyhledávání zastaví, pokud je v průběhu. Hledání ignoruje všechny další argumenty při `/stop` byla zadána. K zastavení aktuální vyhledávání. například by zadejte následující operace:  
  
```  
>Edit.FindinFiles /stop  
```  
  
 / Sub nebo /s  
 Volitelné. Vyhledá podsložky v adresáři zadaném v /lookin:`searchpath` argument.  
  
 /Text2 nebo /2  
 Volitelné. Zobrazí výsledky hledání v okně Najít 2 výsledky.  
  
 /Wild nebo/l  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.  
  
 lze nebo /w  
 Volitelné. Vyhledá jenom celá slova.  
  
## <a name="example"></a>Příklad  
 Tento příklad hledá btnCancel v všechny .cls soubory umístěné ve složce "Moje projektů sady Visual Studio" a zobrazí informace shoda v okně Najít 2 výsledky.  
  
```  
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2  
```  
  
## <a name="see-also"></a>Viz také  
 [Hledání v souborech](../../ide/find-in-files.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)