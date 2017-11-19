---
title: "Chyba: Bez ověřování brány Firewall | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.error.firewall.noauth
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1750c0ab8bafe53136d01ba27ada9c242b318c3a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-firewall-no-authentication"></a>Chyba: Bez ověřování brány firewall
Povolit vzdálené ladění není nastavena bránu Firewall ve vzdáleném počítači. Pro vzdálené ladění pomocí `No Authentication`, msvsmon.exe musí být přidaný do seznamu výjimek. Otevírání některé porty protokolu IPSEC může být nutné také.  
  
> [!NOTE]
>  Vzdáleného ladicího programu je možné automaticky konfigurovat bránu Windows Firewall. Pokud používáte jinou bránu firewall než brány Windows Firewall, jako jsou brány firewall třetích stran softwaru nebo hardwaru brána firewall, brány firewall musí ručně nakonfigurovat pro povolení vzdáleného ladění. Uděláte to tak, povolit přenosy na porty TCP/IP, že msvsmon.exe naslouchá na. Ve výchozím nastavení jsou tyto porty 4018 a 4019 4018 se používá na všech operačních systémech, kde 4019 používá pouze v systému Windows x64 k povolení ladění x86 procesy.  
  
 Další informace najdete v tématu [vzdálené ladění](../debugger/remote-debugging.md).