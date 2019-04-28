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
ms.openlocfilehash: 1112ec72e8aca764f749a6d8f1925302f569b17e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850075"
---
# <a name="error-unable-to-initiate-dcom-communication"></a>Chyba: Nelze inicializovat komunikaci modelu DCOM.
Při místní počítač se pokusil komunikovat se vzdáleným počítačem došlo k chybě modelu DCOM. To je způsobeno brány firewall na vzdálený server nebo porušený ověřování Windows na vzdáleném počítači.

### <a name="to-correct-this-error"></a>Oprava této chyby

- Pokud vzdálený počítač má povolenou bránu Windows Firewall, přečtěte si téma [vzdálené ladění](../debugger/remote-debugging.md) pokyny o tom, jak nakonfigurovat bránu firewall pro místní ladění.

- Chcete-li obnovit ověřování Windows, zkuste restartovat oba počítače. Zkontrolujte protokoly událostí na místních i vzdálených počítačů pro chyby protokolu Kerberos a obraťte se na správce domény pro známé problémy.

## <a name="see-also"></a>Viz také
- [Vzdálené ladění](../debugger/remote-debugging.md)