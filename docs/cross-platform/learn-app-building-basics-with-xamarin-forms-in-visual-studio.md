---
title: Základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
ms.prod: visual-studio-dev15
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: f9f233b5f43555f86f0a49c5e5853cad6d7456b1
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924421"
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio

Jakmile jste udělali kroky [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověření prostředí Xamarinu](../cross-platform/verify-your-xamarin-environment.md), tento návod ukazuje, jak vytvořit základní aplikaci s Xamarin.Forms. Pomocí Xamarin.Forms napíšete všech kódů uživatelského rozhraní jednou v knihovně tříd .NET Standard. Xamarin se pak automaticky generují nativní ovládací prvky uživatelského rozhraní pro iOS, Android a Windows Universal platformy.

To je obvykle vhodnější použít knihovny .NET Standard, spíše než sdílený projekt pro tento společný kód. Knihovny .NET Standard zahrnuje těchto rozhraní API pro .NET, které můžou běžet na všechny cílové platformy.

Tady je aplikace, která vytvoříte. (Zleva doprava) běží na iOS a telefony s Androidem a Universal Windows Platform (UWP) Windows 10:

[![Ukázkové aplikace o počasí v iOS, Android a UPW](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)

Provedete tyto kroky k vytvoření této aplikace:

-   [Nastavení řešení](#solution)

-   [Zápis kódu služby sdílená data](#dataservice)

-   [Začněte psát sdíleným kódem uživatelského rozhraní](#uicode)

-   [Testování aplikace pomocí emulátoru Visual Studia pro Android](#test)

-   [Dokončení uživatelského rozhraní pomocí přirozený vzhled a chování napříč platformami](#finish)

> [!TIP]
> Najdete kompletní zdrojový kód pro tento projekt v [ukázky xamarin forms úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).

<a name="solution" />

## <a name="set-up-your-solution"></a>Nastavení řešení

Tyto kroky vytvoří řešení Xamarin.Forms, které obsahuje knihovnu tříd .NET Standard pro sdílený kód a dva balíčky NuGet pro přidání.

1. V sadě Visual Studio vytvořte nový **Cross-Platform App (Xamarin.Forms)** řešení a pojmenujte ho **WeatherApp**. Vyhledejte šablonu tak, že vyberete **Visual C#** a **Cross-Platform** ze seznamu na levé straně.

    ![Vytvoření nového projektu aplikace pro různé platformy Xamarin.Forms](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

    Pokud není šablona, bude pravděpodobně nainstalujte si Xamarin, nebo povolte funkce sady Visual Studio 2017. Zobrazit [nastavení a instalaci](../cross-platform/setup-and-install.md).

2.  Po kliknutí na tlačítko OK, budete mít možnost vybrat několik možností. Vyberte si **prázdná aplikace** a **.NET Standard**:

    ![Vytvoření nového projektu aplikace pro různé platformy](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")

3.  Po kliknutí na tlačítko OK, abyste vytvořili řešení, budete mít řešení se čtyřmi projekty:

    -   **WeatherApp**: knihovny .NET Standard, kde budete psát kód, který je sdílen napříč platformami, včetně běžné obchodní logiky a kód uživatelského rozhraní pomocí Xamarin.Forms.

    -   **WeatherApp.Android**: projekt obsahující kód nativní Android.

    -   **WeatherApp.iOS**: projekt obsahující kód nativní aplikace pro iOS.

    -   **WeatherApp.UWP**: projekt, který obsahuje Windows 10 UPW kódu.

    > [!NOTE]
    >  Můžete odstranit kterýkoli z projektů pro platformu, která nejsou cílení zdarma.

     V rámci každé nativní projekt mají přístup do nativní návrháře pro odpovídající platformu a můžete implementovat specifické pro platformu obrazovek a funkčnosti podle potřeby.

4.  Upgradujte balíček Xamarin.Forms NuGet v rámci vašeho řešení na nejnovější stabilní verzi následujícím způsobem:

    -   Vyberte **nástroje > Správce balíčků NuGet > spravovat balíčky NuGet pro řešení**.

    -   V části **aktualizace** kartě **Xamarin.Forms** balíček a zaškrtněte, pokud chcete aktualizovat všechny projekty v řešení. (Nevybírejte aktualizace pro podpůrné knihovny pro Xamarin Android.)

    -   Aktualizace **verze** pole **poslední stabilní** verzi, která je k dispozici.

    -   Klikněte na tlačítko **nainstalovat**.

         ![Aktualizuje se balíček Xamarin.Forms NuGet](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")

    Měli byste obdržet do podporují upgradování verze Xamarin.Forms pokaždé, když vytvoříte nové řešení Xamarin.Forms. Nelze aktualizovat všechny podpůrné knihovny pro Android. V případě potřeby tyto knihovny se aktualizují po aktualizaci verze Xamarin.Forms.

5.  Přidat **Newtonsoft.Json** balíčku NuGet **WeatherApp** projektu. Tato knihovna se používá ke zpracování informace načtenými z datové služby weather:

    -   Ve správci balíčků NuGet (stále otevřen v kroku 4), vyberte **Procházet** kartu a vyhledejte **Newtonsoft**.

    -   Vyberte **Newtonsoft.Json**.

    -   Zkontrolujte, **WeatherApp** projekt, který je pouze projekt, ve které je potřeba nainstalovat balíček.

    -   Zkontrolujte **verze** pole se nastaví **nejnovější stabilní verze** verze.

    -   Klikněte na tlačítko **nainstalovat**.

    ![Vyhledání a instalace balíčku Newtonsoft.Json NuGet](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")

6.  Opakujte krok 5 najít a nainstalovat **Microsoft.CSharp obsahují třídy** balíčky v projektu .NET Standard. Tato knihovna je potřeba použít jazyk C# `dynamic` datový typ v knihovně .NET Standard.

7.  Sestavte řešení a ověřte, že zde nejsou žádné chyby buildu.

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Zápis kódu služby sdílená data

**WeatherApp** je projekt knihovny .NET Standard, ve kterém budete psát kód, který se sdílí mezi všemi platformami. Aplikace se odkazuje této knihovny sestavovat balíčky zařízení s iOS, Android a Windows projekty.

Tuto ukázku spustit, musíte nejprve zaregistrujete bezplatný klíč rozhraní API v [ http://openweathermap.org/appid ](http://openweathermap.org/appid).

Takto přidejte kód knihovny .NET Standard pro přístup a ukládání dat z této služby weather:

1.  Klikněte pravým tlačítkem myši **WeatherApp** projektu a vyberte **Přidat > třída...** . V **přidat novou položku** dialogového okna, název souboru **Weather.cs**. Tato třída budete používat k ukládání dat ze služby data o počasí.

2.  Nahradí celý obsah **Weather.cs** následujícím kódem:

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

3.  Přidejte jinou třídu do **WeatherApp** projekt s názvem **DataService.cs** , které budete používat ke zpracování dat JSON z datové služby počasí.

4.  Nahradí celý obsah **DataService.cs** následujícím kódem:

    ```csharp
    using System.Net.Http;
    using System.Threading.Tasks;
    using Newtonsoft.Json;

    namespace WeatherApp
    {
        public class DataService
        {
            public static async Task<dynamic> getDataFromService(string queryString)
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

5.  Přidat třídu třetí **WeatherApp** projekt s názvem **Core.cs** místo, kam budete dáte sdílené obchodní logiku. Tento kód tvoří řetězec dotazu s PSČ, volá službu data o počasí a naplní instance `Weather` třídy.

6.  Nahraďte obsah **Core.cs** následujícím kódem:

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

                dynamic results = await DataService.getDataFromService(queryString).ConfigureAwait(false);

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

7. Nahraďte *vaše rozhraní API KEY zde* s klíčem rozhraní API, který jste získali. Stále potřebuje kolem něj uvozovky!

8.  Sestavení **WeatherApp** projekt knihovny, abyste měli jistotu, kód je správný.

 <a name="uicode" />

## <a name="begin-writing-shared-ui-code"></a>Začněte psát sdíleným kódem uživatelského rozhraní

Xamarin.Forms umožňuje implementovat sdíleným kódem uživatelského rozhraní v knihovně .NET Standard. V následujícím postupu přidáte na stránku do projektu s tlačítkem. Toto tlačítko Aktualizace textu na stránce s daty vrácené službou počasí, že jste viděli v předchozí části:

1.  Přidat **stránku obsahu** s názvem **WeatherPage** kliknutím pravým tlačítkem myši **WeatherApp** projekt a výběrem **Přidat > Nová položka...** . V **přidat novou položku** dialogového okna, vyberte **stránku obsahu**. Dejte pozor, abyste vyberte **stránka obsahu (C#)** nebo **zobrazení obsahu**. Pojmenujte ji **WeatherPage.xaml**.

    ![Přidání nové stránky XAML Xamarin.Forms](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")

     Xamarin.Forms je založené na XAML, takže tento krok vytvoří **WeatherPage.xaml** soubor spolu se souborem vnořeného kódu **WeatherPage.xaml.cs**. Možnosti logiky uživatelského rozhraní můžete psát v XAML nebo kódu. Část v tomto názorném postupu budete používat.

2.  Tlačítko pro přidání **WeatherPage** obrazovky, nahraďte obsah **WeatherPage.xaml** následujícím kódem:

    ```xaml
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
           x:Class="WeatherApp.WeatherPage"
           Title="Sample Weather App">
      <Button x:Name="getWeatherBtn"
              Text="Get Weather"
              Clicked="GetWeatherBtn_Clicked" />
    </ContentPage>
    ```

     Všimněte si, že název tlačítka musí být definován pomocí `x:Name` atribut tak, aby toto tlačítko můžete odkazovat pomocí názvu z v rámci souboru kódu na pozadí.

3.  Chcete-li přidat obslužnou rutinu události pro tlačítka `Clicked` událost aktualizace textu tlačítka, nahraďte obsah **WeatherPage.xaml.cs** níže uvedeného kódu. (Můžete změnit na jiný kód zip "60601".)

    ```csharp
    using System;
    using Xamarin.Forms;

    namespace WeatherApp
    {
        public partial class WeatherPage: ContentPage
        {
            public WeatherPage()
            {
                InitializeComponent();

                //Set the default binding to a default object for now
                BindingContext = new Weather();
            }

            private async void GetWeatherBtn_Clicked(object sender, EventArgs e)
            {
                Weather weather = await Core.GetWeather("60601");
                getWeatherBtn.Text = weather.Title;
            }
        }
    }
    ```

4.  Chcete-li otevřít **WeatherPage** jako první obrazovku při spuštění aplikace nahradí výchozí konstruktor v **App.xaml.cs** následujícím kódem:

    ```csharp
    public App()
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());
    }
    ```

5.  Sestavení **WeatherApp** projektu, abyste měli jistotu, kód je správný.

<a name="test" />

## <a name="test-your-app-using-the-visual-studio-emulator-for-android"></a>Testování aplikace pomocí emulátoru Visual Studia pro Android

Nyní jste připraveni aplikaci spustit! Můžeme spustit jenom verze Androidu nyní chcete ověřit, že aplikace je získání dat ze služby počasí. Později je potřeba taky spustit na iOS a UPW verze po přidání další prvky uživatelského rozhraní.

1.  Nastavte **WeatherApp.Android** projekt jako spouštěný projekt tak, že pravým tlačítkem myši a vyberete **nastavit jako spouštěný projekt**.

2.  Na panelu nástrojů sady Visual Studio, zobrazí se vám **WeatherApp.Android** uvedené jako cílový projekt. Vyberte jednu z emulátorů Androidu pro ladění a spuštění **F5**. Doporučujeme použít jeden z **VisualStudio** možnosti emulátoru, které se spustí aplikaci v emulátoru Visual Studia pro Android.

    ![Vyberte cíl ladění emulátoru Androidu](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")

    > [!NOTE]
    > Pokud Visual Studio znamená, že projekt pro Android nemůže najít soubor Newtonsoft.Json, přidejte balíček NuGet do projektu pro Android.

3.  Při spuštění aplikace se spustila v emulátoru, klikněte na tlačítko **získat počasí** tlačítko. Byste měli vidět text na tlačítko Aktualizovat, aby **Chicago**, což je `Title` vlastnost dat načtených z této služby počasí.

     ![Informace o počasí aplikace před a po klepnutí na tlačítko](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")

<a name="finish" />

## <a name="finish-the-ui-with-a-native-look-and-feel-across-platforms"></a>Dokončení uživatelského rozhraní pomocí přirozený vzhled a chování napříč platformami

Xamarin.Forms vykreslí nativní ovládací prvky uživatelského rozhraní pro každou platformu, aby vaše aplikace automaticky nemá přirozený vzhled a chování. Zobrazí se tato přirozený vzhled a chování jasněji při dokončení uživatelského rozhraní na vstupní pole pro PSČ a ovládacích prvků pro zobrazení dat o počasí zahrnout.

1.  Nahraďte obsah **WeatherPage.xaml** se značkami níže. Prvky, které jsou pojmenovány pomocí `x:Name` atributu, jak je popsáno výše můžete odkazovat z kódu. Xamarin.Forms také nabízí celou řadu [možnosti rozložení](/xamarin/xamarin-forms/user-interface/controls/layouts). Tady je pomocí WeatherPage [mřížky](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) a [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/).

    ```xaml
    <?xml version="1.0" encoding="utf-8" ?>
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
                 xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
                 x:Class="WeatherApp.WeatherPage"
                 Title="Sample Weather App">

        <ContentPage.Resources>
            <ResourceDictionary>
                <Style x:Key="labelStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Small" />
                    <Setter Property="TextColor" Value="#404040" />
                </Style>
                <Style x:Key="fieldStyle" TargetType="Label">
                    <Setter Property="FontSize" Value="Medium" />
                    <Setter Property="Margin" Value="10,0,0,0" />
                </Style>
            </ResourceDictionary>
        </ContentPage.Resources>

        <StackLayout>
            <Grid BackgroundColor="#545454" Padding="10, 10, 10, 10">
                <Grid.RowDefinitions>
                    <RowDefinition Height="Auto" />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="Auto" />
                    <ColumnDefinition Width="*" />
                    <ColumnDefinition Width="Auto" />
                </Grid.ColumnDefinitions>

                <Label Text="Search by Zip Code"
                       Grid.Row="0" Grid.Column="0" Grid.ColumnSpan="3"
                       HorizontalOptions="Center"
                       TextColor="White" FontAttributes="Bold" FontSize="Medium" />

                <Label x:Name="zipCodeLabel" Text="Zip Code:"
                       Grid.Row="1" Grid.Column="0"
                       VerticalOptions="Center"
                       Style="{StaticResource labelStyle}"
                       TextColor="#C0C0C0" />

                <Entry x:Name="zipCodeEntry"
                       Grid.Row="1" Grid.Column="1"
                       VerticalOptions="Center"
                       Margin="5,0"
                       BackgroundColor="DarkGray"
                       TextColor="White" />

                <Button x:Name="getWeatherBtn" Text="Get Weather"
                        Grid.Row="1" Grid.Column="2"
                        HorizontalOptions="Center"
                        VerticalOptions="Center"
                        BorderWidth="1"
                        BorderColor="White"
                        BackgroundColor="DarkGray"
                        TextColor="White"
                        Clicked="GetWeatherBtn_Clicked" />
            </Grid>

            <ScrollView VerticalOptions="FillAndExpand">
                <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">
                    <Label Text="Location" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Title}" Style="{StaticResource fieldStyle}" />

                    <Label Text="Temperature" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Temperature}" Style="{StaticResource fieldStyle}" />

                    <Label Text="Wind Speed" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Wind}" Style="{StaticResource fieldStyle}" />

                    <Label Text="Humidity" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Humidity}" Style="{StaticResource fieldStyle}" />

                    <Label Text="Visibility" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Visibility}" Style="{StaticResource fieldStyle}" />

                    <Label Text="Time of Sunrise" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunrise}" Style="{StaticResource fieldStyle}" />

                    <Label Text="Time of Sunset" Style="{StaticResource labelStyle}" />
                    <Label Text="{Binding Sunset}" Style="{StaticResource fieldStyle}" />
                </StackLayout>
            </ScrollView>
        </StackLayout>
    </ContentPage>
     ```

     I když není tady zobrazené, můžete použít `OnPlatform` značky v souborech XAML a vyberte hodnotu vlastnosti, které jsou specifické pro aktuální platformu, na kterém je aplikace spuštěna (naleznete v tématu [základní syntaxe XAML](/xamarin/xamarin-forms/xaml/xaml-basics/essential-xaml-syntax/).) V souboru kódu na pozadí můžete určit, jakou platformu aplikace běží porovnáním [ `Device.RuntimePlatform` ](https://developer.xamarin.com/api/property/Xamarin.Forms.Device.RuntimePlatform/) vlastnost s konstanty definované v [ `Device` ](https://developer.xamarin.com/api/type/Xamarin.Forms.Device/) třídu s názvem [ `Device.iOS` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.iOS/), [ `Device.Android` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.Android/), a [ `Device.UWP` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.UWP/).

2.  V **WeatherPage.xaml.cs**, nahraďte `GetWeatherBtn_Clicked` obslužné rutiny události pomocí kódu níže. Tento kód ověří, že je kód zip do vstupního pole a načte data pro tento kód zip. Potom nastaví kontext vazby celou stránku na výsledný `Weather` instance. Dojde k závěru kód tak, že nastavíte text tlačítka na "Vyhledávání znovu." Každý popisek v uživatelském rozhraní vytvoří vazbu na vlastnost `Weather` třídy. Pokud nastavíte na kontextu vazby na obrazovce `Weather` instance, tyto popisky automaticky aktualizovat.

    ```csharp
    private async void GetWeatherBtn_Clicked(object sender, EventArgs e)
    {
        if (!String.IsNullOrEmpty(zipCodeEntry.Text))
        {
            Weather weather = await Core.GetWeather(zipCodeEntry.Text);
            BindingContext = weather;
            getWeatherBtn.Text = "Search Again";
        }
    }
    ```

3.  Spuštění aplikace na všech třech platformách kliknutím pravým tlačítkem myši příslušný projekt výběrem **nastavit jako spouštěný projekt**a spuštění aplikace na zařízení nebo emulátoru. Zadejte platné PSČ USA pět číslic a stiskněte klávesu **získat počasí** tlačítko a zobrazte data o počasí v dané oblasti. Musíte mít Visual Studio připojená k počítači Mac ve vaší síti pro projekt pro iOS.

     [![Ukázkové aplikace o počasí v iOS, Android a UPW](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)

Úplný zdrojový kód pro tento projekt je v [ukázky xamarin forms úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).
