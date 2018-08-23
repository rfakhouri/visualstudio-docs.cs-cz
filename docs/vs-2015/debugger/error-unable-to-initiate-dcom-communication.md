---
title: 'Chyba: Nepovedlo se inicializovat komunikaci modelu DCOM | Dokumentace Microsoftu'
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
- vs.debug.error.unmarshal_server_failed
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 2a7b27e6-2526-4f32-bc4d-eaee447f24ec
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1c8ee1e5a9a9f799a4e9d5d8a4cc3b6f5e03b504
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669440"
---
# <a name="error-unable-to-initiate-dcom-communication"></a>Chyba: Nelze inicializovat komunikaci modelu DCOM.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: nepovedlo se inicializovat komunikaci modelu DCOM](https://docs.microsoft.com/visualstudio/debugger/error-unable-to-initiate-dcom-communication).  
  
Při místní počítač se pokusil komunikovat se vzdáleným počítačem došlo k chybě modelu DCOM. To je způsobeno brány firewall na vzdálený server nebo porušený ověřování Windows na vzdáleném počítači.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pokud vzdálený počítač má povolenou bránu Windows Firewall, přečtěte si téma [nastavit Up the Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.  
  
-   Chcete-li obnovit ověřování Windows, zkuste restartovat oba počítače. Zkontrolujte protokoly událostí na místních i vzdálených počítačů pro chyby protokolu Kerberos a obraťte se na správce domény pro známé problémy.  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)



