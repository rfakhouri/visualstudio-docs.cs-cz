---
title: 'Chyba: Bez ověřování brány firewall | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3ad413f3e958fa6dc8edd22ef4be1428b6941bd6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54797498"
---
# <a name="error-firewall-no-authentication"></a>Chyba: Bez ověřování brány firewall
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tuto bránu ve vzdáleném počítači není nastavené pro povolení vzdáleného ladění. Pro vzdálené ladění pomocí `No Authentication`, msvsmon.exe musí být přidán do seznamu výjimek. Některé porty protokolu IPSEC může být nutné také.  
  
> [!NOTE]
>  Vzdálený ladicí program je schopen automaticky nastavit bránu Windows Firewall. Při použití brány firewall než Windows Firewall jako brána firewall softwaru třetích stran nebo hardwarové brány firewall, musíte bránu firewall ručně nakonfigurovat pro povolení vzdáleného ladění. Uděláte to tak, umožňují přenosy na portech TCP/IP této msvsmon.exe naslouchá. Ve výchozím nastavení jsou tyto porty 4018 a 4019 4018 se používá ve všech operačních systémech, kde 4019 se používá jenom na Windows x64 pro povolení ladění x86 procesy.  
  
 Další informace najdete v tématu [nastavit Up the Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).
