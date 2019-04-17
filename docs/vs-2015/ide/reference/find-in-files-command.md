---
title: Příkaz Najít v souborech | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- edit.findinfiles
helpviewer_keywords:
- Edit.FindInFiles command
- find in files command
ms.assetid: 2fc78bfe-b339-4599-97f9-4cafd8a194d9
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7fc580a6dc1dd8a1b0c0ad8964ade6dd6145ada2
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59662917"
---
# <a name="find-in-files-command"></a>Najít v souborech – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Hledání souborů pomocí některé podsady z možností, které jsou k dispozici na **najít v souborech** karty **najít a nahradit** okna.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.FindinFiles findwhat [/case] [/ext:extensions]  
[/lookin:searchpath] [/names] [/options] [/reset] [/stop] [/sub]  
[/text2] [/wild|/regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Povinný parametr. Text tak, aby odpovídaly.  
  
## <a name="switches"></a>Přepínače  
 /Case nebo /c  
 Volitelné. Odpovídá dojde pouze v případě, že velká a malá písmena přesně odpovídá platformám zadaným v `findwhat` argument.  
  
 /ext: `extensions`  
 Volitelné. Určuje rozšíření souboru pro soubory k prohledání. Pokud není zadán, používá předchozí rozšíření, pokud dříve bylo zadáno.  
  
 /lookin: `searchpath`  
 Volitelné. Adresář pro hledání. Pokud cesta obsahuje mezery, uzavřete do uvozovek celou cestu.  
  
 /Names nebo /n  
 Volitelné. Zobrazí seznam názvů souborů, které obsahují shody.  
  
 / Options nebo /t  
 Volitelné. Zobrazí seznam aktuální nastavení možnosti hledání a nebude provádět vyhledávání.  
  
 /Regex nebo/r  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzorů textu spíše než literálními znaky. Úplný seznam znaky regulárního výrazu, naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 / Reset nebo /e  
 Volitelné. Vrátí možnosti hledání na jejich výchozí nastavení a nebude provádět vyhledávání.  
  
 /stop  
 Volitelné. Zastaví aktuální operace vyhledávání, pokud je v průběhu. Hledání ignoruje všechny argumenty při `/stop` nebyl zadán. Například chcete-li ukončit aktuální hledání zadáte následující:  
  
```  
>Edit.FindinFiles /stop  
```  
  
 / Sub nebo /s  
 Volitelné. Vyhledá podsložky v adresáři uvedeném na /lookin:`searchpath` argument.  
  
 /Text2 nebo /2  
 Volitelné. Výsledky hledání se zobrazí v okně Najít výsledky 2.  
  
 /Wild nebo/l  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.  
  
 lze nebo /w  
 Volitelné. Vyhledá pouze celá slova.  
  
## <a name="example"></a>Příklad  
 Tento příklad vyhledá btnCancel ve všech souborech .cls umístěný ve složce "My projektů sady Visual Studio" a zobrazí informace o shodu v okně Najít výsledky 2.  
  
```  
>Edit.FindinFiles btnCancel /lookin:"c:/My Visual Studio Projects" /ext:*.cls /text2  
```  
  
## <a name="see-also"></a>Viz také  
 [Najít v souborech](../../ide/find-in-files.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
