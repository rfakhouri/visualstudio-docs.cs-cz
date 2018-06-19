---
title: Vybrané připojení používá poskytovatele Nepodporovaná databáze
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 77519a5497c26553e2023862e46f3ba618e4f99f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31920932"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>Vybrané připojení používá poskytovatele Nepodporovaná databáze

Tato zpráva se zobrazí při přetažení položky, které nepoužívají zprostředkovatele dat .NET Framework pro SQL Server z **Průzkumníka serveru**/**Průzkumník databáze** na [technologie LINQ to SQL Nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md).

[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Podporuje pouze datová připojení, které používají zprostředkovatele rozhraní .NET Framework pro SQL Server. Platné jsou pouze připojení k serveru Microsoft SQL Server nebo Microsoft SQL Server databázový soubor.

Chcete-li tuto chybu, přidat pouze položky z připojení dat, která pomocí zprostředkovatele dat .NET Framework pro SQL Server [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

## <a name="see-also"></a>Viz také

- <xref:System.Data.SqlClient>
- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
