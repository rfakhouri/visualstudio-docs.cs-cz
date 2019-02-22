---
title: Pokračování v provádění po výjimce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d557fc0ec056cac22603338f95920e5c721f67dd
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56637279"
---
# <a name="continuing-execution-after-an-exception"></a>Pokračování v provádění po výjimce
Pokud ladicí program přeruší provádění z důvodu výjimky, zobrazí se **pomocníka výjimky**, ve výchozím nastavení. Pokud jste zakázali **pomocníka výjimky** v **možnosti** dialogovém okně se zobrazí **Pomocníka pro výjimky** (C# nebo Visual Basic) nebo  **Výjimka** dialogové okno (C++).

 Když **pomocníka výjimky** se zobrazí, můžete se pokusit opravit problém, který způsobil výjimku.

## <a name="managed-and-native-code"></a>Spravovaný a nativní kód
 V spravovaného a nativního kódu můžete pokračovat v provádění ve stejném vlákně po neošetřené výjimce. **Pomocníka výjimky** unwinds zásobník volání do bodu, kde byla výjimka vydána.

## <a name="mixed-code"></a>Smíšený kód
 Pokud dosáhnete neošetřenou výjimku při ladění smíšená nativní a spravované kódové, omezení operačního systému zakázat odvíjení zásobníku volání. Pokud se pokusíte zpět zásobník volání pomocí místní nabídky, chybová zpráva vysvětluje, že ladicí program nelze vrátit zpět z neošetřenou výjimkou během ladění Smíšeného kódu.

## <a name="see-also"></a>Viz také

- [Správa výjimek pomocí ladicího programu](../debugger/managing-exceptions-with-the-debugger.md)