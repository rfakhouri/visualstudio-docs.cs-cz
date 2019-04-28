---
title: Konfigurace brány Firewall pro vzdálené ladění, dialogové okno | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
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
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 91b0d7ee490b4e081a264c41b4fe85de07cb637b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63437811"
---
# <a name="configure-firewall-for-remote-debugging-dialog-box"></a>Dialogové okno Konfigurace brány firewall pro vzdálené ladění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto dialogové okno se zobrazí, když brána Windows Firewall blokuje ladicí program příjem informací v síti. Chcete-li pokračovat, vzdálené ladění, je nutné otevřít díry v bráně firewall tak, že ladicí program může přijímat informace.  
  
> [!CAUTION]
> Otevírání díry v bráně Firewall může vystavit bezpečnostní hrozby, které brána Firewall je navržená tak, aby blokovat v počítači. Otevírání riziko pro vzdálené ladění odblokuje porty 4020 a 4021 v sadě Visual Studio 2015. V jiných verzích sady Visual Studio se používají jiné čísla portů. Další informace najdete v tématu [přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md). Kromě toho umožňuje ladicí program otevřete další porty. Další informace najdete v tématu [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).  
  
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
