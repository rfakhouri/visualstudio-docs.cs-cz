---
title: 'Chyba: Uživatel může nemohl spustit uloženou proceduru sp_enable_sql_debug. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.sqlde_accessdenied
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 11957495-c238-4cc5-8937-e4026f5e10e1
caps.latest.revision: 9
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 759386728283d3d39219133e53668afe3259714a
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697676"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Chyba: Uživatel může nemohl spustit uloženou proceduru sp_enable_sql_debug.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Uloženou proceduru sp_enable_sql_debug. nelze spustit na serveru. To může být způsobeno:  
  
- Problém připojením. Musíte mít stabilní připojení k serveru.  
  
- Chybí nezbytná oprávnění na serveru. Chcete-li ladit na SQL Server 2005, musí být účet, který spouští sady Visual Studio a účet používaný pro připojení k systému SQL Server členové sysadmin role. Účet používaný pro připojení k systému SQL Server je váš uživatelský účet Windows (Pokud používáte ověřování Windows) nebo účet s ID uživatele a heslo (Pokud používáte ověřování SQL).  
  
  Další informace najdete v tématu [jak: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414).  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)   
 [Nastavení ladění SQL](https://msdn.microsoft.com/3db09e68-edcc-42de-9c22-4e97cfd55ab3)
