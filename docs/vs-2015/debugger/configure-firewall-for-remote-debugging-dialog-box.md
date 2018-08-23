---
title: Konfigurace brány Firewall pro vzdálené ladění, dialogové okno | Dokumentace Microsoftu
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
- vs.debug.firewallconfiguration
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
helpviewer_keywords:
- Configure Firewall for Remote Debugging dialog box
- remote debugging, configuring firewalls
- firewalls, configuring for remote debugging
ms.assetid: 5dff3393-fdeb-4129-a2f6-31f653107a82
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 26e53e4573de1fb80d33b387e97b6ddd23b54bbb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675729"
---
# <a name="configure-firewall-for-remote-debugging-dialog-box"></a>Dialogové okno Konfigurace brány firewall pro vzdálené ladění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [konfigurace brány Firewall pro vzdálené ladění – dialogové](https://docs.microsoft.com/visualstudio/debugger/configure-firewall-for-remote-debugging-dialog-box).  
  
Toto dialogové okno se zobrazí, když brána Windows Firewall blokuje ladicí program příjem informací v síti. Chcete-li pokračovat, vzdálené ladění, je nutné otevřít díry v bráně firewall tak, že ladicí program může přijímat informace.  
  
> [!CAUTION]
>  Otevírání díry v bráně Firewall může vystavit bezpečnostní hrozby, které brána Firewall je navržená tak, aby blokovat v počítači. Otevírání riziko pro vzdálené ladění odblokuje porty 4020 a 4021 v sadě Visual Studio 2015. V jiných verzích sady Visual Studio se používají jiné čísla portů. Další informace najdete v tématu [přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md). Kromě toho umožňuje ladicí program otevřete další porty. Další informace najdete v tématu [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Zrušit vzdálené ladění**  
 Zruší požadavek na vzdáleného ladění. Nastavení zabezpečení vašeho počítače zůstávají beze změn.  
  
 **Odblokovat vzdálené ladění z počítačů v místní síti (podsíti)**  
 Umožňuje vzdálené ladění z počítačů ve vaší místní podsíti. Otevře ohrožení zabezpečení na počítače v místní podsíti, ale stále blokovat informace pocházející z mimo podsíť brány.  
  
 **Odblokovat vzdálené ladění z libovolného počítače**  
 Umožňuje vzdálené ladění počítače kdekoli v síti. Toto nastavení je nejméně bezpečná.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Nastavení nástroje Remote Tools na zařízení](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c)   
 [Ladění odkazu uživatelského rozhraní](../debugger/debugging-user-interface-reference.md)



