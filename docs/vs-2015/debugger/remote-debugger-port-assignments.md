---
title: Přiřazení portů vzdáleného ladicího programu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e44169c436eb3a164a418413341c1689b37a649f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669399"
---
# <a name="remote-debugger-port-assignments"></a>Přiřazení portů vzdáleného ladicího programu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [přiřazení portů vzdáleného ladicího programu](https://docs.microsoft.com/visualstudio/debugger/remote-debugger-port-assignments).  
  
Visual Studio Remote Debugger může běžet jako aplikace nebo jako službu na pozadí. Při spuštění jako aplikace, používá port, který je přiřazen ve výchozím nastavení následujícím způsobem:  
  
-   Visual Studio 2015:4020  
  
-   Visual Studio 2013:4018  
  
-   Visual Studio 2012:4016  
  
 Jinými slovy číslo portu přiřazené vzdálený ladicí program je zvýšen o 2 pro každou vydanou verzí. Můžete nastavit jiné číslo portu, jako je. Vysvětlíme, jak nastavit čísla portů v další části.  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>Portu vzdáleného ladicího programu na 32bitové operační systémy  
 4020 TCP (ve Visual Studiu 2015) je hlavní port a pro všechny scénáře se vyžaduje. To můžete nakonfigurovat z příkazového řádku nebo v okně vzdáleného ladicího programu.  
  
 V okně vzdáleného ladicího programu klikněte na tlačítko **Nástroje / možnosti**a nastavte číslo portu TCP/IP.  
  
 Na příkazovém řádku spustit vzdálený ladicí program se **portu/** přepnout: **msvsmon/port \<číslo portu >**.  
  
 Můžete najít vzdálený ladicí program přepínače příkazového řádku v nápovědě vzdáleného ladění (stisknutím klávesy **F1** nebo klikněte na tlačítko **Nápověda / využití** v okně vzdáleného ladicího programu).  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>Portu vzdáleného ladicího programu na 64bitové operační systémy  
 Při spuštění 64bitovou verzi vzdáleného ladicího programu, ve výchozím nastavení používá 4020 port.  Pokud ladíte 32bitový proces, spustí 64bitovou verzi vzdáleného ladicího programu na portu 4021 32bitovou verzi vzdáleného ladicího programu. Při spuštění vzdáleného ladicího programu 32-bit, používá 4020 a 4021 nepoužívá.  
  
 Tento port jde nakonfigurovat z příkazového řádku: **Msvsmon/wow64port \<číslo portu >**.  
  
## <a name="the-discovery-port"></a>Port zjišťování  
 UDP 3702 slouží k vyhledání spuštěné instance vzdáleného ladícího programu v síti (například **najít** dialogového okna v **připojit k procesu** dialogového okna). Používá se pouze pro zjišťování počítači se systémem vzdálený ladicí program, takže je volitelný, pokud máte nějaké další způsob, jak zjistit název počítače nebo IP adresu cílového počítače. Jedná se standardním portem pro zjišťování, proto není možné nakonfigurovat číslo portu.  
  
 Pokud nechcete povolit zjišťování, můžete spustit msvsmon z příkazového řádku se zjišťováním zakázané: **Msvsmon /nodiscovery**.  
  
## <a name="remote-debugger-ports-on-azure"></a>Porty vzdálené ladicí program v Azure  
 Vzdálený ladicí program v Azure používá následující porty. Porty v cloudové službě jsou mapovány na porty konkrétního virtuálního počítače. Jsou všechny porty TCP.  
  
||||  
|-|-|-|  
|**připojení**|**Port v cloudové službě**|**Port ve virtuálním počítači**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)



