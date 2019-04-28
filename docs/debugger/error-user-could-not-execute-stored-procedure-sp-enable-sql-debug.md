---
title: 'Chyba: Uživatel může nemohl spustit uloženou proceduru sp_enable_sql_debug. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e051cd594ee26a57fdbb7dcdc5bdad81f06cf771
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850093"
---
# <a name="error-user-could-not-execute-stored-procedure-spenablesqldebug"></a>Chyba: Uživatel může nemohl spustit uloženou proceduru sp_enable_sql_debug.

Uloženou proceduru sp_enable_sql_debug. nelze spustit na serveru. To může být způsobeno:

- Problém připojením. Musíte mít stabilní připojení k serveru.

- Chybí nezbytná oprávnění na serveru. Chcete-li ladit na SQL Server 2005, musí být účet, který spouští sady Visual Studio a účet používaný pro připojení k systému SQL Server členové sysadmin role. Účet používaný pro připojení k systému SQL Server je váš uživatelský účet Windows (Pokud používáte ověřování Windows) nebo účet s ID uživatele a heslo (Pokud používáte ověřování SQL).

Další informace najdete v tématu [jak: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414).

## <a name="see-also"></a>Viz také

- [Postupy: Nastavení oprávnění serveru SQL pro ladění](https://msdn.microsoft.com/84e088d0-0409-41d4-841b-f5d4b0fda414)
- [Nastavení ladění SQL](/previous-versions/visualstudio/visual-studio-2010/s4sszxst\(v\=vs.100\))