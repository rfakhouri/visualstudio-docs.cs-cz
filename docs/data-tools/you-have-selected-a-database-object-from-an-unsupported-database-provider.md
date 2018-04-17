---
title: Výběru objektu databáze od poskytovatele Nepodporovaná databáze | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5dfb475cdb1b63e4dfcaaebcda4b5d2dc3a7f070
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="you-have-selected-a-database-object-from-an-unsupported-database-provider"></a>Od poskytovatele Nepodporovaná databáze výběru objektu databáze
Návrhář relací objektů podporuje pouze zprostředkovatele dat .NET Framework pro SQL Server (<xref:System.Data.SqlClient>). I když můžete kliknout na **OK** a pokračovat v práci s objekty od poskytovatelů Nepodporovaná databáze, může dojít k neočekávanému chování za běhu.  
  
> [!NOTE]
>  Podporovaná jsou jenom připojení dat, které používají zprostředkovatele dat .NET Framework pro SQL Server.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Click **OK**.

   Navrhování tříd entit, které jsou mapovány na připojení, který používá poskytovatele Nepodporovaná databáze můžete pokračovat. Při použití zprostředkovatele Nepodporovaná databáze, může dojít k neočekávanému chování.  
  
     -nebo-  
  
- Klikněte na tlačítko **zrušit**.

   Akce je zastavena. Vytvořit nebo použít datové připojení, které používá zprostředkovatel rozhraní .NET Framework pro SQL Server.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)