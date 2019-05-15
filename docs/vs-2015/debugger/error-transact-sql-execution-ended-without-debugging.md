---
title: 'Chyba: Spuštění Transact-SQL skončilo bez ladění. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.sqlde_sql_executed_but_not_debugged
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 7a4d4999-3973-4339-ba6a-f0d19bcb1d4a
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cdfcaa42c55f87711b0889c6a67d1a4799b84fed
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65681079"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Chyba: Spuštění Transact-SQL skončilo bez ladění.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato chyba nastane, pokud se pokoušíte ladit příkazů jazyka Transact-SQL nebo proceduru SQLCLR a ladicí program nepřijímá zprávy ladění z SQL serveru.  
  
 Může to být kvůli potížím se sítí nebo na problémy na serveru SQL Server, ale nejpravděpodobnější příčinou je problém oprávnění.  
  
 Zahrnuté jsou dva účty:  
  
- Uživatelský účet, který je účet aplikací [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] běží.  
  
- Účet připojení je identita používaná pro připojení k systému SQL Server. Toto není nutně stejné jako identita, která je spuštěná sada Visual Studio, jako kdyby je připojení pomocí ověřování SQL.  
  
  SQL ladění vyžaduje, aby účet aplikace musí odpovídat účtu připojení, nebo správce systému.  
  
  Pokud používáte přihlašovací jméno SQL jako programu sa, účet aplikace musí být instalační program systému SQL Server jako správce systému. Ve výchozím nastavení, správci na počítači systému SQL server běží se na správce systému SQL Server.  
  
  Chcete-li opravit tuto chybu, potřebujete:  
  
- Ověřte nastavení oprávnění. Další informace najdete v tématu [jak: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
- Ujistěte se, že pokud ladění SQL zařídit správné nastavení.  
  
- Poraďte se správcem vaší sítě nebo databáze.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladění SQL](https://msdn.microsoft.com/3db09e68-edcc-42de-9c22-4e97cfd55ab3)   
 [Postupy: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)
