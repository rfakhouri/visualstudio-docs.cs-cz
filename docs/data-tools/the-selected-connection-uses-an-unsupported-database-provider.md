---
title: Zvolené připojení využívá nepodporovaného poskytovatele databáze.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 5fab6be50a9b4c273a7bb911d8afde5cf65d7676
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460586"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>Zvolené připojení využívá nepodporovaného poskytovatele databáze.

Tato zpráva se zobrazí při přetažení položky, které nepoužívají zprostředkovatele dat .NET Framework pro SQL Server z **Průzkumníka serveru** nebo **Průzkumník databáze** na [technologie LINQ to SQL nástroje ve Vizuálu Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md).

**O/R Designer** podporuje pouze datová připojení, které používají zprostředkovatele .NET Framework pro SQL Server. Platí pouze připojení k serveru Microsoft SQL Server nebo soubor databáze Microsoft SQL Server.

Chcete-li opravit tuto chybu, přidávat pouze položky z datová připojení, které používají zprostředkovatele dat .NET Framework pro SQL Server **O/R Designer**.

## <a name="see-also"></a>Viz také:

- <xref:System.Data.SqlClient>
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
