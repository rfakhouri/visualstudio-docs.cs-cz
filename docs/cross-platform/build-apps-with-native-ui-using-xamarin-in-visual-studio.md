---
title: Vývoj aplikací s nativní uživatelského rozhraní v sadě Visual Studio pomocí Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 67d8b2147426a048f2af92b0525fd6c8139b4558
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Vývoj aplikací s nativní uživatelského rozhraní pomocí Xamarinu v sadě Visual Studio

Většina vývojářů, kteří se rozhodnou Xamarinu a C# pro zápis mobilních aplikací a platformy používají Xamarin.Forms. Xamarin.Forms definuje uživatelské rozhraní, která se mapuje na nativní ovládací prvky v iOS, Android a univerzální platformu Windows (UWP). Xamarin.Forms je popsána v článku [další základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

Tento článek popisuje použití jiné metody, která zahrnuje přístup k rozhraní API nativní uživatelského rozhraní pro každou platformu. Práci s nativních rozhraní API je mnohem těžší přístup než Xamarin.Forms, protože vyžaduje rozsáhlé znalosti o každou platformu. Výhoda spočívá v tom uživatelské rozhraní pro konkrétní síly a možnosti pro každou platformu můžete přizpůsobit při stále sdílení základní obchodní logiku.

Jakmile provedete kroky krok [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md), tento postup vám ukáže, jak vytvořit základní aplikaci Xamarin s vrstvami nativní uživatelského rozhraní. Nativní uživatelského rozhraní sdíleného kódu se nachází v rozhraní .NET standardní knihovna a jednotlivé platformy projekty obsahovat definice uživatelského rozhraní. Tady je aplikace, která budete sestavení (zleva doprava) a systémem iOS a telefony Android a Windows 10 desktop.
  
