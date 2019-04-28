---
title: 'Chyba: Vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 5fd98a5b-2cf3-4438-8b0f-6f1a742a62ce
caps.latest.revision: 5
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4136a320f53f37377b9f6ffbff5a48a8be746276
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62535590"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Chyba: Vzdálený počítač se nezobrazuje v dialogovém okně Vzdálená připojení.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení, zkontrolujte následující běžné příčiny.  
  
 Pokud používáte spravovaný režim kompatibility, zkontrolujte v dokumentaci k sadě Visual Studio 2010: [Řešení potíží s vzdálené ladění – Visual Studio 2010](https://msdn.microsoft.com/library/2ys11ead\(v=vs.100\).aspx) .  
  
### <a name="common-causes-for-this-error"></a>Mezi běžné příčiny této chyby  
  
- Vzdálený počítač běží na počítači, který je v jiné podsíti. Tento problém můžete ručně zadejte název počítače nebo IP adresu v dialogovém okně kvalifikátor  
  
- Vzdálený ladicí program není spuštěná ve vzdáleném počítači. Tento problém můžete spusťte vzdálený ladicí program.  
  
- Brána firewall blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte bránu firewall, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.  
  
- Antivirový software blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte antivirový software, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.  
  
## <a name="see-also"></a>Viz také  
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)
