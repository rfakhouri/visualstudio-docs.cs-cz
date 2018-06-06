---
title: Přidání dat interakce vrstev z příkazového řádku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- tier interaction profiling method
- profiling tools,tier interaction method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8dfa0f5b35ec5f5f3e68955d3768da9530000319
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34548658"
---
# <a name="add-tier-interaction-data-from-the-command-line"></a>Přidání dat interakce vrstev z příkazového řádku

Profilace interakce vrstvy poskytuje další informace o dobu provádění synchronní [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] volání funkcí víceúrovňových aplikací, které komunikují s jednu nebo více databází.

**Windows 8 a Windows Server 2012**

Ke shromažďování dat interakce vrstev v aplikacích klasické pracovní plochy Windows 8 a Windows Server 2012 aplikace musíte použít metodu instrumentace. Shromažďování dat interakce vrstev pro aplikace UWP není podporována.

**Edice Visual Studio**

Profilace interakce vrstvy můžete shromáždit pomocí libovolná edice sady Visual Studio. Data profilace sledováním interakce vrstev však lze zobrazit pouze ve Visual Studio Enterprise.

**Shromažďování dat TIP ve vzdáleném počítači**

Shromažďování dat interakce vrstev ve vzdáleném počítači, je nutné zkopírovat **vs_profiler_***\<platformy >***_***\<jazyk >***.exe** souboru z *%VSInstallDir%***\Team nástroje Tools\Setups** složky sady Visual Studio počítač ke vzdálenému počítači a nainstalujte ji. Nelze použít v nástroji pro profilaci [vzdálené ladění](../debugger/remote-debugging.md) stažení balíčku.

**TIP pro sestavy**

Dat interakce vrstev lze zobrazit pouze ve Visual Studio Enterprise. Sledováním interakce vrstev založená na souborech sestavy prostřednictvím [vsperfreport –](../profiling/vsperfreport.md) nejsou k dispozici.

## <a name="add-tier-interaction-data-with-vsperfcmd"></a>Přidání dat interakce vrstev s VSPerfCmd

Nástroje příkazového řádku VSPerfASPNETCmd umožňuje přístup k dokončení funkce, která je k dispozici v nástrojích pro profilaci. Chcete-li profilace data shromážděná pomocí VSPerfCmd přidat sledováním interakce vrstev, je nutné použít **vsperfclrenv –** nástroj nastavit a odebrat proměnné prostředí, který umožňuje dat interakce vrstev. Možnosti, které zadáte a postupy potřebných ke shromažďování dat závisí na typu aplikace, která jsou profilace.

## <a name="profile-stand-alone-applications"></a>Profil samostatných aplikací

Přidání dat interakce vrstev do aplikace, která se nespouští jiným procesem, jako je například aplikace plochy Windows, která umožňuje synchronní [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)] pomocí volání do databáze SQL Server, **/InteractionOn vsperfclrenv –** možnost nastavení proměnných prostředí a **vsperfclrenv – /InteractionOff** možnost je odebrat.

V následujícím příkladu je pomocí metody instrumentace profilovaným desktopová aplikace systému Windows a shromažďovaných dat interakce vrstev.

### <a name="profile-a-windows-desktop-application-example"></a>Profil v příkladu aplikace pracovní plochy Windows

1. Otevřete okno příkazového řádku s oprávněními správce. Klikněte na tlačítko **spustit**, přejděte na příkaz **všechny programy**a pak přejděte na **Příslušenství**. Klikněte pravým tlačítkem na **příkazového řádku**a potom klikněte na **spustit jako správce**.

2. Inicializujte profilace rozhraní .NET a proměnných prostředí TIP. Zadejte následující příkazy:

    ```cmd
    vsperfclrenv /traceon
    vsperfclrenv /interactionon
    ```

3. Spusťte profileru. Zadejte následující příkaz:

    ```cmd
    vsperfcmd /start:trace /output:Desktop_tip.vsp 
    ```

4. Spusťte aplikaci s VSPerfCmd. Zadejte následující příkaz:

    ```cmd
    vsperfcmd /launch:DesktopApp.exe
    ```