[![Aplikace Xamarin pro iOS, Android a Windows](../cross-platform/media/cross-plat-xamarin-build-1.png "1 sestavení Xamarin Cross-Plat")](../cross-platform/media/cross-plat-xamarin-build-1-Large.png#lightbox)
  
Můžete to udělat ji od sestavit tyto věci:  
  
- [Nastavit řešení](#solution)  
  
- [Zápis kódu služby sdílených dat](#dataservice)  
  
- [Návrh uživatelského rozhraní pro Android](#Android)  

- [Návrh uživatelského rozhraní pro Windows](#Windows)  
  
- [Další kroky](#next), mezi které patří navrhování iOS uživatelské rozhraní
  
> [!TIP]
> Můžete najít úplný zdrojový kód pro tento projekt v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
> Pokud máte problémy nebo dojde k chybám, odešlete prosím dotazy na [forums.xamarin.com](http://forums.xamarin.com). Mnoho chyb lze vyřešit aktualizací na nejnovější SDK vyžaduje Xamarin, které jsou popsány v [k vydání verze Xamarinu](https://developer.xamarin.com/releases/) pro každou platformu.    
  
> [!NOTE]
> Dokumentaci pro vývojáře pro Xamarin také nabízí několik návody s rychlý start a podrobné informace, jak je uvedeno dále. Na těchto stránkách Ujistěte se, že je vybrán "Visual Studio" v tématu postupy, které jsou specifické pro Visual Studio.  
>   
>  -   Xamarin aplikace s nativní uživatelského rozhraní:  
>     -   [Hello, Android](/xamarin/android/get-started/hello-android/) (jednoduché aplikace s jednu obrazovku)  
>     -   [Hello, Android Multiobrazovka](/xamarin/android/get-started/hello-android-multiscreen/) (aplikace s navigace mezi obrazovkami)  
>     -   [Android návod fragmenty](/xamarin/android/platform/fragments/fragments/implementing-with-fragments/walkthrough/) (používá se pro obrazovky a podrobností, mimo jiné)  
>     -   [Hello, iOS](/xamarin/ios/get-started/hello-iOS/)  
>     -   [Hello, iOS s více obrazovkami](/xamarin/ios/get-started/hello-iOS-multiscreen/) 

>  -   Aplikace Xamarin s Xamarin.Forms (sdílené uživatelského rozhraní)  
>     -   [Hello, Xamarin.Forms](/xamarin/xamarin-forms/get-started/hello-xamarin-forms/quickstart/)  
>     -   [Hello, Xamarin.Forms s více obrazovkami](/xamarin/xamarin-forms/get-started/hello-xamarin-forms-multiscreen/)  
  
<a name="solution" />

##  <a name="set-up-your-solution"></a>Nastavit řešení  

Visual Studio není k dispozici šablona řešení pro vytváření nativních aplikací uživatelského rozhraní .NET standardní knihovna pro sdílení. Není však pevný k vytvoření řešení z jednotlivých projektů. Těchto kroků vytvořte Xamarin řešení s projekty pro každý typ aplikace platformy a rozhraní .NET standardní knihovna pro sdílené kód.  
  
1.  V sadě Visual Studio vytvořte novou **knihovny tříd (.NET Standard)** řešení a pojmenujte ji **WeatherApp**. Tuto šablonu můžete snadno najít výběrem **Visual C#** na levé straně a pak **.NET Standard**: 

    ![Vytváření .NET standardní řešení](../cross-platform/media/cross-plat-xamarin-build-2.png "sestavení Xamarin napříč platformami 2")

    Po kliknutí na tlačítko OK, **WeatherApp** řešení se skládá z jedné projektu s názvem **WeatherApp**. 

2.  Pokud chcete cílový iOS, do řešení přidáte projektu pro iOS. Klikněte pravým tlačítkem na název řešení v **Průzkumníku řešení** a vyberte **přidat** a **nový projekt**.  V **nový projekt** dialogovém okně na levém vyberte **Visual C#** a potom **iOS** a **univerzální**. (Pokud tam není, možná budete muset nainstalovat Xamarin nebo Visual Studio 2017 funkci povolit, najdete v části [nastavení a instalaci](../cross-platform/setup-and-install.md).) V seznamu šablon, vyberte **jediné zobrazení aplikace (iOS)**. Pojmenujte ji **WeatherApp.iOS**.

3.  Pokud chcete zacílit Android, do řešení přidáte projektu pro Android. V **nový projekt** dialogovém okně na levém vyberte **Visual C#** a **Android**. Vyberte v seznamu šablony **prázdná aplikace (Android)**. Pojmenujte ji **WeatherApp.Android**. 

4. Pokud chcete zacílit univerzální platformu Windows v **nový projekt** dialogovém okně na levém vyberte **Visual C#** a **univerzální pro Windows**. Vyberte v seznamu šablony **prázdná aplikace (univerzální pro Windows)** a pojmenujte ji **WeatherApp.UWP**.
  
5. Pro každou aplikaci projekty (iOS, Android a UWP), klikněte pravým tlačítkem myši **odkazy** v tématu **Průzkumníku řešení** a vyberte **přidat odkaz na**. V **správce odkazů** dialogovém okně na levém vyberte **projektu** a **řešení**. Zobrazí seznam všechny projekty v řešení s výjimkou projektu, jehož odkazy spravujete:

   ![Nastavení odkaz na projekt .NET Standard](../cross-platform/media/cross-plat-xamarin-build-3.png "sestavení Xamarin napříč platformami 3")

   Zaškrtněte políčko vedle **WeatherApp**. 

   Po zaškrtnutí tohoto políčka pro každou z projektů aplikace všechny projekty obsahují odkazy na rozhraní .NET standardní knihovna a můžete sdílet kód v této knihovně.
  
6. Přidat **Newtonsoft.Json** balíček NuGet do projektu .NET Standard, které budete používat ke zpracování informace získané z datové služby počasí:  
  
    -   Klikněte pravým tlačítkem myši **WeatherApp** v projektu **Průzkumníku řešení** a vyberte **spravovat balíčky NuGet...** .  
  
         V okně NuGet, vyberte **Procházet** kartě a vyhledejte **Newtonsoft**.  
  
    -   Vyberte **Newtonsoft.Json**.  
  
    -   Ujistěte se, **verze** pole je nastaveno **nejnovější stabilní** verze.  
  
    -   Klikněte na tlačítko **nainstalovat**.  
  
7.  Opakujte krok 6 vyhledávat a instalovat **Microsoft.CSharp** balíček v .NET Standard projektu. Tato knihovna je nutné k použití jazyka C# `dynamic` typ dat v rozhraní .NET standardní knihovny.
  
8.  Sestavte řešení a ověřte, zda nejsou žádné chyby sestavení.  
  
<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Zápis kódu služby sdílených dat  

 **WeatherApp** projektu je .NET standardní knihovny. Tento projekt je, kde budete psát kód, který je sdílen na všech platformách. Protože každý projekt aplikace obsahuje odkaz na knihovnu .NET Standard, knihovny je součástí systému iOS, Android a UWP balíčky aplikací.  
  
 Následující kroky přidejte do .NET standardní knihovnu, která má přístup a ukládání dat z dané služby počasí kód:  
  
1.  Nejprve si zaregistrovat bezplatnou počasí klíč rozhraní API v [ http://openweathermap.org/appid ](http://openweathermap.org/appid). Tento klíč rozhraní API vám umožní aplikace za účelem získání počasí pro PSČ žádné Spojených státech amerických. (Ale nefunguje pro PSČ mimo Spojené státy.)
  
2.  Klikněte pravým tlačítkem myši **WeatherApp** projektu a vyberte **Přidat > třída...** . V **přidat novou položku** dialogové okno, název souboru **Weather.cs**. Tato třída budete používat k ukládání dat ze služby počasí data.  
  
3.  Nahradí celý obsah **Weather.cs** následujícím kódem:  
  
    ```csharp  
    namespace WeatherApp
    {
        public class Weather
        {
            // Because labels bind to these values, set them to an empty string to
            // ensure that the label appears on all platforms by default.
            public string Title { get; set; } = " ";
            public string Temperature { get; set; } = " ";
            public string Wind { get; set; } = " ";
            public string Humidity { get; set; } = " ";
            public string Visibility { get; set; } = " ";
            public string Sunrise { get; set; } = " ";
            public string Sunset { get; set; } = " ";
        }
    }
    ```  
  
4.  Přidejte jinou třídu do .NET Standard projektu s názvem **DataService.cs**. Tato třída použijete ke zpracování dat JSON ze služby počasí data.  
  
5.  Nahradí celý obsah **DataService.cs** následujícím kódem:  
  
    ```csharp  
    using System.Net.Http;  
    using System.Threading.Tasks;  
    using Newtonsoft.Json;  
  
    namespace WeatherApp  
    {  
        public class DataService  
        {  
            public static async Task<dynamic> GetDataFromService(string queryString)  
            {  
                HttpClient client = new HttpClient();  
                var response = await client.GetAsync(queryString);  
  
                dynamic data = null;  
                if (response != null)  
                {  
                    string json = response.Content.ReadAsStringAsync().Result;  
                    data = JsonConvert.DeserializeObject(json);  
                }  
  
                return data;  
            }  
        }  
    }  
    ```  
  
6.  Přidání třídy třetí do .NET standardní knihovny s názvem **Core.cs**. Tato třída budete používat k formuláři řetězec dotazu s kódem zip, volání služby data počasí a naplnit instanci **počasí** třídy.  
  
7.  Nahraďte obsah **Core.cs** následujícím kódem:  
  
    ```csharp  
    using System;  
    using System.Threading.Tasks;  
  
    namespace WeatherApp  
    {  
        public class Core  
        {  
            public static async Task<Weather> GetWeather(string zipCode)  
            {  
                //Sign up for a free API key at http://openweathermap.org/appid  
                string key = "YOUR API KEY HERE";  
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="  
                    + zipCode + ",us&appid=" + key + "&units=imperial";  

                //Make sure developers running this sample replaced the API key
                if (key == "YOUR API KEY HERE")
                {
                    throw new ArgumentException("You must obtain an API key from openweathermap.org/appid and save it in the 'key' variable.");
                }
  
                dynamic results = await DataService.GetDataFromService(queryString).ConfigureAwait(false);  
  
                if (results["weather"] != null)  
                {  
                    Weather weather = new Weather();  
                    weather.Title = (string)results["name"];                  
                    weather.Temperature = (string)results["main"]["temp"] + " F";  
                    weather.Wind = (string)results["wind"]["speed"] + " mph";                  
                    weather.Humidity = (string)results["main"]["humidity"] + " %";  
                    weather.Visibility = (string)results["weather"][0]["main"];  
  
                    DateTime time = new System.DateTime(1970, 1, 1, 0, 0, 0, 0);  
                    DateTime sunrise = time.AddSeconds((double)results["sys"]["sunrise"]);  
                    DateTime sunset = time.AddSeconds((double)results["sys"]["sunset"]);  
                    weather.Sunrise = sunrise.ToString() + " UTC";  
                    weather.Sunset = sunset.ToString() + " UTC";  
                    return weather;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
        }  
    }  
    ```  
  
8. Nahraďte první výskyt *vaše rozhraní API klíč zde* s klíčem rozhraní API, který jste získali v kroku 1. Je stále nutné uvozovky, do kterých se!
  
9. Odstranit **MyClass.cs** v knihovně .NET standardní vzhledem k tomu, že se nepoužijí.  
  
10. Sestavení **WeatherApp** projektu a zkontrolujte, zda je správný kód.  
  
<a name="Android" />

## <a name="design-ui-for-android"></a>Návrh uživatelského rozhraní pro Android  

 Teď můžete navrhnout uživatelské rozhraní, připojte ho k sdíleného kódu a spusťte aplikaci.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Návrh vzhledu a chování vaší aplikace  
  
1.  V **Průzkumníku řešení**, rozbalte **WeatherApp.Droid > prostředky > rozložení** složky a otevřete **Main.axml**. Tento příkaz otevře soubor v vizuálního návrháře. (Pokud se zobrazí chybě související s Java, najdete [příspěvku na blogu](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)  
  
    > [!TIP]
    >  V projektu nejsou mnoho souborů. Prohlížení je je nad rámec tohoto článku, ale pokud budete chtít do struktury projektu Android trochu další podrobné informace najdete v části [část 2 podrobné informace](/xamarin/android/get-started/hello-android/hello-android-deepdive/) Hello Android článku.  
  
2.  Otevření panelu nástrojů s **zobrazení > jiných Windows > Sada nástrojů**.  
  
3.  Z **sada nástrojů**, přetáhněte ji **RelativeLayout** ovládacího prvku do návrháře. Tento ovládací prvek budete používat jako nadřazený kontejner pro další ovládací prvky.  
  
    > [!TIP]
    >  Pokud kdykoli asi není ke správnému zobrazení rozložení, soubor uložte a přepínání mezi **návrhu** a **zdroj** karet na aktualizovat.  
  
4.  V **vlastnosti** nastavte **pozadí** vlastnost (ve skupině styl) na `#545454`.  Zkontrolujte v záhlaví **vlastnosti** okno, které jste nastavení pozadí **RelativeLayout**.
  
5.  Z **sada nástrojů**, přetáhněte ji **TextView** na ovládací prvek **RelativeLayout** ovládacího prvku.  
  
6.  V **vlastnosti** okno, nastavte tyto vlastnosti. (Může pomoct seřadíte seznam podle abecedy pomocí tlačítka řazení v panelu nástrojů v okně Vlastnosti.):  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Text**|**Vyhledávání podle PSČ**|  
    |**id**|`@+id/ZipCodeSearchLabel`|  
    |**layout_marginStart**|`10dp`|  
    |**TextColor**|`@android:color/white`|  
    |**stylu písma**|`bold`|  
  
    > [!TIP]
    >  Všimněte si, že mnoho vlastností nesmí obsahovat rozevírací seznam hodnot, které můžete vybrat.  Může být obtížné uhodnout jaké řetězcovou hodnotu pro danou vlastnost. Návrhy, zkuste vyhledávání pro název vlastnosti v [R.attr](http://developer.android.com/reference/android/R.attr.html) třídy stránky.  
    >   
    >  Navíc vyhledávání na webu rychlý často vede na stránku [ http://stackoverflow.com/ ](http://stackoverflow.com/) kde ostatní používá stejnou vlastnost.  
  
     Pro odkaz, pokud přejdete na **zdroj** zobrazení, měli byste vidět následující kód pro tento element:  
  
    ```xml  
    <TextView  
        android:text="Search by Zip Code"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:id="@+id/ZipCodeSearchLabel"  
        android:layout_marginStart="10dp"  
        android:textColor="@android:color/white"  
        android:textStyle="bold" />  
  
    ```  
  
7.  Z **sada nástrojů**, přetáhněte **TextView** na ovládací prvek **RelativeLayout** řízení a umístěte jej pod ZipCodeSearchLabel ovládacího prvku. Vyřaďte nový ovládací prvek na příslušné okraji existujícího ovládacího prvku. Pomáhá zvětšení v Návrháři poněkud umístění ovládacího prvku.  
  
8. V **vlastnosti** okno, nastavte tyto vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Text**|**PSČ**|  
    |**id**|`@+id/ZipCodeLabel`|  
    |**layout_marginStart**|`10dp`|  
    |**layout_marginTop**|`6dp`|  
    |**TextColor**|`@android:color/white`|  
  
    Tady je jak kód **zdroj** zobrazení by měl vypadat:  
  
    ```xml  
    <TextView  
        android:text="Zip Code"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/ZipCodeSearchLabel"  
        android:id="@+id/ZipCodeLabel"  
        android:layout_marginStart="10dp"
        android:layout_marginTop="6dp"  
        android:textColor="@android:color/white" />  
    ```  
  
9. Z **sada nástrojů**, přetáhněte **číslo** na ovládací prvek **RelativeLayout**, umístit níže **PSČ** popisek. Nastavte následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**id**|`@+id/zipCodeEntry`|  
    |**layout_marginStart**|`10dp`|  
    |**layout_marginBottom**|`10dp`|  
    |**Šířka**|`165dp`|  
    |**TextColor**|`@android:color/white`|  
  
    **Číslo** ovládací prvek je, kde bude uživatel zadat kód zip Spojených států pět číslic. Zde je kód, který odpovídá u daného ovládacího prvku:  
  
    ```xml  
    <EditText  
        android:inputType="number"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/ZipCodeLabel"  
        android:id="@+id/zipCodeEntry"  
        android:layout_marginStart="10dp"  
        android:layout_marginBottom="10dp"  
        android:width="165dp"  
        android:textColor="@android:color/white" />  
    ```  
  
10. Z **sada nástrojů**, přetáhněte **tlačítko** na **RelativeLayout** řízení a umístit je napravo od ovládacího prvku zipCodeEntry. Nastavte tyto vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**id**|`@+id/weatherBtn`|  
    |**Text**|**Získat informace o počasí**|  
    |**layout_marginStart**|`20dp`|  
    |**layout_alignBottom**|`@id/zipCodeEntry`|  
    |**Šířka**|`165dp`|  
  
    ```xml  
    <Button
        android:text="Get Weather"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_toRightOf="@id/zipCodeEntry"  
        android:id="@+id/weatherBtn"  
        android:layout_marginStart="20dp"  
        android:layout_alignBottom="@id/zipCodeEntry"  
        android:width="165dp" />  
    ```  
  
11. Teď víte, dost pro vytvoření základní uživatelské rozhraní pomocí návrháře Android. Můžete také vytvořit uživatelského rozhraní tak, že přidáte kód přímo do souboru Main.axml stránky. K sestavení rest uživatelského rozhraní, která způsobem, přepněte do zobrazení zdroje v návrháři a potom vložte následující kód *pod* `</RelativeLayout>` ukončovací značku. (Musí být ve značce, protože tyto prvky jsou *není* součástí `RelativeLayout`.)  
  
    ```xml  
    <TextView  
        android:text="Location"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/locationLabel"  
        android:layout_marginStart="10dp"  
        android:layout_marginTop="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/locationText"  
        android:layout_marginStart="20dp"  
        android:layout_marginBottom="10dp" />  
    <TextView  
        android:text="Temperature"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/tempLabel"  
        android:layout_marginStart="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/tempText"  
        android:layout_marginBottom="10dp"  
        android:layout_marginStart="20dp" />  
    <TextView  
        android:text="Wind Speed"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/windLabel"  
        android:layout_marginStart="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/windText"  
        android:layout_marginBottom="10dp"  
        android:layout_marginStart="20dp" />  
    <TextView  
        android:text="Humidity"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/humidtyLabel"  
        android:layout_marginStart="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/humidityText"  
        android:layout_marginBottom="10dp"  
        android:layout_marginStart="20dp" />  
    <TextView  
        android:text="Visibility"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/visibilityLabel"  
        android:layout_marginStart="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/visibilityText"  
        android:layout_marginBottom="10dp"  
        android:layout_marginStart="20dp" />  
    <TextView  
        android:text="Time of Sunrise"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/sunriseLabel"  
        android:layout_marginStart="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/sunriseText"  
        android:layout_marginBottom="10dp"  
        android:layout_marginStart="20dp" />  
    <TextView  
        android:text="Time of Sunset"  
        android:textAppearance="?android:attr/textAppearanceSmall"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/sunsetLabel"  
        android:layout_marginStart="10dp" />  
    <TextView  
        android:textAppearance="?android:attr/textAppearanceMedium"  
        android:layout_width="match_parent"  
        android:layout_height="wrap_content"  
        android:id="@+id/sunsetText"  
        android:layout_marginBottom="10dp"  
        android:layout_marginStart="20dp" />  
    ```  
  
12. Uložte tento soubor a přepněte do **návrhu** zobrazení. Uživatelské rozhraní by měl vypadat takto:  
  
     ![Uživatelské rozhraní pro aplikace pro Android](../cross-platform/media/xamarin_androidui.png "Xamarin_AndroidUI")  
  
13. Otevřete **MainActivity.cs**. Zde je, jak by měla vypadat kód:  
  
    ```  
    protected override void OnCreate (Bundle bundle)  
    {  
        base.OnCreate (bundle);  
  
        // Set our view from the "main" layout resource  
        SetContentView (Resource.Layout.Main);  
    }  
    ```  
  
14. Sestavení projektu pro Android zkontrolujte vaši práci. Proces sestavení přidá ID ovládacích prvků do **Resource.Designer.cs** tak, aby mohou odkazovat na ovládací prvky podle názvu v kódu.  
  
### <a name="consume-your-shared-code"></a>Využívat sdílené kódu  
  
1.  Otevřete **MainActivity.cs** soubor **WeatherApp** projektu v editoru kódu a nahraďte jeho obsah pomocí kódu níže. Tento kód zavolá `GetWeather` metoda, která jste definovali ve vašem sdíleného kódu. Poté v uživatelském rozhraní aplikace zobrazuje data, která se načítají z dané metody.  
  
    ```csharp  
    using System;  
    using Android.App;  
    using Android.Widget;  
    using Android.OS;  
  
    namespace WeatherApp.Droid  
    {  
        [Activity(Label = "Sample Weather App", 
                  Theme = "@android:style/Theme.Material.Light", 
                  MainLauncher = true)]  
        public class MainActivity : Activity  
        {  
            protected override void OnCreate(Bundle bundle)  
            {  
                base.OnCreate(bundle);  
  
                SetContentView(Resource.Layout.Main);  
  
                Button button = FindViewById<Button>(Resource.Id.weatherBtn);  
  
                button.Click += Button_Click;  
            }  
  
            private async void Button_Click(object sender, EventArgs e)  
            {  
                EditText zipCodeEntry = FindViewById<EditText>(Resource.Id.zipCodeEntry);  
  
                if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
                {  
                    Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
                    FindViewById<TextView>(Resource.Id.locationText).Text = weather.Title;  
                    FindViewById<TextView>(Resource.Id.tempText).Text = weather.Temperature;  
                    FindViewById<TextView>(Resource.Id.windText).Text = weather.Wind;  
                    FindViewById<TextView>(Resource.Id.visibilityText).Text = weather.Visibility;  
                    FindViewById<TextView>(Resource.Id.humidityText).Text = weather.Humidity;  
                    FindViewById<TextView>(Resource.Id.sunriseText).Text = weather.Sunrise;  
                    FindViewById<TextView>(Resource.Id.sunsetText).Text = weather.Sunset;  
                }  
            }  
        }  
    }  
    ```  

    Všimněte si, že Aktivita nebyla zadána motiv světla pozadí.
  
### <a name="run-the-app-and-see-how-it-looks"></a>Spusťte aplikaci a v tématu Jak vypadá  
  
1.  V **Průzkumníku řešení**, zajistěte, aby **WeatherApp.Droid** projektu je nastavit jako spouštěný projekt.  
  
2.  Vyberte příslušné zařízení nebo emulátoru target a pak spusťte aplikaci stisknutím klávesy F5.  

    > [!NOTE]
    > Pokud Visual Studio znamená, že projektu pro Android nemůže najít soubor Newtonsoft.Json, přidejte tento balíček NuGet do projektu pro Android. 
  
3.  Na zařízení nebo v emulátoru, zadejte do textového pole a stiskněte klávesu platné PSČ Spojených států pět číslic **získat počasí**. Potom se data počasí pro danou oblast zobrazí v ovládacích prvcích.  
  
    [![Aplikace Xamarin pro Android](../cross-platform/media/cross-plat-xamarin-build-1-android.png "Android sestavení Xamarin Cross-Plat 1")](../cross-platform/media/cross-plat-xamarin-build-1-android-Large.png#lightbox)  
  
> [!TIP]
>  Úplný zdrojový kód pro tento projekt je v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).  
  
<a name="Windows" /> 

## <a name="design-ui-for-windows"></a>Návrh uživatelského rozhraní pro Windows

Dalším krokem je návrh uživatelského rozhraní pro Windows, připojte ho k sdíleného kódu a pak spusťte aplikaci.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Návrh vzhledu a chování vaší aplikace  

 Proces návrhu nativní UWP uživatelské rozhraní v aplikaci Xamarin se neliší od jiných nativní aplikaci UWP. Z tohoto důvodu nebude tady popisovaných použití návrháře. Podrobné informace, najdete v části [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
 Místo toho otevřete **MainPage.xaml** a nahraďte celý obsah XAML následující kód:   
  
```xaml  
<Page
    x:Class="WeatherApp.UWP.MainPage"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:local="using:WeatherApp.UWP"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    mc:Ignorable="d">

    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">

        <StackPanel HorizontalAlignment="Left" 
                    VerticalAlignment="Top" 
                    Height="40" Margin="10,0,0,0" Width="400">
            <TextBlock Text="Weather App" FontSize="30" />
        </StackPanel>
        <StackPanel HorizontalAlignment="Left" 
                    VerticalAlignment="Top" 
                    Height="120" Margin="10,40,0,0" Width="400" 
                    Background="#FF545454">

            <TextBlock Text="Search by Zip Code" TextWrapping="Wrap" 
                       HorizontalAlignment="Left" Margin="10,10,0,0"
                       Foreground="White" FontSize="18" FontWeight="Bold" />
            
            <TextBlock Text="Zip Code" TextWrapping="Wrap" 
                       Margin="10,5,0,0" FontSize="14" Foreground="#FFA8A8A8"/>
            
            <StackPanel Orientation="Horizontal">

                <TextBox x:Name="zipCodeEntry" Text="" 
                         Margin="10,10,0,0" VerticalAlignment="Top" 
                         InputScope="Number" Width="165" />
                
                <Button x:Name="weatherBtn" Content="Get Weather" 
                        Foreground="White" Width="165" Margin="20,0,0,0" Height="60" 
                        Click="GetWeatherButton_Click"/>
            </StackPanel>
        </StackPanel>
        
        <StackPanel Margin="10,175,0,0">
            <StackPanel.Resources>
                <Style x:Key="commonText" TargetType="TextBlock">
                    <Setter Property="HorizontalAlignment" Value="Left" />
                    <Setter Property="VerticalAlignment" Value="Top" />
                    <Setter Property="TextWrapping" Value="Wrap" />
                </Style>
                
                <Style x:Key="labelText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="14" />
                    <Setter Property="Foreground" Value="#FFA8A8A8" />
                </Style>

                <Style x:Key="valueText" TargetType="TextBlock" BasedOn="{StaticResource commonText}">
                    <Setter Property="FontSize" Value="18" />
                    <Setter Property="Margin" Value="10, 0, 0, 10" />
                </Style>
            </StackPanel.Resources>
            
            <TextBlock Text="Location" Style="{StaticResource labelText}" />
            <TextBlock x:Name="locationText" Style="{StaticResource valueText}" />

            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="tempText" Style="{StaticResource valueText}" />
            
            <TextBlock Text="Wind Speed" Style="{StaticResource labelText}" />
            <TextBlock x:Name="windText" Style="{StaticResource valueText}" />
            
            <TextBlock Text="Humidity" Style="{StaticResource labelText}" />
            <TextBlock x:Name="humidityText" Style="{StaticResource valueText}" />
            
            <TextBlock Text="Temperature" Style="{StaticResource labelText}" />
            <TextBlock x:Name="visibilityText" Style="{StaticResource valueText}" />
            
            <TextBlock Text="Time of Sunrise" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunriseText" Style="{StaticResource valueText}" />
            
            <TextBlock Text="Time of Sunset" Style="{StaticResource labelText}" />
            <TextBlock x:Name="sunsetText" Style="{StaticResource valueText}" />
        </StackPanel>
    </Grid>
</Page>
```  
  
### <a name="consume-your-shared-code"></a>Využívat sdílené kódu  
  
V **MainPage.xaml.cs** kódu soubor, přidejte následující obslužné rutiny události pro tlačítko: 
  
```csharp  
private async void GetWeatherButton_Click(object sender, RoutedEventArgs e)  
{  
    if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
    {  
        Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
        locationText.Text = weather.Title;  
        tempText.Text = weather.Temperature;  
        windText.Text = weather.Wind;  
        visibilityText.Text = weather.Visibility;  
        humidityText.Text = weather.Humidity;  
        sunriseText.Text = weather.Sunrise;  
        sunsetText.Text = weather.Sunset;  

        weatherBtn.Content = "Search Again";  
    }  
}  
```  
  
Tento kód zavolá `GetWeather` metoda, která jste definovali ve vašem sdíleného kódu. `GetWeather` je stejnou metodu, kterou jste volali metodu v aplikacích pro Android. Tento kód také ukazuje data načtená z dané metody v ovládacích prvků uživatelského rozhraní aplikace.  
  
### <a name="run-the-app-and-see-how-it-looks"></a>Spusťte aplikaci a v tématu Jak vypadá  
  
1.  V **Průzkumníku řešení**, nastavte **WeatherApp.UWP** projekt jako spouštěný projekt.  

2.  V **platformy řešení** rozevíracím, vyberte **x86** a vyberte **místního počítače** k nasazení aplikace pro Windows 10 desktop.
  
3.  Spusťte aplikaci stisknutím klávesy F5.  
  
4.  Zadejte platné PSČ pět číslic Spojených států do textového pole a stiskněte klávesu **získat počasí**. Data o počasí pro danou oblast se pak zobrazí na stránce.  

    [![Aplikace Xamarin na UWP](../cross-platform/media/cross-plat-xamarin-build-1-uwp.png "UWP sestavení Xamarin Cross-Plat 1")](../cross-platform/media/cross-plat-xamarin-build-1-uwp-Large.png#lightbox)  

> [!TIP]
>  Úplný zdrojový kód pro tento projekt je v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).  

<a name="next" /> 

## <a name="next-steps"></a>Další kroky  

 **Do řešení přidat uživatelského rozhraní pro iOS**  
  
 Tato ukázka rozšiřte přidáním nativní uživatelského rozhraní pro iOS. K testování kódu v systému iOS, budete muset připojit na Mac ve vaší místní síti, která má Xcode a Xamarin nainstalován. Jakmile to uděláte, můžete použít Návrháře iOS přímo v sadě Visual Studio. Najdete v článku [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather) pro dokončené aplikace.  
  
 Najdete také [Hello, iOS](/xamarin/ios/get-started/hello-ios/hello-ios-quickstart?tabs=vswin) návod.   
  
 **Přidání kódu pro konkrétní platformu v sdílený projekt**  
  
 Sdílené kód v knihovně .NET Standard je platforma jazykově neutrální. Knihovny je kompilovat jednou a součástí každého balíčku aplikace specifické pro platformu. Pokud chcete napsat sdílené kód, který používá Podmíněná kompilace izolovat kódu pro konkrétní platformu, můžete použít *sdílené* projektu. Další informace najdete v tématu [možnosti sdílení kódu](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/practical-code-sharing-strategies).  
  
## <a name="see-also"></a>Viz také  

 [Xamarin dokumentace](http://docs.microsoft.com/xamarin)   
 [Centrum vývojářů pro Windows](https://dev.windows.com/en-us)   
 [Stručná referenční příručka plakát SWIFT a C#](http://aka.ms/scposter)
