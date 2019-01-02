---
title: Vybrali jste databázový objekt od nepodporovaného poskytovatele databáze.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 4efaf92c9f4688d6870c1152be27eb4c8f4ed933
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53894438"
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>Vybrali jste databázový objekt od nepodporovaného poskytovatele databáze.

**O/R Designer** podporuje pouze zprostředkovatele dat .NET Framework pro SQL Server (<xref:System.Data.SqlClient>). I když můžete kliknout na **OK** a pokračovat v práci s objekty od poskytovatelů Nepodporovaná databáze, vám může dojít k neočekávanému chování za běhu.

> [!NOTE]
> Jsou podporovány pouze datová připojení, které používají zprostředkovatele dat .NET Framework pro SQL Server.

## <a name="to-correct-this-error"></a>Oprava této chyby

- Klikněte na **OK**.

   Navrhování tříd entit, které mapují na připojení, které používá nepodporovaného poskytovatele databáze. můžete pokračovat. Při použití nepodporované databázové poskytovatelů, může dojít k neočekávanému chování.

    -nebo-

- Klikněte na tlačítko **zrušit**.

   Tato akce je zastavená. Vytvořit nebo použít datové připojení, který používá zprostředkovatele .NET Framework pro SQL Server.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)