---
title: 'Chyba: Vzdálený počítač nezobrazí v dialogovém okně Vzdálená připojení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
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
ms.openlocfilehash: c52a2ebd99b052171220fd8a06f1ae7ff5dc258e
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31471330"
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