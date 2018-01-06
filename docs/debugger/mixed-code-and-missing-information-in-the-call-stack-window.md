---
title: "Smíšený kód a chybějící informace v okně zásobník volání | Microsoft Docs"
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
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a234529f13217cabf59a8d3827427e2f5341fb53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Smíšený kód a chybějící informace v okně Zásobník volání
Z důvodu rozdíly mezi zásobníky volání pro spravovaná a nativní kód nelze ladicího programu vždy zobrazí zásobníku dokončení volání, když kód typy kombinaci. Když nativní kód zavolá spravovaného kódu, můžete si povšimnout následující nesrovnalostí v **zásobníkem volání** okno:  
  
-   Nativní rámce okamžitě výše spravovaného kódu může být chybí **zásobníkem volání** okno. Další informace najdete v tématu [postupy: vystoupení ze spravovaného kódu, pokud v okně zásobník volání chybějí nativní rámce](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).  
  
-   Pro spuštění mimo ladicí program, aplikace ve smíšeném režimu **zásobníkem volání** okno může zobrazit pouze spravovaného kódu a nebudou viditelné žádná nativní rámce.  
  
 Obou případech se poměrně jen výjimečně. Zásobníky volání v nejvíce nativní volání do spravovaného kódu, zobrazovat správně.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md)