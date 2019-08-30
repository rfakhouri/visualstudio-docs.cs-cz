---
title: Ladění živé aplikace Azure technologie ASP.NET
description: Zjistěte, jak nastavit snímkovací body a zobrazit snímky se Snapshot Debugger.
ms.custom: ''
ms.date: 03/16/2018
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 6944c930ba6357fffeebba417a32cd167bd4debd
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70179821"
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>Ladění živé aplikace ASP.NET Azure pomocí ladicího programu snímků

Snapshot Debugger pořídí snímek vaší aplikace do produkčního prostředí, když spustí kód, který vás zajímá. Dáte pokyn, aby ladicí program k vytvoření snímku, můžete nastavit snímkovací a protokolovací body ve vašem kódu. Ladicí program umožňuje zobrazit přesně toho, co nefunguje, aniž by to ovlivnilo provozu aplikace v produkčním prostředí. Snapshot Debugger můžete výrazně zkrátit čas potřebný k vyřešení problémů, ke kterým dochází v produkčním prostředí.

Snímkovací a protokolovací body jsou podobná zarážky, ale na rozdíl od zarážek, není snímkovacích bodů: zastavení aplikace při průchodu. Zachytávání snímků na snímkovacího bodu obvykle trvá 10 20 milisekund.

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Spuštění ladicího programu snímků
> * Nastavení snímkovacího bodu a zobrazení snímku
> * Nastavte protokolovacích bodů:

## <a name="prerequisites"></a>Požadavky

