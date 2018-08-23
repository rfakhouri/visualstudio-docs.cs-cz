---
title: 'Chyba: Spuštění Transact-SQL skončilo bez ladění. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7de8aaba3abf4ef7c767ed549b5454b1599e808d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676904"
---
# <a name="error-transact-sql-execution-ended-without-debugging"></a>Chyba: Spuštění Transact-SQL skončilo bez ladění.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: spuštění Transact-SQL skončilo bez ladění](https://docs.microsoft.com/visualstudio/debugger/error-transact-sql-execution-ended-without-debugging).  
  
Tato chyba nastane, pokud se pokoušíte ladit příkazů jazyka Transact-SQL nebo proceduru SQLCLR a ladicí program nepřijímá zprávy ladění z SQL serveru.  
  
 Může to být kvůli potížím se sítí nebo na problémy na serveru SQL Server, ale nejpravděpodobnější příčinou je problém oprávnění.  
  
 Zahrnuté jsou dva účty:  
  
-   Uživatelský účet, který je účet aplikací [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] běží.  
  
-   Účet připojení je identita používaná pro připojení k systému SQL Server. Toto není nutně stejné jako identita, která je spuštěná sada Visual Studio, jako kdyby je připojení pomocí ověřování SQL.  
  
 SQL ladění vyžaduje, aby účet aplikace musí odpovídat účtu připojení, nebo správce systému.  
  
 Pokud používáte přihlašovací jméno SQL jako programu sa, účet aplikace musí být instalační program systému SQL Server jako správce systému. Ve výchozím nastavení, správci na počítači systému SQL server běží se na správce systému SQL Server.  
  
 Chcete-li opravit tuto chybu, potřebujete:  
  
-   Ověřte nastavení oprávnění. Další informace najdete v tématu [jak: nastavit SQL Server oprávnění pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
-   Ujistěte se, že pokud ladění SQL zařídit správné nastavení.  
  
-   Poraďte se správcem vaší sítě nebo databáze.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení ladění SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)   
 [Postupy: nastavení oprávnění serveru SQL pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Vzdálené ladění](../debugger/remote-debugging.md)



