---
title: "Přidání dat interakce vrstev z příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tier interaction profiling method
- profiling tools,tier interaction method
ms.assetid: 5a35647f-03f2-4555-8eeb-fda7e0080e67
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a210ce1f6aeac113033bd82306bb5b682a5e21b9
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="adding-tier-interaction-data-from-the-command-line"></a>Přidání dat interakce vrstev z příkazového řádku
Profilace interakce vrstvy poskytuje další informace o dobu provádění synchronní [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] volání funkcí víceúrovňových aplikací, které komunikují s jednu nebo více databází.  
  
 **Windows 8 a Windows Server 2012**  
  
 Ke shromažďování dat interakce vrstev v aplikacích klasické pracovní plochy Windows 8 a Windows Server 2012 aplikace musíte použít metodu instrumentace. Shromažďování dat interakce vrstev pro aplikace UWP není podporována.  
  
 **Edice Visual Studio**  
  
 Profilování interakce vrstev lze shromažďovat pomocí sady [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)] nebo [!INCLUDE[vs_pro_current_short](../profiling/includes/vs_pro_current_short_md.md)]. Ale dat profilace sledováním interakce vrstev lze zobrazit pouze v [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] a [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)].  
  
 **Shromažďování dat TIP ve vzdáleném počítači**  
  
 Chcete-li shromažďování dat interakce vrstev ve vzdáleném počítači, musíte zkopírovat **vs_profiler_***\<platformy >***_**  *\< Jazyk >***.exe** souboru z *VSInstallDir %***\Team Tools\Performance Tools\Setups** složky počítače Visual Studio vzdálený počítač a nainstalujte ji. Nelze použít v nástroji pro profilaci [vzdálené ladění](../debugger/remote-debugging.md) stažení balíčku.  
  
 **TIP pro sestavy**  
  
 Dat interakce vrstev lze zobrazit pouze v [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)] IDE. Sledováním interakce vrstev založená na souborech sestavy prostřednictvím [vsperfreport –](../profiling/vsperfreport.md) nejsou k dispozici.  
  
## <a name="adding-tier-interaction-data-with-vsperfcmd"></a>Přidání dat interakce vrstev s VSPerfCmd  
 Nástroje příkazového řádku VSPerfASPNETCmd umožňuje přístup k dokončení funkce, která je k dispozici v nástrojích pro profilaci. Chcete-li profilace data shromážděná pomocí VSPerfCmd přidat sledováním interakce vrstev, je nutné použít **vsperfclrenv –** nástroj nastavit a odebrat proměnné prostředí, který umožňuje dat interakce vrstev. Možnosti, které zadáte a postupy potřebných ke shromažďování dat závisí na typu aplikace, která jsou profilace.  
  
### <a name="profiling-stand-alone-applications"></a>Profilace samostatných aplikací  
 Přidání dat interakce vrstev do aplikace, která se nespouští jiným procesem, jako je například aplikace plochy Windows, která umožňuje synchronní [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] pomocí volání do databáze SQL Server, **/InteractionOn vsperfclrenv –** možnost nastavení proměnných prostředí a **vsperfclrenv – /InteractionOff** možnost je odebrat.  
  
 V následujícím příkladu je pomocí metody instrumentace profilovaným desktopová aplikace systému Windows a shromažďovaných dat interakce vrstev.  
  
##### <a name="profiling-a-windows-desktop-application-example"></a>Profilace v příkladu aplikace pracovní plochy Windows  
  
1.  Otevřete okno příkazového řádku s oprávněními správce. Klikněte na tlačítko **spustit**, přejděte na příkaz **všechny programy**a pak přejděte na **Příslušenství**. Klikněte pravým tlačítkem na **příkazového řádku**a potom klikněte na **spustit jako správce**.  
  
2.  Inicializujte profilace rozhraní .NET a proměnných prostředí TIP. Zadejte následující příkazy:  
  
    ```  
    vsperfclrenv /traceon  
    vsperfclrenv /interactionon  
    ```  
  
3.  Spusťte profileru. Zadejte následující příkaz:  
  
    ```  
    vsperfcmd /start:trace /output:Desktop_tip.vsp   
    ```  
  
