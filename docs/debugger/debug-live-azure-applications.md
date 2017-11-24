---
title: "Ladění aplikací za provozu technologie ASP.NET Azure – Visual Studio | Microsoft Docs"
ms.date: 11/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02f91441c493d65e8abcdc80bd85b01f2bd423bf
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2017
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>Ladění za provozu aplikací ASP.NET Azure pomocí snímku ladicí program

Ladicí program snímku pořídí snímek aplikací v provozním, když provede kód, který vás zajímá. Dáte pokyn, aby ladicí program na pořízení snímku, nastavte snappoints a logpoints ve vašem kódu. Ladicí program umožňuje zobrazit přesně kde došlo k chybě, bez vlivu na provoz produkční aplikace. Ladicí program snímku můžete výrazně zkrátit dobu potřebnou k vyřešení problémů, ke kterým došlo v produkčním prostředí.

Snappoints a logpoints jsou podobné zarážky. Na rozdíl od zarážky, snappoints není zastavení aplikace při průchodu. Pořízením na snappoint obvykle trvá 10 20 milisekund. 

Snímek kolekce je k dispozici pro následující webové aplikace běžící v Azure App Service:

- Aplikace ASP.NET spuštěné na rozhraní .NET Framework 4.6.1 nebo novější.
- ASP.NET Core aplikací běžících na .NET Core 2.0 nebo novější na systému Windows.

Kromě toho ladicí program snímku je dostupná jenom pro Visual Studio Enterprise 2017 verze 15,5 nebo vyšší a plány služby App Service základní nebo vyšší. 

## <a name="start-the-snapshot-debugger"></a>Spuštění ladicího programu snímku

1. Nainstalujte [Visual Studio Enterprise 15,5 Preview](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-preview-relnotes) nebo novější. Při aktualizaci z předchozí verze preview Visual Studio 2017, spusťte instalační program Visual Studio a zkontrolujte ladicí program snímku součástí technologie ASP.NET a webové úlohy vývoj.

2. Otevřete projekt, který chcete snímek ladění. 

    > [!IMPORTANT] 
    > Aby snímku ladění, je třeba otevřít **stejnou verzi zdrojový kód** je publikována ve službě Azure App Service. 

3. V Průzkumníku cloudu (vyberte **zobrazení > Průzkumník cloudu**), klikněte pravým tlačítkem na projekt se nasadí do služby Azure App Service a vyberte **připojit ladicí program snímku** spuštění ladicího programu snímku.

   ![Spuštění ladicího programu snímku](../debugger/media/snapshot-launch.png "spuštění ladicího programu snímku")

    Při prvním vyberete **připojit ladicí program snímku**, zobrazí se výzva k instalaci ladicí program snímku ve službě Azure App Service. Tato instalace vyžaduje restart služby Azure App Service. 

   Visual Studio je nyní v režimu ladění snímek.

   ![Režim ladění snímku](../debugger/media/snapshot-message.png "snímku režim ladění")

   **Moduly** okno zobrazí, když mají všechny moduly načten pro Azure App Service (zvolte **ladění / Windows / moduly** otevřete toto okno).

   ![Zkontrolujte okna moduly](../debugger/media/snapshot-modules.png "zkontrolujte okna moduly")

## <a name="set-a-snappoint"></a>Nastavte snappoint

1. V editoru kódu klikněte na levém oddělovací mezery u řádek kódu, které vás zajímají nastavení snappoint. Ujistěte se, že je kód, který znáte, budou spuštěny.

   ![Nastavte snappoint](../debugger/media/snapshot-set-snappoint.png "nastavit snappoint")

2. Klikněte na tlačítko **Start Collection** zapnout snappoint.  

   ![Zapnout snappoint](../debugger/media/snapshot-start-collection.png "zapnout snappoint")

    > [!TIP]
    > Nelze krok při zobrazení snímku, ale můžete umístit více snappoints ve vašem kódu provést spuštění na různé řádky kódu. Pokud máte více snappoints ve vašem kódu, snímku ladicího programu zajistí odpovídající snímky ze stejné relace koncového uživatele, i v případě, že více uživatelů stiskne vaší aplikace.

## <a name="take-a-snapshot"></a>Pořízení snímku

Když je zapnutý snappoint, bude zachytit snímek, vždy, když se spustí na řádek kódu, kde je umístěn snappoint. Spuštění tohoto může být způsobeno skutečné žádosti na vašem serveru. Chcete-li vynutit vaší snappoint narazí, můžete také přejděte do zobrazení prohlížeče webový server a proveďte požadované všechny akce, které způsobit vaší snappoint být narazí.

## <a name="inspect-snapshot-data"></a>Zkontrolujte data snímku

1. Když je dosaženo snappoint, se zobrazí v okně diagnostické nástroje snímek. Zvolte **ladění / Windows / zobrazit diagnostické nástroje** otevřete toto okno.

   ![Otevřete snappoint](../debugger/media/snapshot-diagsession-window.png "otevřete snappoint")

