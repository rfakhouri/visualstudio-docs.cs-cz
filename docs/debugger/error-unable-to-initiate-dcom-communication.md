---
title: 'Chyba: Nelze inicializovat komunikaci modelu DCOM | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.unmarshal_server_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 2a7b27e6-2526-4f32-bc4d-eaee447f24ec
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c80f2455b53cba46f0f2f753c55ff1b7e9dad8d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-unable-to-initiate-dcom-communication"></a>Chyba: Nelze inicializovat komunikaci modelu DCOM.
Při pokusu o komunikaci s vzdálený počítač v místním počítači došlo k chybě DCOM. To je způsobeno brány firewall na vzdálený server nebo přerušená ověřování systému Windows ve vzdáleném počítači.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud vzdálený počítač povolíte bránu Windows Firewall, najdete v části [vzdálené ladění](../debugger/remote-debugging.md) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
-   Chcete-li obnovit ověřování systému Windows, zkuste restartování obou počítačů. Zkontrolujte protokoly událostí na místních i vzdálených počítačích pro chyby protokolu Kerberos a známé problémy, kontaktujte správce domény.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)