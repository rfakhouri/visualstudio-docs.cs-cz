---
title: "Analýza spotřeby energie v aplikacích pro UPW | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 96d06843-b97e-45a8-8126-07478a40bfc4
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: uwp
ms.openlocfilehash: 9ad762745627c2c30378f5017d88e78b00921d4a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="analyze-energy-use-in-uwp-apps"></a>Analýza spotřeby energie v aplikacích pro UPW
Visual Studio **spotřeba energie na** profileru pomáhá analyzovat power a spotřeby energie aplikací UWP do úsporného režimu tablet zařízení, která používají nebo jeho část čas na své vlastní baterie. Na zařízení napájeném z baterie může aplikace s příliš vysokou spotřebou energie způsobit tak velkou nespokojenost zákazníka, že ji může dokonce i odinstalovat. Optimalizace energie můžete zvýšit přijetí vaší aplikace a použít zákazníků.  
  
##  <a name="BKMK_What_the_Energy_Consumption_tool_is__how_it_works__and_what_it_measures"></a>Co je profileru spotřeba energie, jak to funguje a co měří  
 Profiler Spotřeba energie shromažďuje údaje o činnosti displeje, procesoru a síťových připojení zařízení během relace profilování. Poté vygeneruje odhady množství energie použité pro tyto činnosti a celkové množství energie použité pro relaci profilování.  
  
> [!NOTE]
>  Energetický profiler provádí odhad výkonu a spotřeby energie pomocí softwarového modelu standardního hardwaru referenčního zařízení, jež reprezentuje tablety s nízkou spotřebou, na kterých by vaše aplikace mohla běžet. Pro dosažení co nejlepšího odhadu doporučujeme shromáždit profilová data u tabletů s nízkou spotřebou.  
>   
>  Ačkoliv model poskytuje dobré odhady pro řadu zařízení s nízkou spotřebou, skutečné hodnoty zařízení, která profilujete, budou pravděpodobně odlišné. Použijte tyto hodnoty pro nalezení aktivit displeje, procesoru a sítě, které jsou v porovnání s využitím jiných prostředků náročné, takže by mohly představovat vhodné kandidáty na optimalizaci.  
  
 Spotřeba energie na profileru používá tyto definice *power* a *energie*:  
  
-   *Napájení* míry rychlost, jakou vynutit se používá k provedení práce, která se provádí v časovém intervalu. V elektrický vědecké účely, je standardní jednotky napájení *watt*, který je definován jako rychlost, jakou práci při jednu Ampér – měrná aktuální toků prostřednictvím elektrický rozdíly z jednoho Volt – měrná. V **spotřeby energie** grafu, jednotky se zobrazují jako miliwattech **mW** 1/1 000 watt, které jsou.  
  
     Všimněte si, že výkon má směr (množství práce se v čase může zvýšit nebo snížit) a rychlost (velikost zvýšení nebo snížení množství práce).  
  
-   *Energie* míry celkovou spotřebu energie, jako kapacity nebo potenciální jako kapacita napájení z baterie, nebo jako celkový počet dosáhl napájení použito přes v časovém intervalu. Jednotkou energie je watthodina, tedy výkon jednoho wattu konstantně působící po jednu hodinu. V **energie Souhrn**, jednotky se zobrazují jako udávaná hodin **mW-h**.  
  
 ![Kapacita energie power používá, celkovou spotřebu použít](../profiling/media/energyprof_capcitypowerused.png "ENERGYPROF_CapcityPowerUsed")  
  
 Například plně nabitá baterie v tabletu uchovává určité množství energie. Při využívání této energie pro provádění úloh, jako je například komunikace po síti, výpočty hodnot nebo zobrazování grafického obsahu, se výkon spotřebovává různou rychlostí. Pro libovolné časové období se celkové množství spotřebovaného výkonu poměřuje také energií.  
  
