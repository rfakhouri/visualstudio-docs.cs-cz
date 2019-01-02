---
title: 'Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM. | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
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
ms.openlocfilehash: f507f8f2630c001beb9aad3e6f76904e6cd11489
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53887500"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>Chyba: Vzdálený počítač nemohl inicializovat komunikaci modelu DCOM.
Při pokusu o komunikaci s místním počítači, na vzdáleném počítači došlo k chybě modelu DCOM. Místní počítač je počítač, který je  
  
 spuštění sady Visual Studio. Této chybě může dojít z několika důvodů:  
  
-   Místní počítač má povolenou bránu firewall.  
  
-   Ověřování Windows ze vzdáleného počítače v místním počítači nefunguje.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Pokud místní počítač má povolenou bránu Windows Firewall, přečtěte si téma [vzdálené ladění](../debugger/remote-debugging.md) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
2.  Testovací ověření Windows tak, že zkusíte otevřít sdílené složky na místním počítači ze vzdáleného serveru.  
  
3.  Chcete-li obnovit ověřování Windows, zkuste restartovat oba počítače. Zkontrolujte protokoly událostí na místních i vzdálených počítačů pro chyby protokolu Kerberos a obraťte se na správce domény pro známé problémy.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)