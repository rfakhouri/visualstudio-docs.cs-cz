---
title: Ladit funkce rozhraní Windows API | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d10c4804d4d53c22281c11d8afc464cf2ac3732
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53861511"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Jak mohu ladit funkce rozhraní API systému Windows?
Pokud chcete ladit funkce rozhraní Windows API, která má načteny symboly NT, postupujte takto.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>Nastavení zarážky na funkci rozhraní API Windows NT symboly načteny  
  
-   Zadejte název funkce společně s názvem knihovny DLL, ve kterém se funkce nachází. V kódu, 32-bit použijte upravené podobě název funkce. Chcete-li nastavit zarážku na **MessageBeep**, musíte například zadat následující.  
  
    ```cpp
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     Chcete-li získat upravený název, přečtěte si téma [zobrazení dekorovaných názvů](https://msdn.microsoft.com/library/f79e2717-a4db-4d12-a689-69830cce2be0).  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
