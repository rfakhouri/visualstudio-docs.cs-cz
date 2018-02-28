---
title: "Seznam zdroj – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Debug.ListSource
helpviewer_keywords:
- Debug.ListSource command
- list source command
- ListSource command
ms.assetid: e45f08d2-f4a3-49c3-9452-aa60508e2f74
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: bb3f3e6cb441697fb8546fcec485d292e979690b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="list-source-command"></a>Listovat zdroj – příkaz
Zobrazí zadané řádků zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListSource [/Count:number] [/Current] [/File:filename]  
[/Line:number] [/ShowLineNumbers:yes|no]  
```  
  
## <a name="switches"></a>Přepínače  
 / Počet:`number`  
 Volitelné. Určuje počet řádků určených k zobrazení.  
  
 / Aktuální  
 Volitelné. Zobrazuje aktuálního řádku.  
  
 Nebo souborů:`filename`  
 Volitelné. Cesta souboru, který se zobrazí. Pokud není zadaný žádný název souboru, příkaz zobrazí zdrojový kód pro řádek aktuální příkaz.  
  
 / Řádku:`number`  
 Volitelné. Zobrazuje číslo konkrétní řádku.  
  
 / ShowLineNumbers:`yes|no`  
 Volitelné. Určuje, jestli se mají zobrazovat čísla řádků.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Tento příklad uvádí zdrojového kódu z řádku 4 souboru Form1.vb, s čísla řádků, které jsou viditelné.  
  
```  
Debug.ListSource /File:"C:\Visual Studio Projects\Form1.vb" /Line:4 /ShowLineNumbers:yes  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)