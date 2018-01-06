---
title: "Chyba: Vypršení časového limitu při ladění webových služeb | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
- XML Web services, timeout while debugging
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 25b53910dd51dc9535ee2e9e6009fb435bd70735
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-timeout-while-debugging-web-services"></a>Chyba: Během ladění webových služeb vypršel časový limit.
Pokud jste se zanoříte se do webové služby XML z volání kódu, volání může někdy v důsledku vypršení časového limitu že nemůže pokračovat, ladění. Může zobrazit chybová zpráva typu to.  
  
```  
An unhandled exception of type 'System.Net.WebException' occurred in   
system.Web.services.dll  
Additional information: The operation has timed-out.  
```  
  
## <a name="solution"></a>Řešení  
 K tomuto problému nedošlo, nastavte hodnotu časového limitu pro volání webové služby XML na nekonečný, jak je znázorněno v tomto příkladu:  
  
```  
Service1 obj = new Service1();  
obj.TimeOut = -1; // infinite time out.  
```  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)