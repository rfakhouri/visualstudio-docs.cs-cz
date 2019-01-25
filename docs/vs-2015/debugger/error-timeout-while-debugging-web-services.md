---
title: 'Chyba: Během ladění webových služeb vypršel časový limit | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
- XML Web services, timeout while debugging
ms.assetid: 4b7df112-788a-4429-9a0c-4c6dac4fb609
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5745a23e70f9245d6f1cb34a6d4ccc042f64bdd3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766638"
---
# <a name="error-timeout-while-debugging-web-services"></a>Chyba: Během ladění webových služeb vypršel časový limit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Když provádíte krokování do webové služby XML z volající kód, volání může někdy vypršení časového limitu, což má za následek, že se nemůže pokračovat v ladění. Může zobrazit chybová zpráva takovou situaci.  
  
```  
An unhandled exception of type 'System.Net.WebException' occurred in   
system.Web.services.dll  
Additional information: The operation has timed-out.  
```  
  
## <a name="solution"></a>Řešení  
 K tomuto problému vyhnout, nastavte hodnotu časového limitu pro volání webové služby XML k nekonečné, jak je znázorněno v tomto příkladu:  
  
```  
Service1 obj = new Service1();  
obj.TimeOut = -1; // infinite time out.  
```  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
