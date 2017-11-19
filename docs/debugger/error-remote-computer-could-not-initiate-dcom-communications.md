---
title: "Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.unmarshal_callback_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: bbba0766-2502-4ef1-a75d-bf1f0db39e37
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 377211f0ca7e4095da58b169f113689db9c7b41e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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