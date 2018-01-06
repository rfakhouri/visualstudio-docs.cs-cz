---
title: "Přiřazení portů vzdáleného ladicího programu | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 05/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 238bb4ec-bb00-4c2b-986e-18ac278f3959
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c541922ac18c28e085db37b6ac9fa9349adbeb9b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="remote-debugger-port-assignments"></a>Přiřazení portů vzdáleného ladicího programu
Visual Studio Debugger vzdálené můžete spustit jako aplikace nebo služba pozadí. Když je spuštěna jako aplikace, používá port, který je přiřazen ve výchozím nastavení následujícím způsobem:  

-   Visual Studio 2017:4022

-   Visual Studio 2015:4020  
  
-   Visual Studio 2013:4018  
  
-   Visual Studio 2012:4016  
  
 Jinými slovy číslo portu přiřazené vzdáleného ladicího programu se zvýší 2 pro jednotlivé verze. Můžete nastavit jiný port číslo vám líbilo. Bude vám vysvětlíme, jak nastavit čísla portů v další části.  
  
## <a name="the-remote-debugger-port-on-32-bit-operating-systems"></a>Port vzdáleného ladicího programu na 32bitové operační systémy  
 TCP 4022 (v aplikaci Visual Studio 2017) je hlavní portu a musí se pro všechny scénáře. To můžete nakonfigurovat z příkazového řádku nebo okna vzdáleného ladicího programu.  
  
 V okně vzdáleného ladicího programu, klikněte na **nástroje > Možnosti**a nastavte číslo portu TCP/IP.  
  
 Na příkazovém řádku spusťte vzdáleného ladicího programu s **/port** přepínač: **/msvsmon port \<číslo portu >**.  
  
 Můžete najít všechny vzdáleného ladicího programu spínačů příkazového řádku v vzdáleného ladění nápovědy (stiskněte **F1** nebo klikněte na tlačítko **pomoci > využití** v okně vzdáleného ladicího programu).  
  
## <a name="the-remote-debugger-port-on-64-bit-operating-systems"></a>Port vzdáleného ladicího programu na 64bitové operační systémy  
 Při spuštění 64bitové verze vzdáleného ladicího programu, ve výchozím nastavení používá 4022 port.  Pokud ladíte 32bitový proces, spustí 64bitové verze vzdáleného ladicího programu na portu 4023 32bitovou verzi vzdáleného ladicího programu. Pokud spouštíte 32bitovou vzdáleného ladicího programu, používá 4022 a 4023 nepoužívá.  
  
 Tento port je možné konfigurovat z příkazového řádku: **Msvsmon /wow64port \<číslo portu >**.  
  
## <a name="the-discovery-port"></a>Port zjišťování  
 UDP 3702 se používá pro hledání spuštěné instance vzdáleného ladicího programu v síti (například **najít** dialogové okno ve **připojit k procesu** dialogové okno). Používá se pouze pro zjišťování počítač se systémem vzdáleného ladicího programu, takže je volitelné, pokud máte nějaké další způsob, jak zjistit název počítače nebo IP adresu cílového počítače. Toto je standardní port pro zjišťování, takže nelze konfigurovat číslo portu.  
  
 Pokud nechcete povolit zjišťování, můžete spustit msvsmon z příkazového řádku se zjišťováním zakázáno: **Msvsmon /nodiscovery**.  
  
## <a name="remote-debugger-ports-on-azure"></a>Porty vzdáleného ladicího programu v Azure  
 Používá následující porty vzdáleného ladicího programu v Azure. Porty cloudové služby jsou mapovány na porty pro jednotlivé virtuální počítač. Jsou všechny porty TCP.  
  
||||  
|-|-|-|  
|**Připojení**|**Port v cloudové službě**|**Port ve virtuálním počítači**|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Connector|30400|30398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.Forwarder|31400|31398|  
|Microsoft.WindowsAzure.Plugins.RemoteDebugger.FileUpload|32400|32398|  
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění](../debugger/remote-debugging.md)