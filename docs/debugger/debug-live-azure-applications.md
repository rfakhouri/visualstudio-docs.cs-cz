---
title: Ladění aplikací za provozu ASP.NET Azure
ms.description: Learn how to set snappoints and view snapshots with the Snapshot Debugger.
ms.custom: mvc
ms.date: 03/16/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- azure
ms.openlocfilehash: c576795a130b6e654310a9ad48381fdc6a23c0e2
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766321"
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>Ladění za provozu aplikací ASP.NET Azure pomocí snímku ladicí program

Ladicí program snímku pořídí snímek aplikací v provozním, když provede kód, který vás zajímá. Dáte pokyn, aby ladicí program na pořízení snímku, nastavte snappoints a logpoints ve vašem kódu. Ladicí program umožňuje zobrazit přesně kde došlo k chybě, bez vlivu na provoz produkční aplikace. Ladicí program snímku můžete výrazně zkrátit dobu potřebnou k vyřešení problémů, ke kterým došlo v produkčním prostředí.

Snappoints a logpoints jsou podobná zarážky, ale na rozdíl od zarážky, nemusíte snappoints zastavení aplikace při průchodu. Pořízením na snappoint obvykle trvá 10 20 milisekund. 

V tomto kurzu se naučíte:

> [!div class="checklist"]
> * Spuštění ladicího programu snímku
> * Nastavení snappoint a zobrazení snímku
> * Nastavte logpoint

## <a name="prerequisites"></a>Požadavky

* Ladicí program snímku je dostupná jenom pro Visual Studio Enterprise 2017 verze 15,5 nebo vyšší s **ASP.NET a webové úlohy vývoj**. Pro ASP.NET Core, musíte taky. **NET základní vývoj** zatížení nainstalována.

    Pokud ještě není nainstalovaný, nainstalujte [Visual Studio Enterprise 2017 verze 15,5](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) nebo novější. Při aktualizaci z předchozí instalace Visual Studio 2017, spusťte instalační program Visual Studio a změnami komponentu snímku ladicí program **ASP.NET a webové úlohy vývoj**.

* Plán aplikační služby Azure základní nebo vyšší.

* Snímek kolekce je k dispozici pro následující webové aplikace běžící v Azure App Service:

    * Aplikace ASP.NET spuštěné na rozhraní .NET Framework 4.6.1 nebo novější.
    * ASP.NET Core aplikací běžících na .NET Core 2.0 nebo novější na systému Windows.

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>Otevřete projekt a spusťte snímek ladicí program

1. Otevřete projekt, který chcete snímek ladění. 

    > [!IMPORTANT] 
    > K ladění snímek, budete muset otevřít **stejnou verzi zdrojový kód** je publikována ve službě Azure App Service. 

