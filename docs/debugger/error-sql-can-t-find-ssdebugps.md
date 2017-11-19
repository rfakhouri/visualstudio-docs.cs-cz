---
title: "Chyba: SQL může & č. 39; t najít ssdebugps. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 43a437cfc4be1c9168b16e4b9d1a46e2eadcb2e6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Chyba: SQL může & č. 39; t najít ssdebugps.
SSDEBUGPS.dll je součást ladění hostitel systému SQL Server.  
  
 Tato chyba nastane, když se pokoušíte spustit ladění a určuje, že zadaný soubor se nenachází na [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače. Možné příčiny jsou buď vzdálené ladění instalační program se nebude nikdy spuštěn, nebo zda nějakým způsobem nebyl odstraněn tento soubor.  
  
 Existují dva způsoby, jak vyřešit tuto chybu: opětovným spuštěním instalačního programu vzdálené ladění a pomocí kopírování souborů do [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače.  
  
 Vzdálené ladění instalační program znovu spustíte, postupujte podle pokynů v [vzdálené ladění](../debugger/remote-debugging.md).  
  
 Pokud můžete vyhledat kopii ssdebugps.dll, můžete je zkopírovat do [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače. Pokud je k dispozici, soubor bude v \Program Files\ directory běžné Files\Microsoft Shared\SQL ladění. Může být na jiném [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače, nebo na počítači, který má [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)] nainstalována.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>Kopírování SSDEBUGPS.dll do počítače serveru SQL Server 2005  
  
1.  Zkopírujte soubor do adresáře se stejným názvem a cestu na [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače.  
  
2.  Registraci otevřením **příkazového řádku**a spuštěním následujícího příkazu:  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```