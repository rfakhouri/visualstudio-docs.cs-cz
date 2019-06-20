---
title: Aplikací ASP.NET Core v sadě Visual Studio pro Mac
description: Tento článek popisuje, jak začít pracovat s technologií ASP.NET v sadě Visual Studio pro Mac, včetně instalace a vytvoření nového projektu.
author: asb3993
ms.author: amburns
ms.date: 05/30/2019
ms.assetid: 771C2F8E-46BC-4280-AFE8-ED9D5C7790CE
ms.openlocfilehash: 4e38378c22c6920e471b72d990d61d9b4ebd3d7f
ms.sourcegitcommit: b468d71052a1b8a697f477ab23a3644de139f1e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2019
ms.locfileid: "67253797"
---
# <a name="building-aspnet-core-applications-in-visual-studio-for-mac"></a>Aplikací ASP.NET Core v sadě Visual Studio pro Mac 


ASP.NET Core je open source a multiplatformní rozhraní pro vytváření moderních cloudových aplikací připojených k Internetu, například webové aplikace a služby, aplikace IoT a mobilní back-EndY. Aplikace ASP.NET Core můžete spustit na [.NET Core](https://www.microsoft.com/net/core/platform) nebo na verze rozhraní .NET Framework. Byl navržen k poskytování optimalizované vývojářská platforma pro aplikace, které jsou nasazené do cloudu nebo místní spouštění. Se skládá z modulární komponenty s minimální režií, takže zachování flexibility při sestavování řešení. Můžete vyvíjet a spouštět multiplatformní aplikace ASP.NET Core ve Windows, Mac a Linux. ASP.NET Core je open source v [Githubu](https://github.com/aspnet/home).

V tomto testovacím prostředí vytvoříte a prozkoumejte aplikace ASP.NET Core pomocí sady Visual Studio pro Mac.

## <a name="objectives"></a>Cíle


> [!div class="checklist"]
> * Vytvoření webové aplikace ASP.NET Core
> * Prozkoumejte ASP.NET Core hostování, konfigurace a middleware modelu
> * Ladění webové aplikace ASP.NET Core

## <a name="prerequisites"></a>Požadavky

- [Visual Studio pro Mac](https://www.visualstudio.com/vs/visual-studio-mac)

## <a name="intended-audience"></a>Cílová skupina

Toto testovací prostředí je určeno pro vývojáře, kteří znají C#, i když prostředí není potřeba.

## <a name="task-1-creating-a-new-aspnet-core-application"></a>Úkol 1: Vytvoření nové aplikace ASP.NET Core

1. Spuštění **Visual Studio for Mac**.

2. Vyberte **soubor > Nový řešení**.

3. Vyberte **.NET Core > aplikace** kategorie a **webové aplikace ASP.NET Core (C#)** šablony. Klikněte na **Další**.

    ![](media/netcore-image1.png)

4. Zadejte název **"CoreLab"** a klikněte na tlačítko **vytvořit** pro vytvoření projektu. Chvilku vyplnění bude trvat.

    ![](media/netcore-image2.png)

## <a name="task-2-touring-the-solution"></a>Úkol 2: Uznávaný řešení

1. Výchozí šablona vytvoří řešení pomocí jednoho projektu ASP.NET Core s názvem **CoreLab**. Rozbalte uzel projektu k vystavení jeho obsah.

    ![](media/netcore-image3.png)

2. Tento projekt se řídí model-view-controller (MVC) paradigma poskytnout jasné rozdělení povinností mezi daty (modelů), prezentace (zobrazení) a funkce (kontrolery). Otevřít **HomeController.cs** soubor **řadiče** složky.

    ![](media/netcore-image4.png)

3. **HomeController** třídy podle úmluvy – zpracovává všechny příchozí požadavky, které začínají **/Home**. **Index** metoda obsluhuje požadavky do kořenového adresáře (například `http://site.com/Home`) a jiné metody zpracovávat žádosti o jejich cestu s názvem podle úmluvy, třeba **About()** zpracování žádosti o `http://site.com/Home/About`. To je samozřejmě všechno konfigurovatelné. Jeden zajímavé je, že **HomeController** je výchozí kontroler v novém projektu, proto požadavky do kořenového adresáře webu (`http://site.com`) byste projít **Index()** z  **HomeController** stejně, jako jsou požadavky na `http://site.com/Home` nebo `http://site.com/Home/Index`.

    ![](media/netcore-image5.png)

4. Projekt má také **zobrazení** složku, která obsahuje další složky, které mapují na každém řadiči (a jeden pro **Shared** zobrazení. Například v zobrazení CSHTML souboru (rozšíření HTML) **/Home/About** cesta bude na **Views/Home/About.cshtml**. Otevřete tento soubor.

    ![](media/netcore-image6.png)

5. Tento soubor CSHTML používá syntaxi Razor k vykreslení HTML na základě kombinace standardních značek a vložené C#. Další informace najdete v [online dokumentaci](https://docs.microsoft.com/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c).

    ![](media/netcore-image7.png)

6. Řešení obsahuje také **wwwroot** složku, která se použije kořen pro váš web. Statické webový obsah, jako jsou šablony stylů CSS, obrázky a knihoven jazyka JavaScript, můžete vložit přímo na cesty byste jim být při nasazení webu.

    ![](media/netcore-image8.png)

7. Existují také celou řadu konfiguračních souborů, které slouží ke správě projektu, jeho balíčky a aplikace za běhu. Například výchozí aplikaci [konfigurace](https://docs.microsoft.com/aspnet/core/fundamentals/configuration) je uložen v **appsettings.json**. Však můžete přepsat všech nebo některých z těchto nastavení na základě na prostředí, například tím, že poskytuje **appsettings. Development.JSON** souboru **vývoj** prostředí.

    ![](media/netcore-image9.png)

## <a name="task-3-understanding-how-the-application-is-hosted"></a>Úkol 3: Vysvětlení, jak je hostitelem aplikace

1. Z **Průzkumníka řešení**, otevřete **Program.cs**. Toto je zaváděcí nástroj, který se spustí aplikace.

    ![](media/netcore-image10.png)

2. I když existují jenom dva řádky kódu tady, jsou to podstatné. Podívejme se na nich. První, nový **WebHostBuilder** se vytvoří. Aplikace ASP.NET Core vyžadují hostitele, ve kterém chcete spustit. Hostitel musí implementovat **IWebHost** rozhraní, které vystavuje kolekce funkcí a služeb, a **Start** metody. Hostitel se obvykle vytvoří pomocí instance **WebHostBuilder**, kde jsou vytvářeny a vrátí **WebHost** instance. **WebHost** odkazuje na server, který bude zpracovávat požadavky.

    ![](media/netcore-image11.png)

3. Zatímco **WebHostBuilder** zodpovídá pro vytváření hostitele, který bude bootstrap serveru pro aplikaci, vyžaduje zadejte server, který implementuje **IServer**. Ve výchozím nastavení je to  **[Kestrel](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel)** , napříč platformami webový server pro ASP.NET Core na základě **libuv**, což je knihovna asynchronní vstupně-výstupní operace napříč platformami.

    ![](media/netcore-image12.png)

4. Dále je nastavte kořenové obsahu serveru. Určuje, kde hledá soubory obsahu, jako jsou soubory zobrazení MVC. Výchozí kořen obsahu je složka, ve kterém je aplikace spuštěna.

    ![](media/netcore-image13.png)

5. Pokud aplikace musí fungovat s webový server Internetové informační služby (IIS), **UseIISIntegration** metoda by měla být volána jako součást vytváření hostitele. Že to není konfigurace serveru, jako je třeba **UseKestrel** nepodporuje. Použití služby IIS s ASP.NET Core, musíte zadat oba **UseKestrel** a **UseIISIntegration**. **Kestrel** je navržen pro spouštění za proxy serverem a by se neměly nasazovat přímo směřující internet. **UseIISIntegration** určuje IIS jako reverzní proxy server, ale je relevantní pouze, když běží na počítačích, které služba IIS. Pokud nasadíte aplikaci pro Windows, nechte ho. V opačném případě nebude snížit.

    ![](media/netcore-image14.png)

6. Je přehlednější postupů k oddělení načítání nastavení od spuštění aplikace. Snadno provedete, **UseStartup** nazývá určit, že **spuštění** třída je volat pro načtení nastavení a další úlohy po spuštění, jako je například vložení middleware v kanálu protokolu HTTP. Můžete mít více **UseStartup** volání s předpokladem, že každý z nich přepíše předchozí nastavení podle potřeby.

    ![](media/netcore-image15.png)

7. Posledním krokem při vytváření **IWebHost** je volání **sestavení**.

    ![](media/netcore-image16.png)

8. Zatímco **IWebHost** třídy jsou nutné k implementaci neblokující **spustit**, projekty ASP.NET Core má rozšířenou metodu volá **spustit** tím končí naše  **Spustit** s blokování kódu, takže není nutné ručně metoda zabránit okamžitě ukončí.

    ![](media/netcore-image17.png)

## <a name="task-4-running-and-debugging-the-application"></a>Úloha 4: Spuštění a ladění aplikace

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem myši **CoreLab** uzel projektu a vyberte **možnosti**.

    ![](media/netcore-image18.png)

2. **Možnosti projektu** dialogového okna obsahuje všechno, co je potřeba upravit, jak je aplikace vytvořená a spustit. Vyberte **spustit > Konfigurace > výchozí** uzlu na levém panelu.

3. Zkontrolujte **spouštět na externí konzole** a zrušte zaškrtnutí políčka **pozastavit výstup konzoly**. Obvykle nemusí jeho konzole viditelné v místním prostředí aplikace, ale místo toho typicky zaznamenávají svých výsledků **výstup** panel. Pro účely tohoto testovacího prostředí se vám ukážeme ho v samostatném okně, i když není nutné to udělat během vývoje.

4. Klikněte na **OK**.

    ![](media/netcore-image19.png)

5. Stisknutím klávesy **F5** sestavíte a spustíte aplikaci. Alternativně můžete vybrat **spuštění > Spustit ladění**.

6. Visual Studio pro Mac se spustí dvě okna. První je okno konzoly, která poskytuje přehled o aplikace v místním prostředí serveru.

    ![](media/netcore-image20.png)

7. Druhým je okno prohlížeče typické pro testování webu. Jde o prohlížeči ví, tuto aplikaci můžou být hostované kdekoli. Klikněte na tlačítko **o** přejděte na tuto stránku.

    ![](media/netcore-image21.png)

8. Mimo jiné stránka vykresluje nějaký text, nastavte v kontroleru.

    ![](media/netcore-image22.png)

9. Zachovat obě okna otevřete a vrátit se sadou Visual Studio pro Mac. Otevřete **Controllers/HomeController.cs** Pokud ještě není otevřený.

    ![](media/netcore-image23.png)

10. Nastavte zarážku v prvním řádku **o** metody. To můžete provést klepnutím na okraj nebo nastavuje kurzor na řádku a stisknutím klávesy **F9**. Tento řádek nastaví některá data **ViewData** kolekce, který je vykreslen na stránce CSHTML v **Views/Home/About.cshtml**.

    ![](media/netcore-image24.png)

11. Vraťte se do prohlížeče a aktualizace o stránce. Tím se aktivuje zarážky v sadě Visual Studio pro Mac.

12. Najedete myší **ViewData** člen zobrazíte jeho data. Můžete také rozšířit jeho podřízených členů zobrazíte vnořené data.

    ![](media/netcore-image25.png)

13. Odeberte narážku aplikace stejným způsobem, který jste použili ho přidat.

14. Otevřít **Views/Home/About.cshtml**.

15. Změní celý text **"Další"** k **"změnit"** a soubor uložte.

    ![](media/netcore-image26.png)

16. Stisknutím klávesy **pokračovat** tlačítko pro pokračování v provádění.

    ![](media/netcore-image27.png)

17. Vraťte se do okna prohlížeče, zobrazí aktualizovaný text. Tato změna docházelo v okamžiku a není nutně vyžadovat zarážek ladicího programu. Aktualizujte prohlížeč, pokud se tato změna se projeví okamžitě.

    ![](media/netcore-image28.png)

18. Zavřete konzolu prohlížeče testovací okno a aplikace. Tento kód přestane i ladění.

## <a name="task-5-application-startup-configuration"></a>Úloha 5: Konfigurace spuštění aplikace

1. Z **Průzkumníka řešení**, otevřete **Startup.cs**. Můžete si všimnout některých červenou vlnovkou zpočátku na pozadí probíhá obnovení balíčků NuGet a kompilátor Roslyn sestavuje ucelený přehled o závislosti projektu.

    ![](media/netcore-image29.png)

2. Vyhledejte **spuštění** metody. Tato část definuje počáteční konfiguraci aplikace a hustě zabaleny. Pojďme si to ujasnit.

    ![](media/netcore-image30.png)

3. Metoda spustí na inicializaci **ConfigurationBuilder** a nastavení jeho základní cesta.

    ![](media/netcore-image31.png)

4. V dalším kroku načte požadované **appsettings.json** souboru.

    ![](media/netcore-image32.png)

5. Poté, pokusí se načíst konkrétní prostředí **appsettings.json** soubor, který by se mělo přepsat stávající nastavení. Jde například zadaný **appsettings. Development.JSON** soubor použitý pro toto konkrétní prostředí. Další informace o konfiguraci v ASP.NET Core, projděte si [dokumenty](https://docs.microsoft.com/aspnet/core/fundamentals/configuration).

    ![](media/netcore-image34.png)

6. A konečně proměnné prostředí jsou přidány do Tvůrce konfigurace a konfigurace je vytvořená a nastavte pro využití.

    ![](media/netcore-image35.png)

## <a name="task-6-inserting-application-middleware"></a>Krok 6: Vložení aplikace middlewaru

1. Vyhledejte **konfigurovat** metodu **spuštění** třídy. Je to, kde veškerý middleware je nakonfigurovaný tak, že může být vložen do kanálu protokolu HTTP a používají ke zpracování každého požadavku na server. Zatímco tato metoda je volána pouze jednou, obsah z metod (například **UseStaticFiles**) mohou být provedeny u každého požadavku.

    ![](media/netcore-image36.png)

2. Můžete také přidat další middleware, který se spustí jako součást kanálu. Přidejte následující kód za **aplikace. UseStaticFiles** automaticky přidat **X-Test** záhlaví pro každou odchozí odpovědi. Technologie IntelliSense vám pomůže dokončit kód při psaní.

    ```csharp
    app.Use(async (context, next) =>
    {
        context.Response.Headers.Add("X-Test", new[] { "Test value" });
        await next();
    });
    ```

3. Stisknutím klávesy **F5** sestavte a spusťte projekt.

4. Prohlížeč jsme můžete použít ke kontrole hlavičky pro ověření, že jsou přidány. Následující pokyny jsou určené pro Safari, ale můžete provést totéž [Chrome](https://stackoverflow.com/questions/4423061/view-http-headers-in-google-chrome) nebo [Firefox](https://stackoverflow.com/questions/33974595/in-firefox-how-do-i-see-http-request-headers-where-in-web-console).

5. Jakmile prohlížeč načte webu, vyberte **Safari > Předvolby**.

6. Na **Upřesnit** kartě **nabídky Zobrazit vyvíjet v řádku nabídek** a zavřete dialogové okno.

    ![](media/netcore-image37.png)

7. Vyberte **vývoj > Zobrazit prostředky stránky**.

8. Aktualizujte okno prohlížeče, takže můžete sledovat a analyzovat provoz a obsah nově otevřené vývojářské nástroje.

9. Stránku HTML localhost zpracovanou serverem budou položky vybrané ve výchozím nastavení.

    ![](media/netcore-image38.png)

10. Rozbalte **postranní panel podrobnosti**.

    ![](media/netcore-image39.png)

11. Přejděte do dolní části bočního panelu zobrazíte hlavička odpovědi přidat v kódu výše.

    ![](media/netcore-image40.png)

12. Zavřete okno prohlížeče a konzoly, když vyhovují.

## <a name="summary"></a>Souhrn

V tomto testovacím prostředí jsme zjistili, jak začít s vývojem aplikací ASP.NET Core pomocí sady Visual Studio pro Mac. Pokud chcete prozkoumat vývoj úplnější filmy databázovou aplikaci, najdete v článku [Začínáme s ASP.NET Core MVC](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/start-mvc) kurzu.
