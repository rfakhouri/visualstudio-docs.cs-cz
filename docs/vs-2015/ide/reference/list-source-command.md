---
title: Příkaz zdroj seznamu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
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
manager: jillfra
ms.openlocfilehash: e0a4a8482dc1c2c66a45902f2f3382b179b46b13
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59662839"
---
# <a name="list-source-command"></a>Listovat zdroj – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
  
 /ShowLineNumbers:`yes|no`  
 Volitelné. Určuje, jestli se mají zobrazovat čísla řádků.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V tomto příkladu obsahuje zdrojový kód z řádek 4 souboru Form1.vb, s čísly řádků viditelná.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)