1. Dvakrát klikněte na snappoint otevřete snímku v editoru kódu.

   ![Zkontrolujte data snímku](../debugger/media/snapshot-inspect-data.png "zkontrolujte data snímku")

   Z tohoto hlediska můžete podržet přes proměnné, které chcete zobrazit datatips –, použijte **místní hodnoty –**, **sleduje**, a **zásobníkem volání** windows a také vyhodnocení výrazů.

    Web, samotné je stále za provozu a nejsou dopad na koncové uživatele. Pouze jeden snímek pořízen za snappoint ve výchozím nastavení: Po zachycení snímku snappoint vypne. Pokud chcete zaznamenat jiného snímku na snappoint, můžete zapnout snappoint zpět na kliknutím **aktualizace kolekce**.

Můžete také přidat další snappoints do vaší aplikace a je zapnout pomocí **aktualizace kolekce** tlačítko.

**Potřebujete pomoc?** Najdete v článku [řešení potíží a známé problémy](../debugger/debug-live-azure-apps-troubleshooting.md) a [– nejčastější dotazy k ladění snímku](../debugger/debug-live-azure-apps-faq.md) stránky.

## <a name="set-a-conditional-snappoint"></a>Nastavit podmíněný snappoint

Pokud je obtížné znovu vytvořit konkrétní stav ve vaší aplikaci, zvažte, zda může pomoci použití podmíněného snappoint. Podmíněné snappoints můžete vyhnout pořízení snímku, dokud aplikace vstupuje do požadovaného stavu, například pokud proměnná obsahuje hodnotu konkrétní co vás zajímá. Můžete nastavit podmínky pomocí výrazů, filtry, nebo počtu položek.

#### <a name="to-create-a-conditional-snappoint"></a>Chcete-li vytvořit podmíněného snappoint

1. Klikněte pravým tlačítkem na ikonu snappoint (dutý míč) a zvolte **nastavení**.

   ![Vyberte nastavení](../debugger/media/snapshot-snappoint-settings.png "zvolit nastavení")

1. V okně Nastavení snappoint zadejte výraz.

   ![Zadejte výraz](../debugger/media/snapshot-snappoint-conditions.png "zadejte výraz")

   V předchozí ilustraci, provede se výpis pouze pro snappoint při `visitor.FirstName == "Dan"`.

## <a name="set-a-logpoint"></a>Nastavte logpoint

Kromě vytvoření snímku, když je dosaženo snappoint, můžete také nakonfigurovat snappoint do protokolu zprávu (to znamená, vytvořit logpoint). Můžete nastavit logpoints bez nutnosti nasazení vaší aplikace. Logpoints prakticky spustí a způsobit, že žádný dopad nebo vedlejší účinky na běžící aplikaci.

#### <a name="to-create-a-logpoint"></a>Chcete-li vytvořit logpoint

1. Klikněte pravým tlačítkem na ikonu snappoint (modré šestiúhelník) a zvolte **nastavení**.

1. V okně Nastavení snappoint vyberte **akce**.

    ![Vytvoření logpoint](../debugger/media/snapshot-logpoint.png "vytvořit logpoint")

1. Do pole zpráva můžete zadat nový zprávu protokolu, kterou chcete protokolovat. Můžete také vyhodnotit proměnné ve zprávě protokolu tím, že je uvnitř složené závorky.

    Pokud se rozhodnete **odeslat do okna výstupu**, když logpoint přístupů, tato zpráva se zobrazí v okně diagnostické nástroje.

    ![V okně .diagsession datový Logpoint](../debugger/media/snapshot-logpoint-output.png "Logpoint data v okně .diagsession")

    Pokud si zvolíte **poslat protokolu aplikace**, když je dosaženo logpoint, zpráva se zobrazí, kdekoli, zobrazí se zprávy z `System.Diagnostics.Trace` (nebo `ILogger` v .NET Core), například [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs).

## <a name="next-steps"></a>Další kroky

- Informace o tom, chcete-li prověřit proměnné při zobrazení snímku, najdete v části [prohlídka funkce Debbuger](../debugger/debugger-feature-tour.md).
- Zobrazení [– nejčastější dotazy k ladění snímku](../debugger/debug-live-azure-apps-faq.md).
- Zobrazení [řešení potíží s tipy a známé problémy pro ladění snímku](../debugger/debug-live-azure-apps-troubleshooting.md).
- Pokud chcete zobrazit snímky ve službě Application Insights, pokud se vaše aplikace dotkne výjimku, můžete to udělat. Další informace najdete v tématu [ladění snímků výjimky v aplikacích .NET](/azure/application-insights/app-insights-snapshot-debugger). Application Insights podporuje aplikace Service Fabric kromě Azure App Service.
