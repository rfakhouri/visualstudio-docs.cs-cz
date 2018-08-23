---
title: Pokračování v provádění po výjimce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a71d71622809dfaeea399355e490fe4e69b52b9f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670791"
---
# <a name="continuing-execution-after-an-exception"></a>Pokračování v provádění po výjimce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [pokračování provádění po výjimce](https://docs.microsoft.com/visualstudio/debugger/continuing-execution-after-an-exception).  
  
Pokud ladicí program přeruší provádění z důvodu výjimky, zobrazí se dialogové okno. Visual Basic nebo C#, zobrazí se [pomocníka pro výjimky](http://msdn.microsoft.com/library/992892ac-9d52-44cc-bf09-b44bfc5befeb) dialogové okno, ve výchozím nastavení. Pro jazyk C++, zobrazí se starší **výjimka** dialogové okno. Pokud používáte Visual Basic nebo C#, ale jste zakázali **pomocníka pro výjimky** v **možnosti** dialogovém okně se zobrazí **výjimka** dialogové okno.  
  
 Když **pomocníka pro výjimky** nebo **výjimka** se zobrazí dialogové okno, můžete se pokusit opravit problém, který způsobil výjimku.  
  
## <a name="managed-code"></a>Spravovaný kód  
 Ve spravovaném kódu můžete pokračovat v provádění ve stejném vlákně po neošetřené výjimce. **Pomocníka pro výjimky** unwinds zásobník volání do bodu, kde byla výjimka vydána.  
  
## <a name="native-code"></a>Nativní kód  
 V nativním C/C++ máte dvě možnosti:  
  
-   Můžete kliknout na **přerušit** a pokuste se tento problém vyřešit. Při práci v režimu přerušení, lze vrátit zásobník volání kliknutím pravým tlačítkem na snímek v **zásobník volání** okno a vyberete **Unwind k tomuto rámci** v místní nabídce. Když budete pokračovat v ladění, **výjimka** dialogové okno zobrazí znovu, pokud jste problém. V opačném případě **výjimka** neobjeví dialogové okno.  
  
-   Můžete kliknout na **pokračovat** pro pokračování v provádění bez pokusu o vyřešení problému. **Výjimka** se znovu zobrazí dialogové okno.  
  
## <a name="mixed-code"></a>Smíšený kód  
 Pokud dosáhnete neošetřenou výjimku při ladění smíšená nativní a spravované kódové, omezení operačního systému zakázat odvíjení zásobníku volání. Pokud se pokusíte zpět zásobník volání pomocí místní nabídky, chybová zpráva vysvětluje, že ladicí program nelze vrátit zpět z neošetřenou výjimkou během ladění Smíšeného kódu.  
  
## <a name="see-also"></a>Viz také  
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)





