---
title: Příkaz zdroj seznamu | Dokumentace Microsoftu
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
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ce57d39d609268e2570d588e6863eb1e8b8d3111
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696234"
---
# <a name="list-source-command"></a>Listovat zdroj – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [listovat zdroj – příkaz](https://docs.microsoft.com/visualstudio/ide/reference/list-source-command).  
  
  
Zobrazí zadané řádky zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>Přepínače  
 / Počet:`number`  
 Volitelné. Určuje počet řádků k zobrazení.  
  
 Nebo aktuální  
 Volitelné. Zobrazí aktuální řádek.  
  
 / Souboru:`filename`  
 Volitelné. Cesta k souboru, který má zobrazit. Pokud není zadán žádný název souboru, příkaz zobrazuje zdrojový kód pro řádek aktuální příkaz.  
  
 / Řádek:`number`  
 Volitelné. Zobrazí konkrétní řádek určený číslem.  
  
 / Showlinenumberszobrazitčíslařádků:`yes|no`  
 Volitelné. Určuje, jestli se mají zobrazovat čísla řádků.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V tomto příkladu obsahuje zdrojový kód z řádek 4 souboru Form1.vb, s čísly řádků viditelná.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)



