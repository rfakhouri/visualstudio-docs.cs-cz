---
title: Konfigurace brány Firewall pro vzdálené ladění, dialogové okno | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.firewallconfiguration
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- Configure Firewall for Remote Debugging dialog box
- remote debugging, configuring firewalls
- firewalls, configuring for remote debugging
ms.assetid: 5dff3393-fdeb-4129-a2f6-31f653107a82
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f4a7346d9398ab9743319661efffdaf3f1f4b89b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55018602"
---
# <a name="configure-firewall-for-remote-debugging-dialog-box"></a>Dialogové okno Konfigurace brány firewall pro vzdálené ladění
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
 [Vzdálené ladění](../debugger/remote-debugging.md)  
 [Ladění odkazu uživatelského rozhraní](../debugger/debugging-user-interface-reference.md)