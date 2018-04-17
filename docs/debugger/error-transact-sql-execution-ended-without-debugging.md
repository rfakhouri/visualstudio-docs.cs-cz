---
title: 'Chyba: Spuštění Transact-SQL skončilo bez ladění. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 621d6411a6702b4449768ee6850e5bdf42b85946
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Chyba: Spuštění Transact-SQL skončilo bez ladění.
K této chybě dojde, když se pokoušíte ladění jazyka Transact-SQL nebo SQLCLR postupu a ladicí program nepřijímá zprávy ladění z SQL serveru.  
  
 Může to být kvůli problémům v síti nebo na problémy na serveru SQL Server, ale nejpravděpodobnější příčinou je problém oprávnění.  
  
 Existují dva účty související se situací:  
  
-   Účet aplikací je uživatelský účet, který [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží jako.  
  
-   Účet připojení je identita použitá k připojení k systému SQL Server. Nejedná se nutně stejné jako identity, která Visual Studio je spuštěna jako v případě, že připojení je pomocí ověřování SQL.  
  
 Ladění SQL vyžaduje, aby účet aplikací musí odpovídat účtu připojení nebo sysadmin.  
  
 Pokud používáte přihlašovací jméno SQL jako sa, účet aplikace musí být instalační program systému SQL Server jako správce systému. Ve výchozím nastavení, správci systému SQL server počítač běží na jsou sysadmins systému SQL Server.  
  
 Chcete-li tuto chybu můžete potřebovat k:  
  
-   Ověřte nastavení oprávnění. Další informace najdete v tématu [postupy: nastavení SQL serveru oprávnění pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
-   Ujistěte se, že pokud ladění SQL správně nastavené.  
  
-   Podívejte se na správce sítě nebo databáze.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení SQL ladění](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)   
 [Postupy: nastavení oprávnění serveru SQL pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)