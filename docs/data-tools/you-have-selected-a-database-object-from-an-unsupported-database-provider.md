---
title: "Výběru objektu databáze od poskytovatele Nepodporovaná databáze | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0f1298e-31aa-471e-ae19-1bafffd2ae40
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 05e638be5cc11f66052e5a1f6116e7205b824106
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
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
[Návrhář relací objektů zprávy](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)