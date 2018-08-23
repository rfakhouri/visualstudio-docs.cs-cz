---
title: 'Chyba: SQL můžete&#39;t najít ssdebugps. | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- FSharp
- VB
- CSharp
- C++
- SQL
ms.assetid: 596425c8-14c7-4c05-8823-e1c52f420f5e
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1782412ded2c4edff0da29b13160107664170d20
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669915"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Chyba: SQL můžete&#39;t najít ssdebugps.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: SQL můžete&#39;t najít ssdebugps](https://docs.microsoft.com/visualstudio/debugger/error-sql-can-t-find-ssdebugps).  
  
Ssdebugps.dll nebyl je součást ladění hostitel systému SQL Server.  
  
 Tato chyba nastane, pokud se pokoušíte spustit ladění a označuje, že zadaný soubor není k dispozici na [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače. Možné příčiny, že buď nastavení vzdáleného ladění byla nespouštět nebo že nějakým způsobem získali odstranit tento soubor.  
  
 Existují dva způsoby, jak vyřešit tuto chybu: opětovným spuštěním instalačního programu vzdálené ladění a zkopírováním do souboru [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače.  
  
 Znovu spusťte instalační program vzdálené ladění, postupujte podle pokynů v [vzdálené ladění](../debugger/remote-debugging.md).  
  
 Pokud můžete vyhledat kopii ssdebugps.dll nebyl, můžete zkopírovat ho do [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače. Pokud jsou k dispozici, soubor bude v adresáři \Program Files\ běžné Files\Microsoft Shared\SQL ladění. Možná pro vás bude na jiném [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] strojově, nebo na počítači, který má [!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)] nainstalované.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>Ke zkopírování ssdebugps.dll nebyl do počítače serveru SQL Server 2005  
  
1.  Zkopírujte soubor do adresáře se stejným názvem a cestu na [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače.  
  
2.  Zaregistrujte ho tak, že otevřete **příkazového řádku**a spuštěním následujícího příkazu:  
  
    ```  
    regsrv32 ssdebugps.dll  
    ```