* Snapshot Debugger je k dispozici pouze počínaje verzí Visual Studio 2017 Enterprise verze 15,5 nebo vyšší s **úlohou vývoj pro Azure**. (Na kartě **jednotlivé součásti** najdete v části **ladění a testování** > **snímků – ladicí program**.)

   ::: moniker range=">=vs-2019"
   Pokud ještě není nainstalován, nainstalujte [Visual Studio 2019](https://visualstudio.microsoft.com/downloads). Pokud aktualizujete z předchozí instalace sady Visual Studio, spusťte Instalační program pro Visual Studio a podívejte se na součást Snapshot Debugger v **ASP.NET a vývoji webu**.
   ::: moniker-end
   ::: moniker range="<=vs-2017"
   Pokud ještě není nainstalovaný, nainstalujte [Visual Studio Enterprise 2017 verze 15.5](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) nebo novější. Pokud aktualizujete z předchozí instalace sady Visual Studio 2017, spusťte Instalační program pro Visual Studio a podívejte se na součást Snapshot Debugger v úloze **vývoje ASP.NET a webu**.
   ::: moniker-end

* Plán služby App Service Basic nebo vyšší.

* Shromažďování snímků je k dispozici pro následující web apps ve službě Azure App Service:
  * Aplikace ASP.NET spuštěné na rozhraní .NET Framework 4.6.1 nebo novější.
  * Aplikace ASP.NET Core na .NET Core 2.0 nebo novější na Windows.

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>Otevřete svůj projekt a spusťte ladicí program snímků

1. Otevřete projekt, který chcete snímek ladění.

   > [!IMPORTANT]
   > K ladění snímků, budete muset otevřít *stejnou verzi zdrojového kódu* , který je publikován do služby Azure App Service.

::: moniker range="<=vs-2017"

2. V Průzkumníku cloudu (**zobrazení > Průzkumník cloudu**), klikněte pravým tlačítkem na projekt je nasazen na službě Azure App Service a vyberte **připojit Snapshot Debugger**.

   ![Spuštění ladicího programu snímků](../debugger/media/snapshot-launch.png)

::: moniker-end

::: moniker range=">=vs-2019"

2. Zvolit **ladění > připojit Snapshot Debugger...** . Vyberte Azure App Service projekt je nasazený a účet úložiště Azure a pak klikněte na **připojit**. Snapshot Debugger také podporuje [službu Azure Kubernetes](debug-live-azure-kubernetes.md) a [& Virtual Machine Scale Sets Azure Virtual Machines (VM)](debug-live-azure-virtual-machines.md).

   ![Spuštění Snapshot debuggeru z nabídky ladění](../debugger/media/snapshot-debug-menu-attach.png)

   ![Vybrat prostředek Azure](../debugger/media/snapshot-select-azure-resource-appservices.png)

::: moniker-end

   > [!IMPORTANT]
   > Při prvním vyberete **připojit Snapshot Debugger**, budete vyzváni k instalaci rozšíření webu pro Snapshot Debugger ve službě Azure App Service. Tato instalace vyžaduje restartování služby Azure App Service.

   ::: moniker range="<=vs-2017"
   > [!NOTE]
   > Rozšíření webu Application Insights podporuje také ladění snímků. Pokud se vám zobrazí chybová zpráva "rozšíření webu je zastaralé", přečtěte si téma [tipy pro řešení potíží a známé problémy ladění snímků](../debugger/debug-live-azure-apps-troubleshooting.md) pro upgrade podrobností.
   ::: moniker-end
   ::: moniker range=">=vs-2019"
   > [!NOTE]
   > (Visual Studio 2019 verze 16,2 a vyšší) Snapshot Debugger povolili podporu cloudu Azure. Ujistěte se, že se Váš účet Azure Resource i Azure Storage, který vyberete, nachází ve stejném cloudu. Pokud máte dotazy týkající se konfigurace [dodržování předpisů Azure](https://azure.microsoft.com/overview/trusted-cloud/) v rámci vaší organizace, obraťte se prosím na správce Azure.
   ::: moniker-end

   Visual Studio je nyní v režimu ladění snímků.
   ![Režim ladění snímků](../debugger/media/snapshot-message.png)

   V okně **moduly** se zobrazí, když se všechny moduly načtou pro Azure App Service (pro otevření tohoto okna vyberte **modul ladění > Windows >** ).

   ![Zkontrolujte okno modulů](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>Nastavte snímkovacího bodu

1. V editoru kódu klikněte na levé tlačítko vedle řádku kódu, který vás zajímá, a nastavte snímkovací bod. Ujistěte se, že se jedná o kód, který víte, že se spustí.

   ![Nastavte snímkovacího bodu](../debugger/media/snapshot-set-snappoint.png)

2. Klikněte na tlačítko **spustit shromažďování** zapnout snímkovacího bodu.

   ![Zapnout snímkovací bod](../debugger/media/snapshot-start-collection.png)

   > [!TIP]
   > Nelze krok při zobrazení snímku, ale můžete umístit více snímkovacích bodů: ve vašem kódu sledovat provádění na různé řádky kódu. Pokud máte více snímkovacích bodů: ve vašem kódu, Snapshot Debugger zajišťují, že odpovídající snímky se ze stejné relace koncového uživatele. Snapshot Debugger nepodporuje to i v případě, že existují mnoho uživatelé, kteří vyvolávají vaší aplikace.

## <a name="take-a-snapshot"></a>Pořízení snímku

Jakmile je snímkovací bod nastaveno, můžete buď ručně vygenerovat snímek, a to tak, že v prohlížeči zobrazíte svůj web a spustíte řádek kódu označený nebo počkejte, než vaši uživatelé vygenerují ze svého používání webu.

## <a name="inspect-snapshot-data"></a>Kontrolovat data snímku

1. Při dosažení snímkovacího bodu, se zobrazí v okně diagnostické nástroje snímku. Chcete-li otevřít toto okno, vyberte možnost **ladění > Windows > zobrazit diagnostické nástroje**.

   ![Otevřete snímkovacího bodu](../debugger/media/snapshot-diagsession-window.png)

1. Dvakrát klikněte na panel snímkovacího bodu otevřete snímku v editoru kódu.

   ![Kontrolovat data snímku](../debugger/media/snapshot-inspect-data.png)

   V tomto zobrazení můžete najedete myší proměnné, které chcete zobrazit datové tipy, použijte **lokální**, **hodinky**, a **zásobník volání** windows a také vyhodnocujte výrazy.

   Samotný web je stále živý a koncoví uživatelé to neovlivní. Pouze jeden snímek je ve výchozím nastavení zaznamenávány za snímkovacích bodů: Po zachycení snímku snímkovací bod vypne. Pokud chcete zaznamenat další snímek na snímkovacího bodu, můžete zapnout snímkovací bod zpět kliknutím **aktualizovat shromažďování**.

Můžete také přidat další snímkovací body do vaší aplikace a je zapnout pomocí **aktualizovat shromažďování** tlačítko.

**Potřebujete pomoc?** Zobrazit [řešení potíží a známé problémy](../debugger/debug-live-azure-apps-troubleshooting.md) a [– nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md) stránky.

## <a name="set-a-conditional-snappoint"></a>Nastavit podmíněné snímkovací bod

Pokud je obtížné znovu vytvořit konkrétní stav ve vaší aplikaci, zvažte použití podmíněného snímkovací bod. Podmíněný snímkovací body vám umožňuje řídit, kdy se má pořídit snímek, například když proměnná obsahuje určitou hodnotu, kterou chcete zkontrolovat. Můžete nastavit podmínky, které využívají výrazy a filtry, nebo počtu položek.

#### <a name="to-create-a-conditional-snappoint"></a>Chcete-li vytvořit podmíněného snímkovací bod

1. Klikněte pravým tlačítkem na ikonu snímkovací bod (prázdný koule) a zvolte **nastavení**.

   ![Zvolit nastavení](../debugger/media/snapshot-snappoint-settings.png)

1. V okně Nastavení snímkovací bod zadejte výraz.

   ![Zadejte výraz](../debugger/media/snapshot-snappoint-conditions.png)

   V předchozí ilustraci snímku pouze prováděné na snímkovací bod při `visitor.FirstName == "Dan"`.

## <a name="set-a-logpoint"></a>Nastavte protokolovacích bodů:

Kromě pořízení snímku při dosažení snímkovacího bodu, můžete také nakonfigurovat snímkovací bod k zaznamenání zprávy (to znamená, vytvořit protokolovacích bodů:). Můžete nastavit protokolovací body bez nutnosti nasazení vaší aplikace. Protokolovací body prakticky spustí a způsobit, že žádný dopad nebo vedlejší účinky k běžící aplikaci.

#### <a name="to-create-a-logpoint"></a>Chcete-li vytvořit protokolovacích bodů:

1. Klikněte pravým tlačítkem na ikonu snímkovací bod (modré šestiúhelník) a zvolte **nastavení**.

1. V okně Nastavení snímkovací bod vyberte **akce**.

   ![Vytvoření protokolovacích bodů:](../debugger/media/snapshot-logpoint.png)

1. Do pole **zpráva** můžete zadat novou zprávu protokolu, kterou chcete protokolovat. Můžete také vyhodnotit proměnné ve zprávě protokolu je umístit uvnitř složených závorek.

   Pokud se rozhodnete **odeslat do okna výstup**, když protokolovacích bodů: dosažení, zpráva se zobrazí v okně diagnostické nástroje.

   ![Protokolovací bod data v okně Diagnostické nástroje](../debugger/media/snapshot-logpoint-output.png)

   Pokud se rozhodnete **odeslat do protokolu aplikace**, když protokolovacích bodů: dosažení, zpráva se zobrazí kdekoli, zobrazí se zprávy z `System.Diagnostics.Trace` (nebo `ILogger` v .NET Core), například [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs).

## <a name="next-steps"></a>Další postup

V tomto kurzu jste se naučili, jak používat Snapshot Debugger pro App Services. Můžete chtít přečtěte si další podrobnosti o této funkci.

> [!div class="nextstepaction"]
> [Nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md)