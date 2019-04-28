---
title: 'Chyba: Bez ověřování brány firewall | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.firewall.noauth
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
ms.openlocfilehash: 4a72d16869c92b1965fae8db0ae32146a3a57e67
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399210"
---
# <a name="error-firewall-no-authentication"></a>Chyba: Bez ověřování brány firewall
Tuto bránu ve vzdáleném počítači není nastavené pro povolení vzdáleného ladění. Pro vzdálené ladění pomocí `No Authentication`, msvsmon.exe musí být přidán do seznamu výjimek. Některé porty protokolu IPSEC může být nutné také.

> [!NOTE]
> Vzdálený ladicí program je schopen automaticky nastavit bránu Windows Firewall. Při použití brány firewall než Windows Firewall jako brána firewall softwaru třetích stran nebo hardwarové brány firewall, musíte bránu firewall ručně nakonfigurovat pro povolení vzdáleného ladění. Uděláte to tak, umožňují přenosy na portech TCP/IP této msvsmon.exe naslouchá. Ve výchozím nastavení jsou tyto porty 4018 a 4019 4018 se používá ve všech operačních systémech, kde 4019 se používá jenom na Windows x64 pro povolení ladění x86 procesy.

 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).