##  <a name="BKMK_Identify_scenarios_with_user_marks"></a>Určit scénáře značkami, podle uživatele  
 Můžete přidat *uživatele značky* k datům profilování, aby bylo možné identifikovat oblasti pravítka časové osy.  
  
 ![Značky uživatele v časové ose](../profiling/media/profilers_usermarktimeline.png "PROFILERS_UserMarkTimeline")  
  
 Značka se zobrazí jako oranžový trojúhelník umístěný na časové ose v čase spuštění metody. Zpráva a čas se zobrazí jako popisek, jakmile na značku umístíte ukazatel myší. Pokud jsou dvě nebo více uživatelských značek blízko u sebe, značky i popisky se sloučí. Značky od sebe rozlišíte přiblížením časové osy.  
  
 **Přidat značky jazyka C#, Visual Basic, C++ – kód**  
  
 Přidání značka uživatele jazyka C#, Visual Basic, C++ – kód, nejprve vytvořit [Windows.Foundation.Diagnostics LoggingChannel](http://msdn.microsoft.com/library/windows/apps/windows.foundation.diagnostics.loggingchannel.aspx) objektu. Potom vložit volání pro [LoggingChannel.LogMessage](http://msdn.microsoft.com/library/windows/apps/dn264210.aspx) metody v bodech ve vašem kódu, který chcete označit. Použití [LoggingLevel.Information](http://msdn.microsoft.com/library/windows/apps/windows.foundation.diagnostics.logginglevel.aspx) v volání.  
  
 Jakmile se metoda spustí, uživatelská značka je spolu se zprávou přidána do profilových dat.  
  
