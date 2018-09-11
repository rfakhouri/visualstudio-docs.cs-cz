---
title: Jak mohu ladit funkce rozhraní API systému Windows? | Dokumenty Microsoft
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
ms.openlocfilehash: 7cc765c6da62973469280e97759fbab566ca6f37
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281673"
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
