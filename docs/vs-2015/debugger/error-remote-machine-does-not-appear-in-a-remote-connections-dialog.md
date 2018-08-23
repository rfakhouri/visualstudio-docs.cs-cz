---
title: 'Chyba: Vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 5fd98a5b-2cf3-4438-8b0f-6f1a742a62ce
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 552be1e38cdb7401af36b287b23091d754c35980
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674449"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Chyba: Vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení](https://docs.microsoft.com/visualstudio/debugger/error-remote-machine-does-not-appear-in-a-remote-connections-dialog).  
  
Pokud vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení, zkontrolujte následující běžné příčiny.  
  
 Pokud používáte spravovaný režim kompatibility, zkontrolujte v dokumentaci k sadě Visual Studio 2010: [řešení potíží s vzdálené ladění – Visual Studio 2010](https://msdn.microsoft.com/library/2ys11ead\(v=vs.100\).aspx) .  
  
### <a name="common-causes-for-this-error"></a>Mezi běžné příčiny této chyby  
  
-   Vzdálený počítač běží na počítači, který je v jiné podsíti. Tento problém můžete ručně zadejte název počítače nebo IP adresu v dialogovém okně kvalifikátor  
  
-   Vzdálený ladicí program není spuštěná ve vzdáleném počítači. Tento problém můžete spusťte vzdálený ladicí program.  
  
-   Brána firewall blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte bránu firewall, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.  
  
-   Antivirový software blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte antivirový software, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)



