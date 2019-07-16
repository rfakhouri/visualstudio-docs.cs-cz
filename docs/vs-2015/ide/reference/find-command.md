---
title: Najít – příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- edit.find
helpviewer_keywords:
- Find command
- Edit.Find command
ms.assetid: f0c705dc-2b97-423d-abbf-5584d4827208
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ee744a8ab3a22d640f3d48e7291b546f36415d24
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199307"
---
# <a name="find-command"></a>Najít – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Hledá v souborech pomocí některé podsady z možností, které jsou k dispozici na **najít v souborech** karty **najít a nahradit** okna.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Edit.Find findwhat [/case] [/doc | /proc | /open | /sel]   
[/markall] [/options] [/reset] [/up] [/wild | /regex] [/word]  
```  
  
## <a name="arguments"></a>Arguments  
 `findwhat`  
 Povinný parametr. Text tak, aby odpovídaly.  
  
## <a name="switches"></a>Přepínače  
 /Case nebo /c  
 Volitelné. Odpovídá dojde pouze v případě, že velká a malá písmena přesně odpovídá platformám zadaným v `findwhat` argument.  
  
 / DOC nebo /d  
 Volitelné. Vyhledá aktuálním dokumentu. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 /markall nebo /m  
 Volitelné. Umístí obrázek na každém řádku, který obsahuje shodu hledání v rámci aktuálního dokumentu.  
  
 /Open nebo /o  
 Volitelné. Vyhledá všechny otevřené dokumenty, jako by byly jeden dokument. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 / Options nebo /t  
 Volitelné. Zobrazí seznam aktuální nastavení možnosti hledání a nebude provádět vyhledávání.  
  
 /proc nebo /p  
 Volitelné. Hledá aktuální proceduře. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 / Reset nebo /e  
 Volitelné. Vrátí možnosti hledání na jejich výchozí nastavení a nebude provádět vyhledávání.  
  
 /sel nebo /s  
 Volitelné. Vyhledá pouze aktuální výběr. Zadat pouze jeden z oborů dostupných hledání `/doc`, `/proc`, `/open`, nebo `/sel`.  
  
 /Up nebo /u  
 Volitelné. Vyhledávání z aktuálního umístění v souboru směrem k začátku souboru. Ve výchozím nastavení začne hledání na aktuální pozici v souboru a hledání na konci souboru.  
  
 /Regex nebo/r  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy, které představují vzorů textu spíše než literálními znaky. Úplný seznam znaky regulárního výrazu, naleznete v tématu [regulární výrazy](../../ide/using-regular-expressions-in-visual-studio.md).  
  
 /Wild nebo/l  
 Volitelné. Používá předdefinované speciální znaky v `findwhat` argument jako zápisy představující znak nebo posloupnost znaků.  
  
 lze nebo /w  
 Volitelné. Vyhledá pouze celá slova.  
  
## <a name="example"></a>Příklad  
 Tento příklad vyhledá velká a malá písmena pro slovo "somestring" v aktuálně vybrané části kódu.  
  
```  
>Edit.Find somestring /sel /case  
```  
  
## <a name="see-also"></a>Viz také  
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
