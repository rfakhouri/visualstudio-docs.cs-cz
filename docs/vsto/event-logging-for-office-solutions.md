---
title: Protokolování událostí pro řešení pro systém Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], event viewer
- ClickOnce deployment [Office development in Visual Studio], event viewer
- deploying applications [Office development in Visual Studio], event viewer
- Office development in Visual Studio, event viewer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 4b1319e906060a1fe4d94fbd2e6bb0a3f9d53eb9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="event-logging-for-office-solutions"></a>Protokolování události u řešení pro systém Office
  V prohlížeči událostí v systému Windows můžete použít zobrazíte zprávy výjimek, které jsou zachyceny [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] při instalaci nebo odinstalaci řešení Office. Tyto zprávy z protokoly událostí můžete použít k vyřešení instalace a nasazení problémy.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="reading-the-event-log"></a>Čtení protokol událostí  
 Otevřete **Prohlížeč událostí** a filtr pro události, které chcete zobrazit.  
  
#### <a name="to-read-the-event-log-in-windows-server-2003-and-windows-xp"></a>Ke čtení protokol událostí v systému Windows Server 2003 a Windows XP  
  
1.  V Ovládacích panelech otevřete **nástroje pro správu**.  
  
2.  Spustit **Prohlížeč událostí**.  
  
3.  V seznamu protokolů událostí, vyberte **aplikace**.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **filtru**.  
  
5.  V **zdroj události** seznamu, vyberte **VSTO 4.0**.  
  
6.  Pro instalaci události v **ID události** zadejte **4096**.  
  
7.  Klikněte na tlačítko **OK** zobrazíte filtrované zobrazení.  
  
#### <a name="to-read-the-event-log-in-windows-7-windows-vista-and-windows-server-2008"></a>Ke čtení protokol událostí ve Windows 7, Windows Vista a Windows Server 2008  
  
1.  V Ovládacích panelech otevřete **nástroje pro správu**.  
  
2.  Spustit **Prohlížeč událostí**.  
  
3.  Rozbalte položku **protokoly systému Windows**.  
  
4.  V seznamu protokolů událostí, vyberte **aplikace**.  
  
5.  Na **akce** nabídky, klikněte na tlačítko **filtrovat aktuální protokol**.  
  
6.  V **zdroj události** seznamu, vyberte **VSTO 4.0**.  
  
7.  Pro instalaci události v **ID události** zadejte **4096**.  
  
8.  Klikněte na tlačítko **OK** zobrazíte filtrované zobrazení.  
  
 V prohlížeči událostí obsahuje následující informace:  
  
-   Umístění manifestu nasazení řešení.  
  
-   Zpráva, která popisuje příčinou chyby nebo výjimky.  
  
 Tyto zprávy o výjimkách můžete zjistit, proč pro problém s instalací, například nedůvěryhodný certifikát, umístění služby nedůvěryhodné dokumentu nebo manifest nasazení je neplatná.  
  
 Po odinstalaci řešení Office zprávy výjimek zůstat v protokolu událostí.  
  
 Pokud chcete zobrazit nebo protokolu zprávy o výjimkách, když běží řešení Office, najdete v části [ladění projektů Office](../vsto/debugging-office-projects.md) a [ladění projektů Office](../vsto/debugging-office-projects.md).  
  
### <a name="localization"></a>Lokalizace  
 Jazyk zpráva o výjimce je určen podle sady Visual Studio Tools for Office runtime language. Například pokud má počítač koncový uživatel japonská jazyková sada nainstalovaná, zpráva o výjimce se zapíšou do protokolu událostí v japonštině.  
  
## <a name="disabling-the-event-logger"></a>Zakázání protokolování událostí  
 Ve výchozím nastavení je protokolování událostí povolené při instalaci nebo odinstalaci řešení pro systém Office. Protokoly událostí můžete zakázat nastavením proměnné prostředí VSTO_EVENTLOGDISABLED "1" (jedna).  
  
#### <a name="to-disable-the-event-log"></a>Chcete-li zakázat protokol událostí  
  
1.  V Ovládacích panelech otevřete **systému**.  
  
2.  Na **Upřesnit** , klikněte na **proměnné prostředí**.  
  
3.  V **systémové proměnné** podokně klikněte na tlačítko **nový**.  
  
4.  V **Nová proměnná systému** dialogové okno, typ **VSTO_EVENTLOGDISABLED** v **název proměnné** pole.  
  
5.  V **hodnota proměnné** zadejte **1**.  
  
6.  Click **OK**.  
  
## <a name="see-also"></a>Viz také  
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)   
 [Řešení potíží s nasazením řešení pro systém Office](../vsto/troubleshooting-office-solution-deployment.md)  
  
  