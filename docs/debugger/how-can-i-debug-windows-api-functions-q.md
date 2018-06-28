---
title: Jak mohu ladit funkce rozhraní API systému Windows? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: 042f243c0469b8b37e301cf5c9f2410cf201f7be
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058603"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Jak mohu ladit funkce rozhraní API systému Windows?
Pokud chcete ladit funkce rozhraní API systému Windows, která má symboly NT načíst, postupujte takto.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>Chcete-li nastavit zarážky funkce rozhraní API systému Windows se symboly NT načíst  
  
-   Zadejte název funkce společně s názvem knihovny DLL, kde se funkce nachází. V kódu 32-bit formulář dekorovaný název funkce. Chcete-li nastavit zarážky **MessageBeep**, například musíte zadat následující.  
  
    ```cpp
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     Chcete-li získat upravený název, přečtěte si téma [zobrazení dekorované názvy](http://msdn.microsoft.com/en-us/f79e2717-a4db-4d12-a689-69830cce2be0).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
