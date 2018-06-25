---
title: Další informace základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.topic: conceptual
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
ms.technology: vs-ide-mobile
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: 5c66a74a951edb945bf42eeef3df484b8f84ebd9
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757120"
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio

Jakmile provedete kroky krok [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md), tento postup vám ukáže, jak vytvořit základní aplikaci s Xamarin.Forms. S Xamarin.Forms napíšete veškerý kód uživatelského rozhraní jednou v rozhraní .NET standardní knihovny tříd. Xamarin potom automaticky vykreslí nativní ovládacích prvků uživatelského rozhraní pro iOS, Android a Universal Windows platformy.

Je obvykle lepší používá knihovnu .NET Standard namísto sdílených projektů pro tento společný kód. .NET Standard knihovna obsahuje tyto API technologie .NET, které můžou běžet na všechny cílové platformy.

Zde je aplikace, která budete sestavení. (Zleva doprava) je spuštěn na iOS a Android telefony a Universal Windows Platform (UWP) Windows 10:

[![Ukázka počasí aplikace pro iOS, Android a UWP](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)

Můžete to udělat tyto kroky k vytvoření této aplikace:

-   [Nastavit řešení](#solution)

-   [Zápis kódu služby sdílených dat](#dataservice)

-   [Zahájit zápis sdíleného kódu uživatelského rozhraní](#uicode)

-   [Testování aplikace pomocí emulátor sady Visual Studio pro Android](#test)

-   [Dokončit rozhraní s přirozený vzhled a chování napříč platformami](#finish)

> [!TIP]
> Můžete najít úplný zdrojový kód pro tento projekt v [xamarin-forms-samples úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).

<a name="solution" />

## <a name="set-up-your-solution"></a>Nastavit řešení

Tyto kroky vytvářet řešení Xamarin.Forms, která obsahuje .NET standardní knihovny tříd pro sdílené kód a dvě přidání balíčků NuGet.

1. V sadě Visual Studio vytvořte novou **Multiplatformní aplikace (Xamarin.Forms)** řešení a pojmenujte ji **WeatherApp**. Pomocí příkazu Zobrazit šablony **Visual C#** a **napříč platformami** ze seznamu na levé straně.

    ![Vytvoření nového projektu aplikace na platformě Xamarin.Forms napříč platformami](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

    Pokud není šablony, můžete chtít nainstalovat Xamarin nebo povolit funkci Visual Studio 2017. V tématu [nastavení a instalaci](../cross-platform/setup-and-install.md).

2.  Po kliknutí na tlačítko OK, máte možnost vybrat některé možnosti. Vyberte **prázdná aplikace** a **.NET Standard**:

    ![Vytvoření nového projektu mezi aplikace platformy](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")

3.  Po kliknutí na tlačítko OK, abyste vytvořili řešení, budete mít řešení s čtyři projekty:

    -   **WeatherApp**: .NET Standard knihovny, kde budete psát kód, který je sdílen napříč platformami, včetně běžné obchodní logiky a kód uživatelského rozhraní pomocí Xamarin.Forms.

    -   **WeatherApp.Android**: projekt, který obsahuje nativní kód pro Android.

    -   **WeatherApp.iOS**: projekt, který obsahuje kód nativní aplikace pro iOS.

    -   **WeatherApp.UWP**: projekt, který obsahuje kód Windows 10 UWP.

    > [!NOTE]
    >  Jste volné odstraní všechny projekty pro platformu, která nejsou cílení.

     V rámci každé nativnímu projektu máte přístup k nativní designer pro odpovídající platformu a můžete implementovat specifické pro platformu obrazovky a funkci podle potřeby.

4.  Balíček Xamarin.Forms NuGet ve vašem řešení upgradujte na nejnovější stabilní verze následujícím způsobem:

    -   Vyberte **nástroje > Správce balíčků NuGet > Správa balíčků NuGet pro řešení**.

    -   V části **aktualizace** zkontrolujte **Xamarin.Forms** balíček a zkontrolujte aktualizovat všechny projekty v řešení. (Nevybírejte aktualizace pro podporu knihovny Xamarin Android.)

    -   Aktualizace **verze** do **nejnovější stabilní** verzi, která je k dispozici.

    -   Klikněte na tlačítko **nainstalovat**.

         ![Aktualizuje balíček Xamarin.Forms NuGet](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")

    Měli byste obdržet do která podporují upgradovat na verzi Xamarin.Forms pokaždé, když vytvoříte nové řešení Xamarin.Forms. Nelze aktualizovat všechny knihovny podpora pro Android. V případě potřeby tyto knihovny se aktualizují při aktualizaci na verzi Xamarin.Forms.

5.  Přidat **Newtonsoft.Json** balíček NuGet, abyste **WeatherApp** projektu. V této knihovně se používá ke zpracování informace získané z datové služby počasí:

    -   V Správce balíčků NuGet (stále otevřen z kroku 4), vyberte **Procházet** kartě a vyhledejte **Newtonsoft**.

    -   Vyberte **Newtonsoft.Json**.

    -   Zkontrolujte **WeatherApp** projektu, který je pouze projektu, ve kterém je potřeba k instalaci balíčku.

    -   Ujistěte se, **verze** pole je nastaveno **nejnovější stabilní** verze.

    -   Klikněte na tlačítko **nainstalovat**.

    ![Vyhledání a instalace balíčku Newtonsoft.Json NuGet](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")

6.  Opakujte krok 5 a najít a nainstalovat **Microsoft.CSharp** balíček v .NET Standard projektu. Tato knihovna je nutné k použití jazyka C# `dynamic` typ dat v rozhraní .NET standardní knihovny.

7.  Sestavte řešení a ověřte, zda nejsou žádné chyby sestavení.

<a name="dataservice" />

## <a name="write-shared-data-service-code"></a>Zápis kódu služby sdílených dat

**WeatherApp** .NET Standard projektu knihovny je, kde budete psát kód, který je sdílen na všech platformách. Tato knihovna je odkazován objektem aplikace balíčky sestavení iOS, Android a Windows projekty.

Pokud chcete tuto ukázku spustit, musíte nejprve zaregistrujete k bezplatné klíč rozhraní API v [ http://openweathermap.org/appid ](http://openweathermap.org/appid).

Následující kroky pak přidejte do .NET standardní knihovnu, která má přístup a ukládání dat z dané služby počasí kód:

1.  Klikněte pravým tlačítkem myši **WeatherApp** projektu a vyberte **Přidat > třída...** . V **přidat novou položku** dialogové okno, název souboru **Weather.cs**. Tato třída budete používat k ukládání dat ze služby počasí data.

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

3.  Přidejte jinou třídu do **WeatherApp** projektu s názvem **DataService.cs** , které budete používat ke zpracování dat JSON ze služby počasí data.

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

5.  Přidejte třídu třetí k **WeatherApp** projektu s názvem **Core.cs** kam budete umísťovat sdílené obchodní logiku. Tento kód forms řetězec dotazu s kódem zip, zavolá službu data počasí a naplní instanci `Weather` třídy.

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

7. Nahraďte *vaše rozhraní API klíč zde* s klíčem rozhraní API, který jste získali. Je stále nutné uvozovky, do kterých se!

8.  Sestavení **WeatherApp** projekt knihovny zkontrolujte, zda je správný kód.

 <a name="uicode" />

## <a name="begin-writing-shared-ui-code"></a>Zahájit zápis sdíleného kódu uživatelského rozhraní

Xamarin.Forms umožňuje implementovat sdílený kód uživatelského rozhraní v knihovně .NET Standard. V následujícím postupu přidáte na stránce s tlačítkem na projekt. Toto tlačítko aktualizací, které se text na stránce s daty vrácený službou počasí jste viděli v předchozí části:

1.  Přidat **obsahu stránce** s názvem **WeatherPage** kliknutím pravým tlačítkem myši **WeatherApp** projekt a výběrem **Přidat > novou položku...** . V **přidat novou položku** dialogovém okně, vyberte **obsahu stránce**. Dejte pozor, abyste vyberte **obsahu stránce (C#)** nebo **zobrazení obsahu**. Pojmenujte ji **WeatherPage.xaml**.

    ![Přidání nové stránky Xamarin.Forms XAML](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")

     Xamarin.Forms je založené na jazyce XAML, takže tento krok vytvoří **WeatherPage.xaml** soubor souborem vnořené kódu **WeatherPage.xaml.cs**. Můžete napsat logiku uživatelského rozhraní v jazyce XAML nebo kódu. Můžete to udělat některé i v tomto návodu.

2.  Chcete-li přidat tlačítko **WeatherPage** obrazovky, nahraďte obsah **WeatherPage.xaml** s následující kód:

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

     Všimněte si, že název tlačítko musí být definován pomocí `x:Name` atributů tak, aby toto tlačítko, můžete odkazovat podle názvu z v souboru kódu na pozadí.

3.  Přidání obslužné rutiny události pro tlačítka `Clicked` událostí, které chcete aktualizovat text tlačítka, nahraďte obsah **WeatherPage.xaml.cs** pomocí kódu níže. (Zaregistrované, můžete změnit na jiný kód zip "60601".)

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

4.  Chcete-li otevřít **WeatherPage** jako první obrazovce při spuštění aplikace, nahradí výchozí konstruktor v **App.xaml.cs** následujícím kódem:

    ```csharp
    public App()
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());
    }
    ```

5.  Sestavení **WeatherApp** projektu a zkontrolujte, zda je správný kód.

<a name="test" />

## <a name="test-your-app-using-the-visual-studio-emulator-for-android"></a>Testování aplikace pomocí emulátor sady Visual Studio pro Android

Teď můžete začít a spusťte aplikaci. Umožňuje spustit jenom Android verze teď chcete-li ověřit, že aplikace je získání dat ze služby počasí. Později také spustíte na iOS a verze UWP po přidání další prvky uživatelského rozhraní.

1.  Nastavte **WeatherApp.Android** projekt jako spouštěný projekt pravým tlačítkem myši a výběrem **nastavit jako spouštěný projekt**.

2.  Na panelu nástrojů Visual Studio se zobrazí **WeatherApp.Android** uveden jako cílový projekt. Vyberte jeden z Android emulátorů pro ladění a stiskněte tlačítko **F5**. Doporučujeme použít jednu z **Visual Studio** emulátoru možnosti, které bude aplikace spuštěna v emulátor sady Visual Studio pro Android.

    ![Výběr cíli ladění emulátoru Android](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")

    > [!NOTE]
    > Pokud Visual Studio znamená, že projektu pro Android nemůže najít soubor Newtonsoft.Json, přidejte tento balíček NuGet do projektu pro Android.

3.  Při spuštění aplikace v emulátoru, klikněte **získat počasí** tlačítko. Byste měli vidět text na tlačítko Aktualizovat na **Chicagu**, který je `Title` vlastnost dat získaný ze služby počasí.

     ![Informace o počasí aplikace před a po klepnutím na tlačítko](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")

<a name="finish" />

## <a name="finish-the-ui-with-a-native-look-and-feel-across-platforms"></a>Dokončit rozhraní s přirozený vzhled a chování napříč platformami

Xamarin.Forms vykreslí nativní ovládací prvky uživatelského rozhraní pro každou platformu, tak, aby vaše aplikace automaticky obsahuje přirozený vzhled a chování. Zobrazíte tuto přirozený vzhled a chování zřetelněji tak dokončení rozhraní zahrnout vstupní pole pro PSČ a ovládacích prvků pro zobrazení dat počasí.

1.  Nahraďte obsah **WeatherPage.xaml** s kód níže. Prvky, které jsou s názvem pomocí `x:Name` atributu, jak je popsáno výše, může být odkazován z kódu. Xamarin.Forms také poskytuje řadu [možnosti rozložení](/xamarin/xamarin-forms/user-interface/controls/layouts). Zde je pomocí WeatherPage [mřížky](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) a [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/).

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

     I když není tady zobrazené, můžete použít `OnPlatform` značku soubory XAML a vyberte hodnotu vlastnosti, které jsou specifické pro aktuální platformě, na kterém je spuštěna aplikace (najdete v části [základní syntaxe XAML](/xamarin/xamarin-forms/xaml/xaml-basics/essential-xaml-syntax/).) V souboru kódu na pozadí, můžete určit, jakou platformu aplikace běží základě porovnání [ `Device.RuntimePlatform` ](https://developer.xamarin.com/api/property/Xamarin.Forms.Device.RuntimePlatform/) vlastnost s konstanty definované v [ `Device` ](https://developer.xamarin.com/api/type/Xamarin.Forms.Device/) třídu s názvem [ `Device.iOS` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.iOS/), [ `Device.Android` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.Android/), a [ `Device.UWP` ](https://developer.xamarin.com/api/field/Xamarin.Forms.Device.UWP/).

2.  V **WeatherPage.xaml.cs**, nahraďte `GetWeatherBtn_Clicked` obslužné rutiny události pomocí kódu níže. Tento kód ověřuje, že je PSČ pole Položka a načte data pro tento kód zip. Potom nastaví kontext vazby na celou stránku výsledná `Weather` instance. Kód se ukončí nastavení text tlačítka na "Vyhledat znovu." Každý popisek v uživatelském rozhraní se váže k vlastnost `Weather` třídy. Když nastavíte na kontext vazby na obrazovce `Weather` instance, tyto popisky aktualizovat automaticky.

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

3.  Spusťte aplikaci na všech platformách tři pravým tlačítkem na příslušný projekt výběr **nastavit jako spouštěný projekt**a spuštění aplikace na zařízení nebo emulátor. Zadejte platné PSČ Spojených států pět číslic a stiskněte klávesu **získat počasí** tlačítko pro zobrazení dat počasí pro danou oblast. Musíte mít Visual Studio připojené k počítači Mac ve vaší síti pro projekt pro iOS.

     [![Ukázka počasí aplikace pro iOS, Android a UWP](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")](../cross-platform/media/crossplat-xamarin-formsguide-1-Large.png#lightbox)

Úplný zdrojový kód pro tento projekt je v [xamarin-forms-samples úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).