5. Prověření aplikace shromažďovat data profilování a pak zavřete aplikaci běžným způsobem.

6. Zrušte zaškrtnutí proměnné prostředí TIP. Zadejte následující příkaz:

    ```cmd
    vsperfclrenv /off
    ```

Další informace najdete v tématu [profilu samostatné aplikace](../profiling/command-line-profiling-of-stand-alone-applications.md).

## <a name="profile-services"></a>Profil služby

Do profilu služby, včetně [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace, použijte **vsperfclrenv – /GlobalInteractionOn** možnost nastavení proměnných prostředí a **/GlobalInteractionOff vsperfclrenv –** možnost je odebrat.

Když jsou profilace služeb, včetně [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webových aplikací, je často potřeba restartovat počítač, aby povolit profilace.

V následujícím příkladu služby systému Windows je profilovaným pomocí metody instrumentace a shromažďovaných dat interakce vrstev.

### <a name="profile-a-windows-service-example"></a>Profil v příkladu služby systému Windows

1. V případě potřeby nainstalujte službu.

2. Otevřete okno příkazového řádku s oprávněními správce. Klikněte na tlačítko **spustit**, přejděte na příkaz **všechny programy**a pak přejděte na **Příslušenství**. Klikněte pravým tlačítkem na **příkazového řádku**a potom klikněte na **spustit jako správce**.

3. Inicializujte .NET profilace proměnné prostředí. Zadejte následující příkaz:

    ```cmd
    vsperfclrenv /globaltraceon
    ```

4. Inicializace proměnných prostředí TIP. Zadejte následující příkaz:

    ```cmd
    vsperfclrenv /globalinteractionon
    ```

5. Restartujte počítač k registraci proměnné prostředí.

6. Otevřete okno příkazového řádku s oprávněními správce.

7. Spusťte profileru. Zadejte následující příkaz:

    ```cmd
    vsperfcmd /start:trace /output:MiddleTier_tip.vsp /user:SYSTEM /crosssession 
    ```

8. V případě potřeby spusťte službu.

9. Připojení profileru ke službě. Zadejte následující příkaz:

    ```cmd
    vsperfcmd /attach:MiddleTier.exe /output:MyService_tip.vsp /user:SYSTEM /crosssession 
    ```

10. Vykonává služby a shromažďovat data profilování.

11. Zastavte profileru. Zadejte následující příkaz:

     `vsperfcmd /detach`

12. Vymažte .NET a TIP profilace proměnné prostředí. Zadejte následující příkaz:

    ```cmd
    vsperfclrenv /globaloff
    ```

13. Restartujte počítač k registraci proměnné prostředí nezaškrtnuté.

Další informace naleznete v jednom z následujících témat:

[Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)

[Profil služby](../profiling/command-line-profiling-of-services.md)

## <a name="add-tier-interaction-data-with-vsperfaspnetcmd"></a>Přidání dat interakce vrstev pomocí VSPerfASPNETCmd

Nástroj příkazového řádku VSPerfASPNETCmd vám umožňuje snadno profil [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Ve srovnání s **VSPerfCmd** nástroj příkazového řádku, jsou omezeny možnosti, musí být nastaveny žádné proměnné prostředí a není vyžadováno restartování počítače. Tyto funkce VSPerfASPNETCmd činí kolekce dat interakce vrstev velmi snadné.

Pokud chcete přidat na data shromážděná pomocí VSPerfASPNETCmd profilace sledováním interakce vrstev, přidejte **/TIP** možnost příkazového řádku. Například použijte následující příkazový řádek ke shromažďování dat interakce vrstev pro [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci pomocí metody instrumentace:

```cmd
vsperfaspnetcmd /tip /trace http://localhost/MyWebApp
```

Další informace o VSPerfASPNETCmd najdete v tématu [profilace rychlé webové stránky pomocí VSPerfASPNETCmd](../profiling/rapid-web-site-profiling-with-vsperfaspnetcmd.md).