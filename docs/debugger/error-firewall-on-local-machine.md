---
title: 'Chyba: Brána firewall v místním počítači | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.firewall.localmachine
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
ms.openlocfilehash: 1781fef79dc9d80bae6a0484788298324e8bbd52
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54963733"
---
# <a name="error-firewall-on-local-machine"></a>Chyba: Brána firewall v místním počítači
Bránu na místním počítači, počítač, na kterém běží Visual Studio, není nastavené pro povolení vzdáleného ladění. Spravované nebo nativní vzdáleného ladění s výchozí spojení, musíte otevřít port TCP 135 DCOM provoz. Musí být otevřeny sdílení souborů a tiskáren a devenv.exe musí být přidán do seznamu výjimek. Některé porty protokolu IPSEC může být nutné také.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).