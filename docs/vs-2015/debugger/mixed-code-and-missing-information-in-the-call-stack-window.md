---
title: Smíšený kód a chybějící informace v okně zásobník volání | Dokumentace Microsoftu
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
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c91b2e49dc94057ab7929380ad1b819cd01731d6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675417"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Smíšený kód a chybějící informace v okně Zásobník volání
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [smíšený kód a chybějící informace v okně zásobník volání](https://docs.microsoft.com/visualstudio/debugger/mixed-code-and-missing-information-in-the-call-stack-window).  
  
Kvůli rozdílům mezi zásobníky volání pro spravovaný a nativní kód nelze ladicí program vždy zobrazit úplný zásobník volání, když kód kombinace. Když nativní kód volá spravovaný kód, můžete si všimnout následující rozdíly v **zásobník volání** okno:  
  
-   Nativní rámce přímo nad spravovaného kódu můžou chybět **zásobník volání** okna. Další informace najdete v tématu [postupy: vystoupení ze spravovaného kódu, pokud v okně zásobník volání chybějí nativní rámce](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).  
  
-   Pro aplikace ve smíšeném režimu spustí mimo ladicí program **zásobník volání** okně může zobrazit pouze spravovaný kód a žádný z nativní rámce se nebude zobrazovat.  
  
 Obě jsou velmi malý. Zásobníky volání v nejvíce nativní volání spravovaného kódu, zobrazovat správně.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md)





