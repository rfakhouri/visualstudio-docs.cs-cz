---
title: 'Chyba: Můžete SQL&#39;t najít ssdebugps. | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 25462a99bd3e773f03af3918a9e25d11ed006c1c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68185195"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Chyba: Můžete SQL&#39;t najít ssdebugps.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Ssdebugps.dll nebyl je součást ladění hostitel systému SQL Server.  
  
 Tato chyba nastane, pokud se pokoušíte spustit ladění a označuje, že zadaný soubor není k dispozici na [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače. Možné příčiny, že buď nastavení vzdáleného ladění byla nespouštět nebo že nějakým způsobem získali odstranit tento soubor.  
  
 Existují dva způsoby, jak vyřešit tuto chybu: opětovným spuštěním instalačního programu vzdálené ladění a zkopírováním do souboru [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače.  
  
 Znovu spusťte instalační program vzdálené ladění, postupujte podle pokynů v [vzdálené ladění](../debugger/remote-debugging.md).  
  
 Pokud můžete vyhledat kopii ssdebugps.dll nebyl, můžete zkopírovat ho do [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače. Pokud jsou k dispozici, soubor bude v adresáři \Program Files\ běžné Files\Microsoft Shared\SQL ladění. Možná pro vás bude na jiném [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] strojově, nebo na počítači, který má [!INCLUDE[vsprvslong](../includes/vsprvslong-md.md)] nainstalované.  
  
### <a name="to-copy-ssdebugpsdll-onto-the-sql-server-2005-machine"></a>Ke zkopírování ssdebugps.dll nebyl do počítače serveru SQL Server 2005  
  
1. Zkopírujte soubor do adresáře se stejným názvem a cestu na [!INCLUDE[sqprsqlong](../includes/sqprsqlong-md.md)] počítače.  
  
2. Zaregistrujte ho tak, že otevřete **příkazového řádku**a spuštěním následujícího příkazu:  
  
    ```  
    regsvr32 ssdebugps.dll  
    ```
