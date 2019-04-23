---
title: Čas trvání cesty ladění za provozu technologie ASP.NET službě Azure virtual machines
description: Zjistěte, jak zaznamenat a přehrát živých aplikací technologie ASP.NET na Azure virtual machines pomocí ladicího programu snímků.
ms.custom: ''
ms.date: 04/11/2019
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: poppastring
ms.author: madownie
manager: andster
monikerRange: '>= vs-2019'
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 3a81f6aa138b361a44a272ebda3557d27a914c64
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60112349"
---
# <a name="record-and-replay-live-aspnet-apps-on-azure-virtual-machines-using-the-snapshot-debugger"></a>Záznam a přehrávání živých aplikací technologie ASP.NET na Azure virtual machines pomocí ladicího programu snímků

Doba trvání cesty ladění (TTD) ve verzi preview v sadě Visual Studio Enterprise umožňuje zaznamenávat do webové aplikace spuštěné na virtuálním počítači (virtuální počítač Azure) přesně rekonstruovat a opakováním postupu provádění. TTD integruje do ladicího programu snímků a umožňuje rewind a přehrát všech řádků kódu libovolný počet pokusů, které chcete, což pomáhá izolovat a identifikovat problémy, které se můžou vyskytovat jenom v produkčním prostředí.

Zachycení záznamu TTD nebude zastavení aplikace. Záznam TDD však přidá významné režijní náklady do spuštěného procesu zpomalení na základě faktorů, které zahrnují procesu velikost a počet aktivních podprocesů.

Tato funkce je ve verzi preview pro verzi sady Visual Studio 2019 přejděte za licenci.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Spuštění ladicího programu snímků s povoleným laděním doba trvání cesty
> * Nastavte snímkovacího bodu a shromažďování cestovní čas záznamu
> * Spusťte ladění čas cestovní záznam

## <a name="prerequisites"></a>Požadavky

