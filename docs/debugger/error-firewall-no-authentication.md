---
title: 'Chyba: Bez ověřování brány Firewall | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6a6a15196445555e883ebc76541f486d7de454b8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="error-firewall-no-authentication"></a>Chyba: Bez ověřování brány firewall
Povolit vzdálené ladění není nastavena bránu Firewall ve vzdáleném počítači. Pro vzdálené ladění pomocí `No Authentication`, msvsmon.exe musí být přidaný do seznamu výjimek. Otevírání některé porty protokolu IPSEC může být nutné také.  
  
> [!NOTE]
>  Vzdáleného ladicího programu je možné automaticky konfigurovat bránu Windows Firewall. Pokud používáte jinou bránu firewall než brány Windows Firewall, jako jsou brány firewall třetích stran softwaru nebo hardwaru brána firewall, brány firewall musí ručně nakonfigurovat pro povolení vzdáleného ladění. Uděláte to tak, povolit přenosy na porty TCP/IP, že msvsmon.exe naslouchá na. Ve výchozím nastavení jsou tyto porty 4018 a 4019 4018 se používá na všech operačních systémech, kde 4019 používá pouze v systému Windows x64 k povolení ladění x86 procesy.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).