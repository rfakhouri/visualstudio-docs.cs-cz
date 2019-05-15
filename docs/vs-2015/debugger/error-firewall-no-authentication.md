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
ms.openlocfilehash: db13165c584399952dc491cf714ac84ee4de7598
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697430"
---
# <a name="error-firewall-no-authentication"></a>Chyba: Bez ověřování brány firewall
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tuto bránu ve vzdáleném počítači není nastavené pro povolení vzdáleného ladění. Pro vzdálené ladění pomocí `No Authentication`, msvsmon.exe musí být přidán do seznamu výjimek. Některé porty protokolu IPSEC může být nutné také.  
  
> [!NOTE]
> Vzdálený ladicí program je schopen automaticky nastavit bránu Windows Firewall. Při použití brány firewall než Windows Firewall jako brána firewall softwaru třetích stran nebo hardwarové brány firewall, musíte bránu firewall ručně nakonfigurovat pro povolení vzdáleného ladění. Uděláte to tak, umožňují přenosy na portech TCP/IP této msvsmon.exe naslouchá. Ve výchozím nastavení jsou tyto porty 4018 a 4019 4018 se používá ve všech operačních systémech, kde 4019 se používá jenom na Windows x64 pro povolení ladění x86 procesy.  
  
 Další informace najdete v tématu [nastavit Up the Remote Tools na zařízení](https://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).
