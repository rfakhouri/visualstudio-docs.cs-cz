---
title: "Pokračování provádění po výjimce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
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
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 84ade967c00e33390402e16a1b2980277f89ed5a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="continuing-execution-after-an-exception"></a>Pokračování v provádění po výjimce
Pokud ladicí program dělí provádění z důvodu výjimku, zobrazí se **pomocníka výjimka**, ve výchozím nastavení. Pokud je zakázána **pomocníka výjimka** v **možnosti** dialogové okno, zobrazí se **Pomocníka pro výjimky** (C# nebo Visual Basic) nebo **výjimky**  dialogové okno (C++).  
  
 Když **pomocníka výjimka** se zobrazí, můžete se pokusit opravit problém, který způsobil výjimku.
  
## <a name="managed-and-native-code"></a>Spravovaná a nativní kód  
 Spravovaná a nativní kód můžou pokračovat ve stejném vlákně, v provádění po k neošetřené výjimce. **Pomocníka výjimka** unwinds zásobníku volání do bodu, kde byla výjimka vydána.
  
## <a name="mixed-code"></a>Smíšený kód  
 Jestli jste nedosáhli neošetřenou výjimku při ladění smíšený nativního a spravovaného kódu, omezení operačního systému zakázat unwinding zásobníku volání. Pokud se pokusíte převíjení zásobníku volání pomocí místní nabídky, chybovou zprávu vysvětluje, že ladicí program nemůže unwind z neošetřenou výjimkou ladění ve smíšeném kódu.  
  
## <a name="see-also"></a>Viz také  
 [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)