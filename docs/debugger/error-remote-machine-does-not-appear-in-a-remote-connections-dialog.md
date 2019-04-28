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
ms.openlocfilehash: dd194bc26574e8004894a72ce29d753cabf66a21
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850802"
---
# <a name="error-remote-machine-does-not-appear-in-a-remote-connections-dialog"></a>Chyba: Vzdálený počítač se nezobrazuje v dialogovém okně Vzdálená připojení.
Pokud vzdálený počítač se nezobrazí v dialogovém okně Vzdálená připojení, zkontrolujte následující běžné příčiny.

 Pokud používáte spravovaný režim kompatibility, zkontrolujte v dokumentaci k sadě Visual Studio 2010: [Řešení potíží s vzdálené ladění – Visual Studio 2010](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/2ys11ead(v=vs.100)).

### <a name="common-causes-for-this-error"></a>Mezi běžné příčiny této chyby

- Vzdálený počítač běží na počítači, který je v jiné podsíti. Tento problém můžete ručně zadejte název počítače nebo IP adresu v dialogovém okně kvalifikátor

- Vzdálený ladicí program není spuštěná ve vzdáleném počítači. Tento problém můžete spusťte vzdálený ladicí program.

- Brána firewall blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte bránu firewall, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.

- Antivirový software blokuje komunikaci mezi Visual Studio a vzdáleném počítači. To pokud chcete napravit, nakonfigurujte antivirový software, aby Visual Studio a vzdáleného ladicího programu (msvsmon) ke komunikaci.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)