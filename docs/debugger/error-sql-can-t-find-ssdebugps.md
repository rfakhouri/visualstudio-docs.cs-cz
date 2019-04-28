---
title: 'Chyba: Můžete SQL&#39;t najít ssdebugps. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.sqlde_cant_find_ssdebugps
dev_langs:
- CSharp
- VB
- FSharp
- C++
- SQL
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 854105ea5d94f6d3b09ce73a23ec45ccab9e797c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850488"
---
# <a name="error-sql-can39t-find-ssdebugps"></a>Chyba: Můžete SQL&#39;t najít ssdebugps.

Ssdebugps.dll nebyl je součást ladění hostitel systému SQL Server.

Tato chyba nastane, pokud se pokoušíte spustit ladění a označuje, že zadaný soubor není k dispozici na [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače. Možné příčiny, že buď nastavení vzdáleného ladění byla nespouštět nebo že nějakým způsobem získali odstranit tento soubor.

Existují dva způsoby, jak vyřešit tuto chybu: opětovným spuštěním instalačního programu vzdálené ladění a zkopírováním do souboru [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače.

Znovu spusťte instalační program vzdálené ladění, postupujte podle pokynů v [vzdálené ladění](../debugger/remote-debugging.md).

Pokud můžete vyhledat kopii ssdebugps.dll nebyl, můžete zkopírovat ho do [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače. Pokud jsou k dispozici, soubor bude v adresáři \Program Files\ běžné Files\Microsoft Shared\SQL ladění. Možná pro vás bude na jiném [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] strojově, nebo na počítači, který má nainstalované Visual Studio 2005.

Zkopírování ssdebugps.dll nebyl do počítače serveru SQL Server 2005:

1. Zkopírujte soubor do adresáře se stejným názvem a cestu na [!INCLUDE[sqprsqlong](../debugger/includes/sqprsqlong_md.md)] počítače.

2. Zaregistrujte ho tak, že otevřete **příkazového řádku**a spuštěním následujícího příkazu:

    ```cmd
    regsvr32 ssdebugps.dll
    ```
