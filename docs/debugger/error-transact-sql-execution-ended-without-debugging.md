---
title: 'Chyba: Spuštění Transact-SQL skončilo bez ladění. | Dokumentace Microsoftu'
ms.date: 11/08/2018
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 17c1854826de2314dfe8124d99f6ec6c8899ee70
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55011218"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Chyba: Spuštění Transact-SQL skončilo bez ladění.

Tato chyba nastane, pokud se snažíte ladit příkazů jazyka Transact-SQL nebo proceduru SQLCLR a ladicí program nebude přijímat zprávy ladění z SQL serveru.  
  
Tento problém může být kvůli potížím se sítí nebo na problémy na serveru SQL Server, ale nejpravděpodobnější příčinou je problém oprávnění.  
  
Zahrnuté jsou dva účty:  
  
- Uživatelský účet, který je účet aplikací [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] běží.  
  
- Účet připojení je identita používaná pro připojení k systému SQL Server. Tento účet není nutně stejné jako identita, která je spuštěná sada Visual Studio, jako kdyby je připojení pomocí ověřování SQL.  
  
  SQL ladění vyžaduje, aby účet aplikace musí odpovídat účtu připojení nebo správce systému.  
  
  Pokud používáte s názvem účtu SQL jako programu sa, účet aplikace musí být nastavení systému SQL Server jako správce systému. Ve výchozím nastavení jsou správci na počítači, na kterém běží SQL server na správce systému SQL Server.  
  
  Chcete-li opravit tuto chybu, potřebujete:  
  
  - Ověřte nastavení oprávnění. Další informace najdete v tématu [jak: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
  - Ujistěte se, že pokud ladění SQL zařídit správné nastavení.  
  
  - Poraďte se správcem vaší sítě nebo databáze.  
  
## <a name="see-also"></a>Viz také

- [Nastavení ladění SQL](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100))
- [Postupy: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)
- [Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)
- [Vzdálené ladění](../debugger/remote-debugging.md)