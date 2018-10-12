---
title: 'Chyba: Vypršel časový limit při ladění webových služeb | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
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
helpviewer_keywords:
- debugger, Web application errors
- XML Web services, timeout while debugging
ms.assetid: 4b7df112-788a-4429-9a0c-4c6dac4fb609
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b84ac5a8142250f9c71d9617a6717a1962b7106
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49190330"
---
# <a name="error-timeout-while-debugging-web-services"></a>Chyba: Během ladění webových služeb vypršel časový limit.
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



