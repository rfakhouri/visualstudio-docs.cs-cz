---
title: Vytvářejte aplikace s nativním uživatelským rozhraním pomocí Xamarinu v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
author: conceptdev
ms.author: crdun
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: b68dd62de137e3c9427715c647ba4a53f07bd281
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2018
ms.locfileid: "46496152"
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Vytváření aplikací s nativním uživatelským rozhraním pomocí Xamarinu v sadě Visual Studio

Většina vývojářů, kteří se rozhodnou Xamarinu a C# pro vytváření multiplatformních mobilních aplikací pomocí Xamarin.Forms. Xamarin.Forms definuje uživatelské rozhraní, který se mapuje na nativní ovládací prvky v iOS, Android a univerzální platformu Windows (UPW). Xamarin.Forms je popsaný v článku [základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

Tento článek popisuje jiný přístup, který zahrnuje přístup k rozhraní API nativního uživatelského rozhraní pro každou platformu. Práce s nativním rozhraním API je mnohem obtížnější přístup než Xamarin.Forms, protože vyžaduje rozsáhlé znalosti jednotlivých platforem. Výhodou je, že můžete přizpůsobit uživatelské rozhraní pro určité výhody a možnosti pro každou platformu, při stále sdílení obchodní logiku.

Jakmile jste udělali kroky [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověření prostředí Xamarinu](../cross-platform/verify-your-xamarin-environment.md), tento návod ukazuje, jak vytvořit základní aplikaci Xamarin pomocí nativní vrstvy uživatelského rozhraní. S nativním uživatelským rozhraním sdílený kód se nachází v knihovně .NET Standard a projekty jednotlivé platformy obsahují definice uživatelského rozhraní. Tady je aplikace, které vytvoříte (zleva doprava) a systémem iOS a telefony s Androidem a Windows 10 desktop.

