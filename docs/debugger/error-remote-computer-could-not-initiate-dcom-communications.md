---
title: 'Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
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
ms.openlocfilehash: 5e104e63bf9dde11efbefe4b657a85b3bfc94549
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM.
Chyba DCOM došlo k chybě při pokusu o komunikaci s místní počítač vzdáleného počítače. Je na počítač, který je v místním počítači  
  
 spuštění sady Visual Studio. Této chybě může dojít z několika důvodů:  
  
-   Místní počítače je povolena brána firewall.  
  
-   Ověřování systému Windows ze vzdáleného počítače v místním počítači nefunguje.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Pokud místní počítač povolíte bránu Windows Firewall, najdete v části [vzdálené ladění](../debugger/remote-debugging.md) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
2.  Test ověřování systému Windows tak, že zkusíte otevřete sdílené složky v místním počítači ze vzdáleného serveru.  
  
3.  Chcete-li obnovit ověřování systému Windows, zkuste restartování obou počítačů. Zkontrolujte protokoly událostí na místních i vzdálených počítačích pro chyby protokolu Kerberos a známé problémy, kontaktujte správce domény.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)