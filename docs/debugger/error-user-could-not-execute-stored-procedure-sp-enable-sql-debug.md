---
title: "Chyba: Uživatel může nemohl spustit uloženou proceduru sp_enable_sql_debug. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.sqlde_accessdenied
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 11957495-c238-4cc5-8937-e4026f5e10e1
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5ab29925b12bfb14ba8f37d371c30aa6f312ea15
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Chyba: Uživatel nemohl spustit uloženou proceduru sp_enable_sql_debug.
Uloženou proceduru sp_enable_sql_debug nelze spustit na serveru. To může být způsobeno:  
  
-   Problému s připojením. Je potřeba mít stabilní připojení k serveru.  
  
-   Chybí nezbytná oprávnění na serveru. K ladění na SQL Server 2005, účet, který spouští sady Visual Studio i účet používaný pro připojení k systému SQL Server musí být členem sysadmin role. Účet používaný pro připojení k systému SQL Server je uživatelský účet systému Windows (Pokud používáte ověřování systému Windows) nebo účet s ID uživatele a heslo (Pokud používáte ověřování SQL).  
  
 Další informace najdete v tématu [postupy: nastavení SQL serveru oprávnění pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavení oprávnění serveru SQL pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení SQL ladění](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)