---
title: Paměť – příkaz seznamu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- debug.listmemory
helpviewer_keywords:
- Debug.ListMemory command
- ListMemory command
- list memory command
ms.assetid: a84de361-a6a6-4f6d-96aa-a0d4a424371e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 884dda624d5405ec017b544afd223be0bebc97e9
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59655865"
---
# <a name="list-memory-command"></a>Listovat paměť – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zobrazí obsah určeného rozsahu paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.ListMemory [/ANSI|Unicode] [/Count:number] [/Format:formattype]  
[/Hex|Signed|Unsigned] [expression]  
```  
  
## <a name="arguments"></a>Arguments  
 `expression`  
 Volitelné. Adresa paměti, ze kterého se má zahájit zobrazování paměti.  
  
## <a name="switches"></a>Přepínače  
 / ANSI&#124;kódování Unicode  
 Volitelné. Zobrazení paměti jako odpovídající počet bajtů paměti, ANSI nebo Unicode znaky.  
  
 / Počet:`number`  
 Volitelné. Určuje počet bajtů paměti k zobrazení, počínaje `expression`.  
  
 / Formát:`formattype`  
 Volitelné. Formát typu pro zobrazení informací o paměti v **paměti** okno; je pravděpodobně být OneByte TwoBytes, FourBytes, EightBytes, Float (32bitová verze) nebo dvakrát (64 bitů). Pokud použijete OneByte `/Unicode` není k dispozici.  
  
 / Hex&#124;podepsané&#124;bez znaménka  
 Volitelné. Určuje formát zobrazení čísel: jako podepsaný držitelem, bez znaménka nebo šestnáctkové.  
  
## <a name="remarks"></a>Poznámky  
 Místo psaní si kompletní **Debug.listmemory –** příkazu se všechny přepínače, můžete vyvolat příkaz předdefinované aliasy using s určitým přepínači přednastaveny tak, aby zadané hodnoty. Například místo zadávání:  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
 můžete psát:  
  
```  
>df /Count:30 /Unicode  
```  
  
 Tady je seznam dostupné aliasy pro **Debug.listmemory –** příkaz:  
  
|Alias|Příkaz a přepínače|  
|-----------|--------------------------|  
|**d**|Debug.listmemory –|  
|**da**|Debug.listmemory – /Ansi|  
|**db**|Debug.listmemory – /Format:OneByte|  
|**dc**|Debug.listmemory – /Format:FourBytes /Ansi|  
|**dd**|Debug.listmemory – /Format:FourBytes|  
|**df**|Debug.listmemory – /Format:Float|  
|**dq**|Debug.listmemory – /Format:EightBytes|  
|**du**|Debug.listmemory – Unicode|  
  
## <a name="example"></a>Příklad  
  
```  
>Debug.ListMemory /Format:float /Count:30 /Unicode  
```  
  
## <a name="see-also"></a>Viz také  
 [Příkaz listovat zásobník volání](../../ide/reference/list-call-stack-command.md)   
 [Listovat vlákna – příkaz](../../ide/reference/list-threads-command.md)   
 [Visual Studio Commands](../../ide/reference/visual-studio-commands.md)   
 [Okno příkazového řádku](../../ide/reference/command-window.md)   
 [Pole najít/příkaz](../../ide/find-command-box.md)   
 [Aliasy příkazů sady Visual Studio](../../ide/reference/visual-studio-command-aliases.md)