* Doba trvání cesty ladění pro Azure Virtual Machines (VM) je pouze k dispozici pro Visual Studio Enterprise. 2019 nebo vyšší s **funkcí vývoj pro Azure**. (V části **jednotlivé komponenty** kartu, najdete ho pod **ladění a testování** > **Snapshot debugger**.)

    Pokud ještě není nainstalovaný, nainstalujte [Visual Studio Enterprise. 2019](https://visualstudio.microsoft.com/vs/).

* Ladění v době trvání cesty je k dispozici pro následující virtuální počítač Azure web apps:
  * Aplikace technologie ASP.NET (AMD64) v rozhraní .NET Framework 4.8 systému nebo novějším.

## <a name="open-your-project-and-start-the-snapshot-debugger-with-time-travel-debugging-enabled"></a>Otevřete svůj projekt a spusťte ladicí program snímků s povoleným laděním doba trvání cesty

1. Otevřete projekt, pro které chcete shromažďovat čas cestovní záznam.

    > [!IMPORTANT]
    > Pokud chcete začít TTD, budete muset otevřít *stejnou verzi zdrojového kódu* , který je publikován do služby virtuálního počítače Azure.

1. Zvolte **ladit > připojit Snapshot Debugger...** . Vyberte webová aplikace nasazená na virtuálním počítači Azure a účet úložiště Azure. Vyberte **povolit ladění doba trvání cesty** ve verzi preview možnost a potom klikněte na tlačítko **připojit**.

      ![Vyberte prostředek Azure](../debugger/media/time-travel-debugging-select-azure-resource-vm.png)

    > [!IMPORTANT]
    > Při prvním vyberete **připojit Snapshot Debugger** pro váš virtuální počítač automaticky restartuje služba IIS.

    Metadata pro **moduly** není původně aktivovaná. Přejděte do webové aplikace a **spustit shromažďování** tlačítka se pak stane aktivní. Visual Studio je nyní v režimu ladění snímků.

   ![Režim ladění snímků](../debugger/media/snapshot-message.png)

    > [!NOTE]
    > Rozšíření webu Application Insights podporuje také ladění snímků. Pokud narazíte na chybovou zprávu "aktuální rozšíření webu", přečtěte si téma [řešení potíží, tipy a známé problémy pro ladění snímků](../debugger/debug-live-azure-apps-troubleshooting.md) pro upgrade podrobnosti.

   **Moduly** okno zobrazuje, když se načtou všechny moduly pro virtuální počítač Azure (zvolte **ladit > Windows > moduly** otevřete toto okno).

   ![Zkontrolujte okno modulů](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint-and-collect-a-time-travel-recording"></a>Nastavte snímkovacího bodu a shromažďování cestovní čas záznamu

1. V editoru kódu klikněte na levém hřbetu v metodě, která vás zajímají nastavení snímkovacího bodu. Ujistěte se, že je kód, o kterém víte, že se spustí.

   ![Nastavte snímkovacího bodu](../debugger/media/time-travel-debugging-set-snappoint-settings.png)

1. Klikněte pravým tlačítkem na ikonu snímkovací bod (prázdný koule) a zvolte **akce**. V **nastavení snímků** okna, klikněte na tlačítko **akce** zaškrtávací políčko. Klikněte **trasu doba trvání cesty na konec této metody** zaškrtávací políčko.

   ![Shromažďovat trasování doba trvání cesty na konec metody](../debugger/media/time-travel-debugging-set-snappoint-action.png)

1. Klikněte na tlačítko **spustit shromažďování** zapnout snímkovacího bodu.

   ![Zapnout snímkovací bod](../debugger/media/snapshot-start-collection.png)

## <a name="take-a-snapshot"></a>Pořízení snímku

Po zapnutí snímkovacího bodu zaznamená snímek pokaždé, když se spustí na řádek kódu, kde je umístěn snímkovacího bodu. Toto spuštění může být způsobeno skutečné žádosti na serveru. K vynucení vašich snímkovací bod přístupů, přejdete na zobrazení prohlížeče vašeho webu a provádět všechny akce požadované to způsobit vaší snímkovací bod k.

## <a name="start-debugging-a-time-travel-recording"></a>Spusťte ladění čas cestovní záznam

1. Při dosažení snímkovacího bodu, se zobrazí v okně diagnostické nástroje snímku. Chcete-li otevřít toto okno, zvolte **ladit > Windows > zobrazit diagnostické nástroje**.

   ![Otevřete snímkovacího bodu](../debugger/media/snapshot-diagsession-window.png)

1. Klikněte na odkaz zobrazit snímek otevřete čas cestovní nahrávání v editoru kódu.
  
   Každý jednotlivý řádek kódu pomocí něj průběžně zaznamenávají podle TTD můžete spustit **pokračovat** a **Reverse pokračovat** tlačítka. Kromě toho **ladění** nástrojů je možné použít k **zobrazit další příkaz**, **Krokovat s vnořením**, **Krokovat s přeskočením**, **Krokovat s Vystoupením**, **Kroku zpět do**, **krokovat zpět přes**, **kroku zpět**.

   ![Spustit ladění](../debugger/media/time-travel-debugging-step-commands.png)

   Můžete také použít **lokální**, **hodinky**, a **zásobník volání** windows a také vyhodnocujte výrazy.

   ![Kontrolovat data snímku](../debugger/media/time-travel-debugging-start-debugging.png)

    Koncoví uživatelé nejsou ovlivněny kteroukoli následnou aktivitu TTD webem jako takovým je ještě živá. Pouze jeden snímek je ve výchozím nastavení zaznamenávány za snímkovacích bodů: Po zachycení snímku snímkovací bod vypne. Pokud chcete zaznamenat další snímek na snímkovacího bodu, můžete zapnout snímkovací bod zpět kliknutím **aktualizovat shromažďování**.

**Potřebujete pomoc?** Zobrazit [řešení potíží a známé problémy](../debugger/debug-live-azure-apps-troubleshooting.md) a [– nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md) stránky.

## <a name="set-a-conditional-snappoint"></a>Nastavit podmíněné snímkovací bod

Pokud je obtížné znovu vytvořit určitého stavu ve vaší aplikaci, zvažte, zda může pomoci použití podmíněné snímkovacího bodu. Podmíněné snímkovací body umožňují předcházet shromažďování čas cestují, záznamu, dokud aplikace přejde do požadovaného stavu, například pokud má proměnná určitou hodnotu, kterou chcete zkontrolovat. [Můžete nastavit podmínky, které využívají výrazy a filtry, nebo počtu položek](../debugger/debug-live-azure-apps-troubleshooting.md).

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak shromažďovat dobu cesty záznam pro Azure Virtual Machines. Můžete si přečíst další podrobnosti o Snapshot Debugger.

> [!div class="nextstepaction"]
> [Nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md)