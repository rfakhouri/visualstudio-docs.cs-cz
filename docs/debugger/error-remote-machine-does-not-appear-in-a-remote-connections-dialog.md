---
title: 'Chyba: Vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
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
ms.openlocfilehash: a081eceb137c7958a489fb0968f190d0d01b32fa
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56698362"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Chyba: Vzdálený počítač se nezobrazuje v dialogovém okně Vzdálená připojení.
Pokud vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení, zkontrolujte následující běžné příčiny.

 Pokud používáte spravovaný režim kompatibility, zkontrolujte v dokumentaci k sadě Visual Studio 2010: [Řešení potíží s vzdálené ladění – Visual Studio 2010](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/2ys11ead(v=vs.100)).

### <a name="common-causes-for-this-error"></a>Mezi běžné příčiny této chyby

-   Vzdálený počítač běží na počítači, který je v jiné podsíti. Tento problém můžete ručně zadejte název počítače nebo IP adresu v dialogovém okně kvalifikátor

-   Vzdálený ladicí program není spuštěná ve vzdáleném počítači. Tento problém můžete spusťte vzdálený ladicí program.

-   Brána firewall blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte bránu firewall, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.

-   Antivirový software blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte antivirový software, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)