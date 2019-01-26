---
title: 'Chyba: Nepovedlo se inicializovat komunikaci modelu DCOM | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unmarshal_server_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 89dc5ba98d706153b919063563f1d4beecacdde5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54932061"
---
# <a name="error-unable-to-initiate-dcom-communication"></a>Chyba: Nelze inicializovat komunikaci modelu DCOM.
Při místní počítač se pokusil komunikovat se vzdáleným počítačem došlo k chybě modelu DCOM. To je způsobeno brány firewall na vzdálený server nebo porušený ověřování Windows na vzdáleném počítači.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud vzdálený počítač má povolenou bránu Windows Firewall, přečtěte si téma [vzdálené ladění](../debugger/remote-debugging.md) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
-   Chcete-li obnovit ověřování Windows, zkuste restartovat oba počítače. Zkontrolujte protokoly událostí na místních i vzdálených počítačů pro chyby protokolu Kerberos a obraťte se na správce domény pro známé problémy.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)