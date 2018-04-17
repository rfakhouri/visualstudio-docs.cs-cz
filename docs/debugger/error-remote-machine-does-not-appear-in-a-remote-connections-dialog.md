---
title: 'Chyba: Vzdálený počítač nezobrazí v dialogovém okně Vzdálená připojení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 278919a2cd102565faedd799519247d7ea2a5a8a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Chyba: Vzdálený počítač nezobrazí v dialogovém okně Vzdálená připojení
Pokud vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení, zkontrolujte následující běžné příčiny.  
  
 Pokud používáte režim spravované kompatibility, zkontrolujte v dokumentaci sady Visual Studio 2010: [řešení potíží s vzdálené ladění – Visual Studio 2010](https://msdn.microsoft.com/en-us/library/2ys11ead\(v=vs.100\).aspx) .  
  
### <a name="common-causes-for-this-error"></a>Mezi běžné příčiny této chyby  
  
-   Vzdálený počítač běží na počítači, který je v jiné podsíti. Chcete-li odstranit tento problém, ručně zadejte název počítače nebo IP adresu v dialogovém okně kvalifikátor  
  
-   Vzdáleného ladicího programu není spuštěna ve vzdáleném počítači. Chcete-li odstranit tento problém, spusťte vzdáleného ladicího programu.  
  
-   Brána firewall blokuje komunikaci mezi Visual Studio a vzdálený počítač. Chcete-li odstranit tento problém, konfigurace brány firewall umožňující Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.  
  
-   Antivirový software blokuje komunikaci mezi Visual Studio a vzdálený počítač. Chcete-li odstranit tento problém, nakonfigurujte antivirový software umožňuje sadě Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)