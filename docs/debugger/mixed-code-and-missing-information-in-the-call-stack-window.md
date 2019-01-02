---
title: Smíšený kód a chybějící informace v okně zásobník volání | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 184e1b9a189ced74f93eef92a79c1c7121fdba2b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53941109"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Smíšený kód a chybějící informace v okně Zásobník volání
Kvůli rozdílům mezi zásobníky volání pro spravovaný a nativní kód nelze ladicí program vždy zobrazit úplný zásobník volání, když kód kombinace. Když nativní kód volá spravovaný kód, můžete si všimnout následující rozdíly v **zásobník volání** okno:  
  
- Nativní rámce přímo nad spravovaného kódu můžou chybět **zásobník volání** okna. Další informace najdete v tématu [jak: Vystoupení ze spravovaného kódu, pokud v okně zásobník volání chybějí nativní rámce](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).  
  
- Pro aplikace ve smíšeném režimu spustí mimo ladicí program **zásobník volání** okně může zobrazit pouze spravovaný kód a žádný z nativní rámce se nebude zobrazovat.  
  
  Obě jsou velmi malý. Zásobníky volání v nejvíce nativní volání spravovaného kódu, zobrazovat správně.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Použijte okno zásobníku volání](../debugger/how-to-use-the-call-stack-window.md)