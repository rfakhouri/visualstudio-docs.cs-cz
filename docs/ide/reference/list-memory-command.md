---
title: "Seznam paměť – příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- debug.listmemory
helpviewer_keywords:
- Debug.ListMemory command
- ListMemory command
- list memory command
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e6780ffc846d3710b78bbfa994ca3e73d14209e0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="list-memory-command"></a>Listovat paměť – příkaz
Zobrazí obsah zadaný rozsah paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListMemory [/ANSI|Unicode] [/Count:number] [/Format:formattype]  
[/Hex|Signed|Unsigned] [expression]  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Volitelné. Adresa paměti, od kterého má začít zobrazení paměti.  
  
## <a name="switches"></a>Přepínače  
 / ANSI &#124; Kódování Unicode  
 Volitelné. Paměť se zobrazí jako znaků odpovídající počet bajtů paměti, ANSI nebo Unicode.  
  
 / Počet:`number`  
 Volitelné. Určuje počet bajtů paměti, která se zobrazí, počínaje `expression`.  
  
 / Formát:`formattype`  
 Volitelné. Typ formátu pro zobrazení informací o paměti v **paměti** okno; může být OneByte, TwoBytes, FourBytes, EightBytes, Float (32bitová verze), nebo dvakrát (64 bitů). Pokud se používá OneByte `/Unicode` není k dispozici.  
  
 /Hex &#124; Podepsané &#124; Bez znaménka  
 Volitelné. Určuje formát pro zobrazení čísla: jako podepsaný držitelem, bez znaménka nebo hexadecimální.  
  
## <a name="remarks"></a>Poznámky  
 Místo psaní se úplná **Debug.listmemory –** příkaz s všech přepínačů, můžete vyvolat příkaz pomocí předdefinované aliasy určité přepínače přednastavení na zadané hodnoty. Například místo zadávání:  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
 Můžete napsat:  
  
```  
>df /Count:30 /Unicode  
```  
  
 Tady je seznam dostupné aliasy pro **Debug.listmemory –** příkaz:  
  
|Alias|Příkaz a přepínače|  
|-----------|--------------------------|  
|**d**|Debug.listmemory –|  
|**da**|Debug.listmemory – /Ansi|  
|**DB**|Debug.listmemory – /Format:OneByte|  
|**řadič domény**|Debug.listmemory – /Format:FourBytes /Ansi|  
|**dd**|Debug.listmemory – /Format:FourBytes|  
|**DF –**|Debug.listmemory – /Format:Float|  
|**dq –**|Debug.listmemory – /Format:EightBytes|  
|**du**|Debug.listmemory – / Unicode|  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
## <a name="see-also"></a>Viz také  
 [Listovat zásobník volání – příkaz](../../ide/reference/list-call-stack-command.md)   
 [Listovat vlákna – příkaz](../../ide/reference/list-threads-command.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)   
 [Příkazové okno](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)