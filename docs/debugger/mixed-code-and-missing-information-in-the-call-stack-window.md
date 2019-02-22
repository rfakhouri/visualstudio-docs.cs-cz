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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 025591ffea4d6746f87e5f1240cd226fa291d116
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703666"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Smíšený kód a chybějící informace v okně Zásobník volání
Kvůli rozdílům mezi zásobníky volání pro spravovaný a nativní kód nelze ladicí program vždy zobrazit úplný zásobník volání, když kód kombinace. Když nativní kód volá spravovaný kód, můžete si všimnout následující rozdíly v **zásobník volání** okno:

- Nativní rámce přímo nad spravovaného kódu můžou chybět **zásobník volání** okna. Další informace najdete v tématu [jak: Vystoupení ze spravovaného kódu, pokud v okně zásobník volání chybějí nativní rámce](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).

- Pro aplikace ve smíšeném režimu spustí mimo ladicí program **zásobník volání** okně může zobrazit pouze spravovaný kód a žádný z nativní rámce se nebude zobrazovat.

  Obě jsou velmi malý. Zásobníky volání v nejvíce nativní volání spravovaného kódu, zobrazovat správně.

## <a name="see-also"></a>Viz také
- [Postupy: Použití okna Zásobník volání](../debugger/how-to-use-the-call-stack-window.md)