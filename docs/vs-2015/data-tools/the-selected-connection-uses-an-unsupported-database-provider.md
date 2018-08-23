---
title: Zvolené připojení využívá nepodporovaného poskytovatele databáze. | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d25dfa1-8fa4-4529-9b90-973bc2ec2993
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4e38bda495521bf81c6eb4b9a00a0f32620a71fb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629682"
---
# <a name="the-selected-connection-uses-an-unsupported-database-provider"></a>Zvolené připojení využívá nepodporovaného poskytovatele databáze.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [zvolené připojení využívá nepodporovaného poskytovatele databáze](https://docs.microsoft.com/visualstudio/data-tools/the-selected-connection-uses-an-unsupported-database-provider).  
  
  
Tato zpráva se zobrazí při přetažení položky, které nepoužívají zprostředkovatele dat .NET Framework pro SQL Server z **Průzkumníka serveru**/**Průzkumník databáze** na [technologie LINQ to SQL Nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md).  
  
 [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] Podporuje pouze datová připojení, které používají zprostředkovatele .NET Framework pro SQL Server. Platí pouze připojení k serveru Microsoft SQL Server nebo soubor databáze Microsoft SQL Server.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Přidat pouze položky z datových připojení, které používají zprostředkovatele dat .NET Framework pro SQL Server [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Data.SqlClient>   
 [Připojování k datům v sadě Visual Studio](../data-tools/connecting-to-data-in-visual-studio.md)   
 [Zprostředkovatelé dat .NET framework](http://msdn.microsoft.com/library/03a9fc62-2d24-491a-9fe6-d6bdb6dcb131)   
 [Návod: Vytvoření třídy LINQ to SQL (Návrhář O-R)](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [Vytváření datových aplikací](../data-tools/creating-data-applications.md)

