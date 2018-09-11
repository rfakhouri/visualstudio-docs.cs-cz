---
title: 'Chyba: Spuštění Transact-SQL skončilo bez ladění. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
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
ms.openlocfilehash: 5e6ae81608ee476e3748fde6830dfaa11c119f7a
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283129"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Chyba: Spuštění Transact-SQL skončilo bez ladění.
Tato chyba nastane, pokud se pokoušíte ladit příkazů jazyka Transact-SQL nebo proceduru SQLCLR a ladicí program nepřijímá zprávy ladění z SQL serveru.  
  
 Může to být kvůli potížím se sítí nebo na problémy na serveru SQL Server, ale nejpravděpodobnější příčinou je problém oprávnění.  
  
 Zahrnuté jsou dva účty:  
  
-   Uživatelský účet, který je účet aplikací [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží.  
  
-   Účet připojení je identita používaná pro připojení k systému SQL Server. Toto není nutně stejné jako identita, která je spuštěná sada Visual Studio, jako kdyby je připojení pomocí ověřování SQL.  
  
 SQL ladění vyžaduje, aby účet aplikace musí odpovídat účtu připojení, nebo správce systému.  
  
 Pokud používáte přihlašovací jméno SQL jako programu sa, účet aplikace musí být instalační program systému SQL Server jako správce systému. Ve výchozím nastavení, správci na počítači systému SQL server běží se na správce systému SQL Server.  
  
 Chcete-li opravit tuto chybu, potřebujete:  
  
-   Ověřte nastavení oprávnění. Další informace najdete v tématu [jak: nastavit SQL Server oprávnění pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
-   Ujistěte se, že pokud ladění SQL zařídit správné nastavení.  
  
-   Poraďte se správcem vaší sítě nebo databáze.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladění SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100))   
 [Postupy: nastavení oprávnění serveru SQL pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)