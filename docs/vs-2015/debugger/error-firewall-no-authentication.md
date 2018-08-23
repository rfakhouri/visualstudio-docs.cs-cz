---
title: 'Chyba: Bez ověřování brány Firewall | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: dda1acb8-bed7-4bc8-9991-9cdc49c2ac1e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dca0d4421cb8b8b5e720ca079547f13ec75e3705
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42665948"
---
# <a name="error-firewall-no-authentication"></a>Chyba: Bez ověřování brány firewall
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [Chyba: bez ověřování brány Firewall](https://docs.microsoft.com/visualstudio/debugger/error-firewall-no-authentication).  
  
Tuto bránu ve vzdáleném počítači není nastavené pro povolení vzdáleného ladění. Pro vzdálené ladění pomocí `No Authentication`, msvsmon.exe musí být přidán do seznamu výjimek. Některé porty protokolu IPSEC může být nutné také.  
  
> [!NOTE]
>  Vzdálený ladicí program je schopen automaticky nastavit bránu Windows Firewall. Při použití brány firewall než Windows Firewall jako brána firewall softwaru třetích stran nebo hardwarové brány firewall, musíte bránu firewall ručně nakonfigurovat pro povolení vzdáleného ladění. Uděláte to tak, umožňují přenosy na portech TCP/IP této msvsmon.exe naslouchá. Ve výchozím nastavení jsou tyto porty 4018 a 4019 4018 se používá ve všech operačních systémech, kde 4019 se používá jenom na Windows x64 pro povolení ladění x86 procesy.  
  
 Další informace najdete v tématu [nastavit Up the Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).