4.  Spusťte aplikaci s VSPerfCmd. Zadejte následující příkaz:  
  
    ```  
    vsperfcmd /launch:DesktopApp.exe  
    ```  
  
5.  Prověření aplikace shromažďovat data profilování a pak zavřete aplikaci běžným způsobem.  
  
6.  Zrušte zaškrtnutí proměnné prostředí TIP. Zadejte následující příkaz:  
  
    ```  
    vsperfclrenv /off  
    ```  
  
 Další informace najdete v tématu [profilování aplikací samostatné](../profiling/command-line-profiling-of-stand-alone-applications.md).  
  
### <a name="profiling-services"></a>Profilace služeb  
 Do profilu služby, včetně [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace, použijte **vsperfclrenv – /GlobalInteractionOn** možnost nastavení proměnných prostředí a **/GlobalInteractionOff vsperfclrenv –** možnost je odebrat.  
  
 Když jsou profilace služeb, včetně [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webových aplikací, je často potřeba restartovat počítač, aby povolit profilace.  
  
 V následujícím příkladu je pomocí metody instrumenation profilovaným služby systému Windows a shromažďovaných dat interakce vrstev.  
  
##### <a name="profiling-a-windows-service-example"></a>Profilace v příkladu služby systému Windows  
  
1.  V případě potřeby nainstalujte službu.  
  
2.  Otevřete okno příkazového řádku s oprávněními správce. Klikněte na tlačítko **spustit**, přejděte na příkaz **všechny programy**a pak přejděte na **Příslušenství**. Klikněte pravým tlačítkem na **příkazového řádku**a potom klikněte na **spustit jako správce**.  
  
3.  Inicializujte .NET profilace proměnné prostředí. Zadejte následující příkaz:  
  
    ```  
    vsperfclrenv /globaltraceon  
    ```  
  
4.  Inicializace proměnných prostředí TIP. Zadejte následující příkaz  
  
    ```  
    vsperfclrenv /globalinteractionon  
    ```  
  
5.  Restartujte počítač k registraci proměnné prostředí.  
  
6.  Otevřete okno příkazového řádku s oprávněními správce.  
  
7.  Spusťte profileru. Zadejte následující příkaz:  
  
    ```  
    vsperfcmd /start:trace /output:MiddleTier_tip.vsp /user:SYSTEM /crosssession   
    ```  
  
8.  V případě potřeby spusťte službu.  
  
9. Připojení profileru ke službě. Zadejte následující příkaz:  
  
    ```  
    vsperfcmd /attach:MiddleTier.exe /output:MyService_tip.vsp /user:SYSTEM /crosssession   
    ```  
  
10. Vykonává služby a shromažďovat data profilování.  
  
11. Zastavte profileru. Zadejte následující příkaz:  
  
     `vsperfcmd /detach`  
  
12. Vymažte .NET a TIP profilace proměnné prostředí. Zadejte následující příkaz:  
  
    ```  
    vsperfclrenv /globaloff  
    ```  
  
13. Restartujte počítač k registraci proměnné prostředí nezaškrtnuté.  
  
 Další informace naleznete v jednom z následujících témat:  
  
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)  
  
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)  
  
## <a name="adding-tier-interaction-data-with-vsperfaspnetcmd"></a>Přidání dat interakce vrstev pomocí VSPerfASPNETCmd  
 Nástroj příkazového řádku VSPerfASPNETCmd vám umožňuje snadno profil [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Ve srovnání s **VSPerfCmd** nástroj příkazového řádku, jsou omezeny možnosti, musí být nastaveny žádné proměnné prostředí a není vyžadováno restartování počítače. Tyto funkce VSPerfASPNETCmd činí kolekce dat interakce vrstev velmi snadné.  
  
 Pokud chcete přidat na data shromážděná pomocí VSPerfASPNETCmd profilace sledováním interakce vrstev, přidejte **/TIP** možnost příkazového řádku. Například použijte následující příkazový řádek ke shromažďování dat interakce vrstev pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci pomocí metody instrumentace:  
  
```  
vsperfaspnetcmd /tip /trace http://localhost/MyWebApp  
```  
  
 Další informace o VSPerfASPNETCmd najdete v tématu [rychlé profilace webu pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).