![Aplikace Xamarin iOS, Android a Windows](../cross-platform/media/cross-plat-xamarin-build-1-Large.png#lightbox)

Můžete udělat Tyhle věci na jejich vytváření:

- [Nastavení řešení](#solution)

- [Zápis kódu služby sdílená data](#dataservice)

- [Návrh uživatelského rozhraní pro Android](#Android)

- [Návrh uživatelského rozhraní pro Windows](#Windows)

- [Další kroky](#next), mezi které patří navrhování uživatelského rozhraní iOS

> [!TIP]
> Najdete kompletní zdrojový kód pro tento projekt v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
> Pokud máte potíže nebo dochází k chybám, zveřejněte ji prosím dotazy na [forums.xamarin.com](http://forums.xamarin.com). Mnoho chyb se dají vyřešit aktualizaci na nejnovější sady SDK vyžadované Xamarin, které jsou popsány v [zpráva k vydání verze Xamarinu](https://developer.xamarin.com/releases/) pro každou platformu.

> [!NOTE]
> Dokumentaci pro vývojáře Xamarinu pro několik kurzy rychlý start a podrobné informace o části nabízí také, jak je uvedeno níže. Na těchto stránkách Ujistěte se, že je vybraná "Visual Studio" zobrazíte návody, které jsou specifické pro Visual Studio.
>
>  -   Aplikace Xamarin s nativním uživatelským rozhraním:
>     -   [Hello, Android](/xamarin/android/get-started/hello-android/) (jednoduché aplikace s jednou obrazovkou)
>     -   [Hello, Android s více obrazovkami](/xamarin/android/get-started/hello-android-multiscreen/) (aplikace s navigace mezi obrazovkami)
>     -   [Návod s androidem fragmenty](/xamarin/android/platform/fragments/implementing-with-fragments/) (používá se pro obrazovky záznamů master/detail, mimo jiné)
>     -   [Hello, iOS](/xamarin/ios/get-started/hello-iOS/)
>     -   [Hello, iOS s více obrazovkami](/xamarin/ios/get-started/hello-iOS-multiscreen/)

>  -   Aplikace Xamarin s Xamarin.Forms (sdílené uživatelské rozhraní)
>     -   [Hello, Xamarin.Forms](/xamarin/xamarin-forms/get-started/hello-xamarin-forms/quickstart/)
>     -   [Hello, Xamarin.Forms s více obrazovkami](/xamarin/xamarin-forms/get-started/hello-xamarin-forms-multiscreen/)

<a name="solution" />

##  <a name="set-up-your-solution"></a>Nastavení řešení

Visual Studio nemá šablonu řešení pro vytváření aplikací pro nativní uživatelské rozhraní sdílení knihovny .NET Standard. Není však obtížné k vytvoření řešení z jednotlivých projektů. Tyto kroky vytvoří Xamarin řešení s projekty pro každý typ aplikační platformy a knihovny .NET Standard pro sdílený kód.

1.  V sadě Visual Studio vytvořte nový **knihovna tříd (.NET Standard)** řešení a pojmenujte ho **WeatherApp**. Tuto šablonu lze najít nejsnadněji tak, že vyberete **Visual C#** na levé straně a pak **.NET Standard**:

    ![Vytvoření řešení .NET Standard](../cross-platform/media/cross-plat-xamarin-build-2.png)

    Po kliknutí na tlačítko OK, **WeatherApp** řešení se skládá z jednoho projektu s názvem **WeatherApp**.

2.  Pokud chcete do cílového systému iOS, přidejte do řešení projekt iOS. Klikněte pravým tlačítkem na název řešení v **Průzkumníka řešení** a vyberte **přidat** a **nový projekt**.  V **nový projekt** dialogovém okně na levém vyberte **Visual C#** a potom **iOS** a **univerzální**. (Pokud tam není, bude pravděpodobně nutné nainstalujte si Xamarin, nebo povolte funkce sady Visual Studio 2017, najdete v článku [nastavení a instalaci](../cross-platform/setup-and-install.md).) V seznamu šablon vyberte **aplikace s jedním zobrazením (iOS)**. Pojmenujte ji **WeatherApp.iOS**.

3.  Pokud chcete cílit na Android, přidejte do řešení projekt pro Android. V **nový projekt** dialogovém okně na levém vyberte **Visual C#** a **Android**. V seznamu šablon vyberte **prázdná aplikace (Android)**. Pojmenujte ji **WeatherApp.Android**.

4. Pokud chcete cílit na univerzální platformu Windows v **nový projekt** dialogovém okně na levém vyberte **Visual C#** a **Windows Universal**. V seznamu šablon vyberte **prázdná aplikace (Universal Windows)** a pojmenujte ho **WeatherApp.UWP**.

5. Pro každou aplikaci projekty (iOS, Android a UPW), klikněte pravým tlačítkem na **odkazy** tématu **Průzkumníka řešení** a vyberte **přidat odkaz**. V **správce odkazů** dialogovém okně na levém vyberte **projektu** a **řešení**. Zobrazí seznam všech projektů v řešení kromě projektu, jejichž odkazy spravujete:

   ![Nastavení odkazu na projekt .NET Standard](../cross-platform/media/cross-plat-xamarin-build-3.png)

   Zaškrtněte políčko vedle **WeatherApp**.

   Po zaškrtnutí tohoto políčka pro každou z projektů aplikace všechny projekty obsahují odkazy na knihovny .NET Standard a sdílení kódu v této knihovně.

6. Přidat **Newtonsoft.Json** balíček NuGet pro projekt .NET Standard, které budete používat ke zpracování informace načtenými z datové služby weather:

    -   Klikněte pravým tlačítkem myši **WeatherApp** projekt **Průzkumníka řešení** a vyberte **spravovat balíčky NuGet...** .

         V okně NuGet vyberte **Procházet** kartu a vyhledejte **Newtonsoft**.

    -   Vyberte **Newtonsoft.Json**.

    -   Zkontrolujte **verze** pole se nastaví **nejnovější stabilní verze** verze.

    -   Klikněte na tlačítko **nainstalovat**.

7.  Opakujte krok 6 najít a nainstalovat **Microsoft.CSharp obsahují třídy** balíčky v projektu .NET Standard. Tato knihovna je potřeba použít jazyk C# `dynamic` datový typ v knihovně .NET Standard.

8.  Sestavte řešení a ověřte, že zde nejsou žádné chyby buildu.

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Zápis kódu služby sdílená data

 **WeatherApp** je projekt knihovny .NET Standard. Tento projekt je, kde budete psát kód, který se sdílí mezi všemi platformami. Protože každý projekt aplikace obsahuje odkaz na knihovny .NET Standard, jsou zahrnuty v iOS, Android a UPW knihovny balíčky aplikací.

 Takto přidejte kód do knihovny .NET Standard pro přístup a ukládání dat z této služby weather:

1.  Nejdřív zaregistrovat bezplatnou počasí klíč rozhraní API na [ http://openweathermap.org/appid ](http://openweathermap.org/appid). Tento klíč rozhraní API vám umožní aplikace za účelem získání počasí pro všechny poštovní směrovací číslo USA. (To nebude fungovat pro PSČ mimo Spojené státy.)

2.  Klikněte pravým tlačítkem myši **WeatherApp** projektu a vyberte **Přidat > třída...** . V **přidat novou položku** dialogového okna, název souboru *Weather.cs*. Tato třída budete používat k ukládání dat ze služby data o počasí.

3.  Nahradí celý obsah *Weather.cs* následujícím kódem:

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

4.  Přidejte další třídu pro projekt .NET Standard s názvem `DataService.cs`. Tato třída budete používat ke zpracování dat JSON z datové služby počasí.

5.  Nahradí celý obsah *DataService.cs* následujícím kódem:

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

6.  Přidat třetí třídy do knihovny .NET Standard s názvem *Core.cs*. Použijete tvoří řetězec dotazu s PSČ, volání služby data o počasí a naplnit instanci této třídy **počasí** třídy.

7.  Nahraďte obsah *Core.cs* následujícím kódem:

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

8. Nahraďte první výskyt *vaše rozhraní API KEY zde* s klíčem rozhraní API, který jste získali v kroku 1. Stále potřebuje kolem něj uvozovky!

9. Odstranit *MyClass.cs* v knihovně .NET Standard vzhledem k tomu, že se nepoužije.

10. Sestavení **WeatherApp** projektu, abyste měli jistotu, kód je správný.

<a name="Android" />

## <a name="design-ui-for-android"></a>Návrh uživatelského rozhraní pro Android

 Nyní lze navrhnout uživatelské rozhraní, připojte ho ke sdílenému kódu a pak spusťte aplikaci.

### <a name="design-the-look-and-feel-of-your-app"></a>Navrhnout vzhled a chování vaší aplikace

1.  V **Průzkumníka řešení**, rozbalte **WeatherApp.Droid > prostředky > rozložení** složky a otevřete *Main.axml*. Tento příkaz otevře soubor v vizuálního návrháře. (Pokud se zobrazí chybu s jazykem Java, najdete v tomto [blogový příspěvek](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)

    > [!TIP]
    >  V projektu je mnoho dalších souborů. Zkoumání jejich je nad rámec tohoto článku, ale pokud budete chtít věnovat struktura projekt pro Android o trochu výkonnější, naleznete v tématu [podrobné informace o části 2](/xamarin/android/get-started/hello-android/hello-android-deepdive/) Hello Android článku.

2.  Otevřete sadu nástrojů s **zobrazení > ostatní Windows > Sada nástrojů**.

3.  Z **nástrojů**, přetáhněte **RelativeLayout** ovládacího prvku do návrháře. Tento ovládací prvek budete používat jako nadřazený kontejner pro ostatní ovládací prvky.

    > [!TIP]
    >  Pokud v každém okamžiku zřejmě není ke správnému zobrazení rozložení, uložte soubor a přepínání mezi **návrhu** a **zdroj** karty aktualizovat.

4.  V **vlastnosti** okno, nastaveno **pozadí** vlastnosti (ve skupině styl) `#545454`.  Ujistěte se, že v záhlaví **vlastnosti** okno, které nastavujete pozadí **RelativeLayout**.

5.  Z **nástrojů**, přetáhněte **TextView** na ovládací prvek **RelativeLayout** ovládacího prvku.

6.  V **vlastnosti** okno, nastavte tyto vlastnosti. (Může být snazší seřadíte seznam podle abecedy pomocí tlačítka řazení v panelu nástrojů okna Vlastnosti.):

    |Vlastnost|Hodnota|
    |--------------|-----------|
    |**Text**|**Hledat podle PSČ**|
    |**id**|`@+id/ZipCodeSearchLabel`|
    |**layout_marginStart**|`10dp`|
    |**TextColor**|`@android:color/white`|
    |**stylu textu**|`bold`|

    > [!TIP]
    >  Všimněte si, že mnoho vlastností neobsahují rozevírací seznam hodnot, které můžete vybrat.  Může být obtížné odhadnout jaké řetězcovou hodnotu pro jakékoli dané vlastnosti. Máte nějaké návrhy, zkuste najít, název vlastnosti v [ `R.attr` ](http://developer.android.com/reference/android/R.attr.html) třídy stránky.
    >
    >  Navíc rychlé webové vyhledávání často vede na stránku [ http://stackoverflow.com/ ](http://stackoverflow.com/) kde ostatní používá stejnou vlastnost.

     Pro srovnání, pokud přejdete na **zdroj** zobrazení, byste měli vidět následující kód pro tento element:

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

7.  Z **nástrojů**, přetáhněte **TextView** na ovládací prvek **RelativeLayout** ovládací prvek a jeho umístěním pod ovládacím prvkem ZipCodeSearchLabel. Vyřaďte nový ovládací prvek na odpovídající okraji existujícího ovládacího prvku. Pomáhá přiblížit návrháře trochu umístění ovládacího prvku.

8. V **vlastnosti** okno, nastavte tyto vlastnosti:

    |Vlastnost|Hodnota|
    |--------------|-----------|
    |**Text**|**PSČ**|
    |**id**|`@+id/ZipCodeLabel`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginTop**|`6dp`|
    |**TextColor**|`@android:color/white`|

    Tady je způsob kód v **zdroj** zobrazení by měl vypadat:

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

9. Z **nástrojů**, přetáhněte **číslo** na ovládací prvek **RelativeLayout**, umístěte níže **PSČ** popisek. Potom nastavte následující vlastnosti:

    |Vlastnost|Hodnota|
    |--------------|-----------|
    |**id**|`@+id/zipCodeEntry`|
    |**layout_marginStart**|`10dp`|
    |**layout_marginBottom**|`10dp`|
    |**Šířka**|`165dp`|
    |**TextColor**|`@android:color/white`|

    **Číslo** je ovládací prvek, kde uživatel zadá PSČ USA pět číslic. Toto je zápis, která odpovídá daného ovládacího prvku:

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

10. Z **nástrojů**, přetáhněte **tlačítko** na **RelativeLayout** řídit a umístit je napravo od ovládacího prvku zipCodeEntry. Nastavte tyto vlastnosti:

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

11. Můžete teď mít dost informací k sestavení základní uživatelské rozhraní pomocí návrháře pro Android. Můžete také vytvořit uživatelské rozhraní tak, že přidáte kód přímo *Main.axml* souboru stránky. K sestavení rest uživatelského rozhraní, přepněte do zobrazení zdroje v návrháři a potom vložte následující kód *pod* `</RelativeLayout>` koncová značka. (Musí být pod značku, protože tyto prvky jsou *není* součástí `RelativeLayout`.)

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

12. Uložte soubor a přepněte do **návrhu** zobrazení. Vaše uživatelské rozhraní by měl vypadat takto:

     ![Uživatelské rozhraní pro aplikace pro Android](../cross-platform/media/xamarin_androidui.png)

13. Otevřít **MainActivity.cs**. Zde je, jak by měl vypadat kód:

    ```csharp
    protected override void OnCreate (Bundle bundle)
    {
        base.OnCreate (bundle);

        // Set our view from the "main" layout resource
        SetContentView (Resource.Layout.Main);
    }
    ```

14. Vytvoření projektu pro Android ke kontrole vaší práce. Proces sestavení přidá ID ovládacích prvků na *Resource.Designer.cs nejde* souboru tak, aby mohou odkazovat na ovládací prvky podle názvu v kódu.

### <a name="consume-your-shared-code"></a>Používat sdílený kód

1.  Otevřít *MainActivity.cs* soubor **WeatherApp** projektu v editoru kódu a jeho obsah nahraďte následujícím kódem. Tento kód volá `GetWeather` metodu, která jste definovali v svým sdíleným kódem. Poté v Uživatelském rozhraní aplikace zobrazuje data, která je načten z metody.

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

    Všimněte si, že aktivita bylo přiděleno motiv světlý pozadí.

### <a name="run-the-app-and-see-how-it-looks"></a>Spusťte aplikaci a zjistit, jak to funguje

1.  V **Průzkumníka řešení**, ujistěte se, že **WeatherApp.Droid** projektu je nastavit jako spouštěný projekt.

2.  Vyberte příslušné zařízení nebo emulátoru cílové a pak spusťte aplikaci stisknutím klávesy F5.

    > [!NOTE]
    > Pokud Visual Studio znamená, že projekt pro Android nemůže najít soubor Newtonsoft.Json, přidejte balíček NuGet do projektu pro Android.

3.  Na zařízení nebo emulátor, zadejte platné PSČ USA pět číslic do textového pole a stiskněte klávesu **získat počasí**. Data o počasí v dané oblasti se pak objeví v ovládacích prvcích.

    [![Aplikace Xamarin v systému Android](../cross-platform/media/cross-plat-xamarin-build-1-android.png)](../cross-platform/media/cross-plat-xamarin-build-1-android-Large.png#lightbox)

> [!TIP]
>  Úplný zdrojový kód pro tento projekt je v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).

<a name="Windows" />

## <a name="design-ui-for-windows"></a>Návrh uživatelského rozhraní pro Windows

Dalším krokem je návrh uživatelského rozhraní pro Windows, připojte ho ke sdílenému kódu a pak spusťte aplikaci.

### <a name="design-the-look-and-feel-of-your-app"></a>Navrhnout vzhled a chování vaší aplikace

 Proces návrhu nativní uživatelské rozhraní UWP v aplikaci Xamarin se nijak neliší od jakékoli jiné nativní aplikace pro UPW. Z tohoto důvodu nebude tady popisovaných použití návrháře. Podrobné informace najdete v tématu [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).

 Místo toho otevřít *MainPage.xaml* a nahraďte celý obsah XAML následujícím kódem:

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

### <a name="consume-your-shared-code"></a>Používat sdílený kód

V *MainPage.xaml.cs* použití modelu code-behind souboru, přidejte následující obslužnou rutinu události pro tlačítko:

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

Tento kód volá `GetWeather` metodu, která jste definovali v svým sdíleným kódem. `GetWeather` je stejnou metodu, která je volána v aplikaci pro Android. Tento kód také ukazuje dat načtených z této metody v ovládacích prvcích uživatelského rozhraní aplikace.

### <a name="run-the-app-and-see-how-it-looks"></a>Spusťte aplikaci a zjistit, jak to funguje

1.  V **Průzkumníka řešení**, nastavte **WeatherApp.UWP** projekt jako spouštěný projekt.

2.  V **platformy řešení** rozevíracím seznamu vyberte **x86** a vyberte **místního počítače** k nasazení aplikace pro Windows 10 desktop.

3.  Spusťte aplikaci stisknutím klávesy **F5** klíč.

4.  Zadejte platné PSČ. pět číslic USA do textového pole a stiskněte klávesu **získat počasí**. Na stránce se pak zobrazí data o počasí v dané oblasti.

    [![Aplikace Xamarin na UPW](../cross-platform/media/cross-plat-xamarin-build-1-uwp.png)](../cross-platform/media/cross-plat-xamarin-build-1-uwp-Large.png#lightbox)

> [!TIP]
>  Úplný zdrojový kód pro tento projekt je v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).

<a name="next" />

## <a name="next-steps"></a>Další kroky

 **Do řešení přidat uživatelského rozhraní pro iOS**

 Tuto ukázku rozšiřte přidáním nativní uživatelské rozhraní pro iOS. K testování kódu v systému iOS, bude nutné se připojit k počítači Mac ve vaší místní síti, která má Xcode a Xamarin nainstalovat. Jakmile to uděláte, můžete použít Návrháře iOS přímo v sadě Visual Studio. Najdete v článku [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather) pro dokončené aplikace.

 Také odkazovat [Hello, iOS](/xamarin/ios/get-started/hello-ios/hello-ios-quickstart?tabs=vswin) návodu.

 **Přidat kód specifický pro platformu ve sdíleném projektu**

 Sdílený kód do knihovny .NET Standard je nezávislá na platformě. Knihovny je zkompilován jednou a součástí každý balíček aplikace pro konkrétní platformu. Pokud chcete zapisovat sdílený kód, který používá podmíněné kompilace izolovat platformě závislého kódu, můžete použít *sdílené* projektu. Další informace najdete v tématu [možnosti sdílení kódu](/xamarin/cross-platform/app-fundamentals/building-cross-platform-applications/practical-code-sharing-strategies).

## <a name="see-also"></a>Viz také:

- [Dokumentace k Xamarinu](http://docs.microsoft.com/xamarin)
- [Windows Dev Center](https://dev.windows.com/en-us)
- [Stručná referenční příručka plakát SWIFT a C#](http://aka.ms/scposter)