> [!NOTE]
>  -   Implementuje Windows.Foundation.Diagnostics LoggingChannel [Windows.Foundation.IClosable](/uwp/api/windows.foundation.iclosable) rozhraní (předpokládané jako [System.IDisposable](/dotnet/api/system.idisposable) v C# a VB). Aby se zabránilo úniku prostředky operačního systému, volání [LoggingChannel.Close](/uwp/api/Windows.Foundation.Diagnostics.LoggingChannel) ([Windows.Foundation.Diagnostics.LoggingChannel.Dispose](/uwp/api/Windows.Foundation.Diagnostics.LoggingChannel) v C# a VB) po dokončení s protokolování kanál.  
> -   Každý otevřený protokolovací kanál musí mít jedinečný název. Pokus o vytvoření nového protokolovacího kanálu se stejným názvem, jaké má jiný kanál, způsobil výjimku.  
  
 Najdete v části Windows SDK ukázka [LoggingSession ukázka](http://code.msdn.microsoft.com/windowsapps/LoggingSession-Sample-ccd52336) příklady.  
  
 **Přidat značky do kódu jazyka JavaScript**  
  
 Chcete-li přidat uživatelské značky, přidejte do míst v kódu, které chcete označit, následující kód:  
  
```  
if (performance && performance.mark) {  
    performance.mark(markDescription);  
}  
```  
  
 *markDescription* je řetězec, který obsahuje zprávu zobrazíte v popisku označit uživatele.  
  
##  <a name="BKMK_Configure_your_environment_for_profiling"></a>Konfigurace prostředí pro profilaci  
 Pokud chcete získat odhad funkční, budete chtít profilu energie aplikace na zařízení úsporný, který používá technologii jeho baterie. Protože Visual Studio se nespouští na většinu těchto zařízení, budete muset počítač Visual Studio se připojte k zařízení pomocí nástrojů pro vzdálenou aplikaci Visual Studio. Pro připojení ke vzdálenému zařízení je třeba nakonfigurovat jak projekt aplikace Visual Studio, tak vzdálené zařízení. V tématu [aplikace UWP spustit na vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md) Další informace.  
  
> [!TIP]
>  -   Nedoporučujeme energie profilace v simulátoru UWP nebo v sadě Visual Studio počítači. Profilace přímo na příslušném zařízení poskytuje mnohem realističtější data.  
> -   Provádějte profilaci na cílovém zařízení v době, kdy je zařízení napájeno bateriemi.  
> -   Zavřete ostatní aplikace, které by mohly využívat stejné prostředky (síť, procesor nebo displej).  
  
##  <a name="BKMK_Collect_energy_profile_data_for_your_app"></a>Shromažďování dat profilu energie pro vaši aplikaci.  
  
1.  Na **ladění** nabídce zvolte **spustit diagnostiku bez ladění**.  
  
     ![Zvolte spotřebu energie v Centrum diagnostiky](../profiling/media/energyprof_diagnosticshub.png "ENERGYPROF_DiagnosticsHub")  
  
2.  Zvolte **spotřeba energie na** a potom zvolte **spustit**.  
  
    > [!NOTE]
    >  Při spuštění **spotřeba energie na** profileru, může dojít **řízení uživatelských účtů** okno požadující vaše oprávnění ke spuštění VsEtwCollector.exe. Zvolte **Ano**.  
  
3.  Spusťte v aplikaci shromažďování dat.  
  
4.  Zastavit profilování, přepněte zpět na Visual Studio (Alt + Tab) a zvolte **zastavit shromažďování** na stránce centra diagnostiky.  
  
     ![Zastavit shromažďování dat](../profiling/media/xamlprof_stopcollection.png "XAMLProf_StopCollection")  
  
     Aplikace Visual Studio analyzuje shromážděná data a zobrazuje výsledky.  
  
##  <a name="BKMK_Collect_energy_profile_data_for_an_installed_app"></a>Shromažďovat data profilu energie pro nainstalovanou aplikaci  
 Nástroj Spotřeba energie lze spustit pouze v aplikacích pro Windows Store 8.1, které jsou spouštěny z řešení aplikace Visual Studio nebo jsou instalovány z Windows Store. Když je řešení otevřené v sadě Visual Studio, je výchozí cíl **spouštěný projekt**. Zacílení nainstalované aplikace:  
  
1.  Zvolte **změnit cíl** a potom zvolte **nainstalované aplikace**.  
  
2.  Z **vyberte balíček aplikace nainstalována** vyberte cíl.  
  
3.  Zvolte **spotřeba energie** na stránce centra diagnostiky.  
  
4.  Zvolte **spustit** zahájíte vytváření profilů.  
  
 Zastavit profilování, přepněte zpět na Visual Studio (Alt + Tab) a zvolte **zastavit shromažďování** na stránce centra diagnostiky.  
  
##  <a name="BKMK_Analyze_energy_profile_data"></a>Analýza dat profilu energie  
 Data energetického profilu se zobrazují v okně dokumentu aplikace Visual Studio:  
  
 ![Stránka sestavy profileru energie](../profiling/media/energyprof_all.png "ENERGYPROF_All")  
  
|||  
|-|-|  
|![Krok 1](../profiling/media/procguid_1.png "ProcGuid_1")|Soubor sestavy má název sestavy*RRRRMMDD hh: mm*.diagsession. Pokud se rozhodnete sestavu uložit, můžete název změnit.|  
|![Krok 2](../profiling/media/procguid_2.png "ProcGuid_2")|Časová osa ukazuje délku relace profilace, aktivační události životního cyklu aplikace a uživatelské značky.|  
|![Krok 3](../profiling/media/procguid_3.png "ProcGuid_3")|Přetažením modrých panelů můžete vybrat určitou oblast časové osy a omezit tak sestavu jen na tuto část časové osy.|  
|![Krok 4](../profiling/media/procguid_4.png "ProcGuid_4")|**Spotřeby energie** grafu je Víceřádkový graf, který zobrazuje změny ve výkonu způsobený prostředků zařízení během relace profilování. Profiler Spotřeba energie sleduje výkon využívaný procesorem, síťovou aktivitou a displejem.|  
|![Krok 5](../profiling/media/procguid_6.png "ProcGuid_6")|**Prostředky (On/vypnutém)** graf obsahuje podrobnosti o síti náklady na energii. **Sítě** panelu představuje čas, který síťové připojení není otevřené. **Přenos dat** podřízené panelu je čas, aby byla aplikace příjem nebo odeslání dat přes síť.|  
|![Krok 6](../profiling/media/procguid_6a.png "ProcGuid_6a")|**Energie využití: Souhrn** ukazuje přímo úměrná množství celkovou spotřebu, která byla použita ve vybrané časové osy procesoru, síťové aktivity a zobrazení na obrazovce.|  
  
 **K analýze dat profilu energie**  
  
 Najděte oblast, kde výkon prostředku dosáhl vrcholu. Přiřaďte tuto oblast k funkci vaší aplikace. Pomocí ovládacích panelů časové osy můžete tuto oblast přiblížit. Pokud jsou zaměřené na využití sítě, rozbalte **sítě** uzel v **prostředky (On/vypnutém)** grafu se porovnat čas, který připojení k síti nebylo otevřete na dobu, která aplikace přijímala nebo přenosu data přes dané připojení. Zkrácení doby, po kterou je síť zbytečně otevřená, představuje velmi efektivní optimalizaci.  
  
##  <a name="BKMK_Optimize_energy_use"></a>Optimalizace energie  
 Kromě přenosu dat vynakládají síťová připojení energii také na inicializaci, udržování a ukončování připojení. Některé sítě udržují připojení po určitou dobu po odeslání nebo přijetí dat, aby umožnily přenos většího množství dat v rámci jednoho připojení. Můžete použít **prostředky (On/vypnutém)** podokně zkontrolujte způsob, jakým aplikace komunikuje s připojením.  
  
 ![Prostředky &#40; na &#47; vypnutí &#41; Podokno](../profiling/media/energyprof_resources.png "ENERGYPROF_Resources")  
  
 Pokud **sítě** a **přenos dat** řádky ukazují, že připojení je otevřeno dlouhou dobu občas přenášet řadu malých datových paketů, můžete dávky dat k odeslání v jedné přenosu zkrátit čas, který je v síti otevřete a tím uložte náklady na energii.  
  
 ![Podokno Souhrn spotřeba energie](../profiling/media/energyprof_summary.png "ENERGYPROF_Summary")  
  
 Spotřebu energie displeje lze ovlivnit hůře. Většina obrazovek potřebuje více energie k zobrazení světlých barev než tmavších barev, takže jedním ze způsobů, jak snížit spotřebu, je použití tmavého pozadí.  
  
##  <a name="BKMK_Other_resources"></a>Další prostředky  
  
-   **Stav připojení a Správa nákladů** částech pro [C# / VB/C++ a XAML](http://msdn.microsoft.com/en-us/0ee0b706-8432-4d49-9801-306ed90764e1) a [JavaScript a HTML](http://msdn.microsoft.com/en-us/372afa6a-1c7c-4657-967d-03a77cd8e933) ve službě Windows Dev Center popisují rozhraní API systému Windows, které poskytují síťové připojení informace, které aplikace můžete minimalizovat náklady na síťový provoz.  
  
     Simulátoru Visual Studio pro aplikace UWP můžete simulovat vlastnosti připojení dat informace o síťové rozhraní API. V tématu [aplikace UWP spustit v simulátoru](../debugger/run-windows-store-apps-in-the-simulator.md)  
  
-   **Časování funkce JavaScript** a **využití procesoru** nástroje vám může pomoct snížit zatížení procesoru při je způsobena neefektivní funkce. V tématu [analýza využití procesoru](../profiling/analyze-cpu-usage-in-a-windows-universal-app.md).

## <a name="see-also"></a>Viz také
 [Profilace v sadě Visual Studio](../profiling/index.md)  
 [Prohlídka funkce profilace](../profiling/profiling-feature-tour.md)