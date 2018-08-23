---
title: 'Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM. | Dokumentace Microsoftu'
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
- vs.debug.error.unmarshal_callback_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: bbba0766-2502-4ef1-a75d-bf1f0db39e37
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 79548e2fbfbb4c10ce912ab90cd0541aea7f1200
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676887"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>Chyba: Vzdálený počítač nemohl inicializovat komunikace modelu DCOM.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: vzdálený počítač nemohl inicializovat komunikace modelu DCOM](https://docs.microsoft.com/visualstudio/debugger/error-remote-computer-could-not-initiate-dcom-communications).  
  
Při pokusu o komunikaci s místním počítači, na vzdáleném počítači došlo k chybě modelu DCOM. Místní počítač je počítač, který je  
  
 spuštění sady Visual Studio. Této chybě může dojít z několika důvodů:  
  
-   Místní počítač má povolenou bránu firewall.  
  
-   Ověřování Windows ze vzdáleného počítače v místním počítači nefunguje.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Pokud místní počítač má povolenou bránu Windows Firewall, přečtěte si téma [nastavit Up the Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
2.  Testovací ověření Windows tak, že zkusíte otevřít sdílené složky na místním počítači ze vzdáleného serveru.  
  
3.  Chcete-li obnovit ověřování Windows, zkuste restartovat oba počítače. Zkontrolujte protokoly událostí na místních i vzdálených počítačů pro chyby protokolu Kerberos a obraťte se na správce domény pro známé problémy.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