1. V Průzkumníku cloudu (**zobrazení > Průzkumník cloudu**), klikněte pravým tlačítkem na projekt se nasadí do služby Azure App Service a vyberte **připojit ladicí program snímku**.

   ![Spuštění ladicího programu snímku](../debugger/media/snapshot-launch.png)

    Při prvním vyberete **připojit ladicí program snímku**, se zobrazí výzva k instalaci rozšíření lokality snímku ladicí program na Azure App Service. Tato instalace vyžaduje restart služby Azure App Service. 

   Visual Studio je nyní v režimu ladění snímek.

    > [!NOTE]
    > Rozšíření lokality služby Application Insights podporuje také ladění snímku. Pokud narazíte na chybová zpráva "lokality rozšíření zastaralá", přečtěte si téma [řešení potíží s tipy a známé problémy pro ladění snímku](../debugger/debug-live-azure-apps-troubleshooting.md) pro upgrade podrobnosti.

   ![Režim ladění snímku](../debugger/media/snapshot-message.png)

   **Moduly** okno zobrazí, když mají všechny moduly načten pro Azure App Service (zvolte **ladění / Windows / moduly** otevřete toto okno).

   ![Zkontrolujte okna moduly](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>Nastavte snappoint

1. V editoru kódu klikněte na levém oddělovací mezery u řádek kódu, které vás zajímají nastavení snappoint. Ujistěte se, že je kód, který znáte, budou spuštěny.

   ![Nastavte snappoint](../debugger/media/snapshot-set-snappoint.png)

2. Klikněte na tlačítko **Start Collection** zapnout snappoint.  

   ![Zapnout snappoint](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > Nelze krok při zobrazení snímku, ale můžete umístit více snappoints ve vašem kódu provést spuštění na různé řádky kódu. Pokud máte více snappoints ve vašem kódu, ladicího programu snímku zajišťuje, že odpovídající snímky jsou ze stejné relace koncového uživatele. Ladicí program snímku tomu i v případě, že existuje mnoho uživatelů stiskne vaší aplikace.

## <a name="take-a-snapshot"></a>Pořízení snímku

Když je zapnutý snappoint, bude zachytit snímek, při každém řádku kódu, kde je umístěn snappoint provede. Spuštění tohoto může být způsobeno skutečné žádosti na vašem serveru. Chcete-li vynutit vaší snappoint přístupů, přejděte do zobrazení prohlížeče vašeho webu a provádět žádné akce požadované které způsobit vaší snappoint být narazí.

## <a name="inspect-snapshot-data"></a>Zkontrolujte data snímku

1. Když je dosaženo snappoint, se zobrazí v okně diagnostické nástroje snímek. Chcete-li otevřít toto okno, zvolte **ladění / Windows / zobrazit diagnostické nástroje**.

   ![Otevřete snappoint](../debugger/media/snapshot-diagsession-window.png)

1. Dvakrát klikněte na snappoint otevřete snímku v editoru kódu.

   ![Zkontrolujte data snímku](../debugger/media/snapshot-inspect-data.png)

   Z tohoto hlediska můžete podržet přes proměnné, které chcete zobrazit datatips –, použijte **místní hodnoty –**, **sleduje**, a **zásobníkem volání** windows a také vyhodnocení výrazů.

    Web, samotné stále za provozu a nejsou dopad na koncové uživatele. Pouze jeden snímek pořízen za snappoint ve výchozím nastavení: Po zachycení snímku snappoint vypne. Pokud chcete zaznamenat jiného snímku na snappoint, můžete zapnout snappoint zpět na kliknutím **aktualizace kolekce**.

Můžete také přidat další snappoints do vaší aplikace a je zapnout pomocí **aktualizace kolekce** tlačítko.

**Potřebujete pomoc?** Najdete v článku [řešení potíží a známé problémy](../debugger/debug-live-azure-apps-troubleshooting.md) a [– nejčastější dotazy k ladění snímku](../debugger/debug-live-azure-apps-faq.md) stránky.

## <a name="set-a-conditional-snappoint"></a>Nastavit podmíněný snappoint

Pokud je obtížné znovu vytvořit konkrétní stav ve vaší aplikaci, zvažte, zda může pomoci použití podmíněného snappoint. Podmíněné snappoints vyhnuli se vytvoření snímku, dokud aplikace vstupuje do požadovaného stavu, například když proměnná má určitou hodnotu, kterou chcete zkontrolovat. Můžete nastavit podmínky pomocí výrazů, filtry, nebo počtu položek.

#### <a name="to-create-a-conditional-snappoint"></a>Chcete-li vytvořit podmíněného snappoint

1. Klikněte pravým tlačítkem na ikonu snappoint (dutý míč) a zvolte **nastavení**.

   ![Vyberte nastavení](../debugger/media/snapshot-snappoint-settings.png)

1. V okně Nastavení snappoint zadejte výraz.

   ![Zadejte výraz](../debugger/media/snapshot-snappoint-conditions.png)

   V předchozí ilustraci, provede se výpis pouze pro snappoint při `visitor.FirstName == "Dan"`.

## <a name="set-a-logpoint"></a>Nastavte logpoint

Kromě vytvoření snímku, když je dosaženo snappoint, můžete také nakonfigurovat snappoint do protokolu zprávu (to znamená, vytvořit logpoint). Můžete nastavit logpoints bez nutnosti nasazení vaší aplikace. Logpoints prakticky spustí a způsobit, že žádný dopad nebo vedlejší účinky na běžící aplikaci.

#### <a name="to-create-a-logpoint"></a>Chcete-li vytvořit logpoint

1. Klikněte pravým tlačítkem na ikonu snappoint (modré šestiúhelník) a zvolte **nastavení**.

1. V okně Nastavení snappoint vyberte **akce**.

    ![Vytvoření logpoint](../debugger/media/snapshot-logpoint.png)

1. Do pole zpráva můžete zadat nový zprávu protokolu, kterou chcete protokolovat. Můžete také vyhodnotit proměnné ve zprávě protokolu tím, že je uvnitř složené závorky.

    Pokud se rozhodnete **odeslat do okna výstupu**, když logpoint přístupů, tato zpráva se zobrazí v okně diagnostické nástroje.

    ![V okně diagsession datový Logpoint](../debugger/media/snapshot-logpoint-output.png)

    Pokud si zvolíte **poslat protokolu aplikace**, když je dosaženo logpoint, zpráva se zobrazí, kdekoli, zobrazí se zprávy z `System.Diagnostics.Trace` (nebo `ILogger` v .NET Core), například [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs).

## <a name="next-steps"></a>Další kroky

V tomto kurzu jste zjistili, jak používat ladicí program snímku. Můžete přečíst další informace o této funkci.

> [!div class="nextstepaction"]
> [Nejčastější dotazy k ladění snímků](../debugger/debug-live-azure-apps-faq.md)
