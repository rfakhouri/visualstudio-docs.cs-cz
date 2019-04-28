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
ms.openlocfilehash: 87a1813410a092ced335f37b9df4cf6547ca1cc3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851042"
---
# <a name="error-firewall-on-local-machine"></a>Chyba: Brána firewall v místním počítači
Bránu na místním počítači, počítač, na kterém běží Visual Studio, není nastavené pro povolení vzdáleného ladění. Spravované nebo nativní vzdáleného ladění s výchozí spojení, musíte otevřít port TCP 135 DCOM provoz. Musí být otevřeny sdílení souborů a tiskáren a devenv.exe musí být přidán do seznamu výjimek. Některé porty protokolu IPSEC může být nutné také.

 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).