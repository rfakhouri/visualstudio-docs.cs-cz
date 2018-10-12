---
title: 'Chyba: Uživatel může nemohl spustit uloženou proceduru sp_enable_sql_debug. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.sqlde_accessdenied
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 11957495-c238-4cc5-8937-e4026f5e10e1
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b732c7d562c97e1043bb6dc62bba7d3a405227b9
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254006"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Chyba: Uživatel nemohl spustit uloženou proceduru sp_enable_sql_debug.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Uloženou proceduru sp_enable_sql_debug. nelze spustit na serveru. To může být způsobeno:  
  
-   Problém připojením. Musíte mít stabilní připojení k serveru.  
  
-   Chybí nezbytná oprávnění na serveru. Chcete-li ladit na SQL Server 2005, musí být účet, který spouští sady Visual Studio a účet používaný pro připojení k systému SQL Server členové sysadmin role. Účet používaný pro připojení k systému SQL Server je váš uživatelský účet Windows (Pokud používáte ověřování Windows) nebo účet s ID uživatele a heslo (Pokud používáte ověřování SQL).  
  
 Další informace najdete v tématu [jak: nastavit SQL Server oprávnění pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavení oprávnění serveru SQL pro ladění](http://msdn.microsoft.com/en-us/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladění SQL](http://msdn.microsoft.com/en-us/3db09e68-edcc-42de-9c22-4e97cfd55ab3)



