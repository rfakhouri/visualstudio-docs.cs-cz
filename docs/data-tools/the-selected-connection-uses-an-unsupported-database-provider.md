---
title: Zvolené připojení využívá nepodporovaného poskytovatele databáze.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: cc74cea11e4c173a11f781af4ee78bf047353c53
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932061"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>Zvolené připojení využívá nepodporovaného poskytovatele databáze.

Tato zpráva se zobrazí při přetažení položky, které nepoužívají zprostředkovatele dat .NET Framework pro SQL Server z **Průzkumníka serveru** nebo **Průzkumník databáze** na [technologie LINQ to SQL nástroje ve Vizuálu Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md).

**O/R Designer** podporuje pouze datová připojení, které používají zprostředkovatele .NET Framework pro SQL Server. Platí pouze připojení k serveru Microsoft SQL Server nebo soubor databáze Microsoft SQL Server.

Chcete-li opravit tuto chybu, přidávat pouze položky z datová připojení, které používají zprostředkovatele dat .NET Framework pro SQL Server **O/R Designer**.

## <a name="see-also"></a>Viz také:

- <xref:System.Data.SqlClient>
- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
