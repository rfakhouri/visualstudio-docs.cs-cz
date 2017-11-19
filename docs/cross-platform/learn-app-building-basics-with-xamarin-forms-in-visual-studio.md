---
title: "Další informace základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
caps.latest.revision: "11"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: d428f340cd1c0c990ec196c3c9d84e6f22093805
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Další informace základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio
Jakmile provedete kroky krok [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md), tento postup vám ukáže, jak vytvořit základní aplikaci (zobrazené dole) s Xamarin.Forms. S Xamarin.Forms napíšete veškerý kód uživatelského rozhraní jednou v knihovny přenosných tříd (PCL). Xamarin potom automaticky vykreslí nativní ovládacích prvků uživatelského rozhraní pro iOS, Android a Windows platformy. Doporučujeme tento přístup, protože možnost PCL nejlepší podporuje používání pouze rozhraní .NET API, které jsou podporovány v rámci všech cílových platforem a protože Xamarin.Forms umožňuje sdílet kód uživatelského rozhraní napříč platformami.  
  
 ![Ukázky počasí aplikaci pro Android, iOS a Windows Phone](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Můžete to udělat ji od sestavit tyto věci:  
  
-   [Nastavit řešení](#solution)  
  
-   [Zápis kódu služby sdílených dat](#dataservice)  
  
-   [Zahájit zápis sdíleného kódu uživatelského rozhraní](#uicode)  
  
-   [Testování aplikace pomocí emulátor sady Visual Studio pro Android](#test)  
  
-   [Dokončit rozhraní s přirozený vzhled a chování napříč platformami](#finish)  
  
> [!TIP]
>  Můžete najít úplný zdrojový kód pro tento projekt v [xamarin-forms-samples úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).  
  
##  <a name="solution"></a>Nastavit řešení  
 Tyto kroky slouží k vytvoření řešení Xamarin.Forms, který obsahuje PCL pro sdílené kód a dvě přidání balíčků NuGet.  
  
1.  V sadě Visual Studio vytvořte novou **prázdná aplikace (Xamarin.Forms přenositelností)** řešení a pojmenujte ji **WeatherApp**. Tuto šablonu lze snadno najít zadáním **Xamarin.Forms** do pole hledání.  
  
     Pokud tam není, možná budete muset nainstalovat Xamarin nebo povolit funkci Visual Studio 2015, najdete v části [nastavení a instalaci](../cross-platform/setup-and-install.md).  
  
     ![Vytvoření nové prázdné aplikace &#40; Xamarin.Forms přenositelností &#41; projekt](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")  
  
2.  Po kliknutí na tlačítko OK, abyste vytvořili řešení, budete mít počtu jednotlivých projektů:  
  
    -   **WeatherApp (přenositelností)**: PCL, kde budete psát kód, který je sdílen napříč platformami, včetně běžné obchodní logiky a kód uživatelského rozhraní pomocí Xamarin.Forms.  
  
    -   **WeatherApp.Droid**: projekt, který obsahuje nativní kód pro Android. To je nastaven jako výchozí projekt po spuštění.  
  
    -   **WeatherApp.iOS**: projekt, který obsahuje kód nativní aplikace pro iOS.  
  
    -   **WeatherApp.UWP**: projekt, který obsahuje kód Windows 10 UWP.  
  
    -   **WeatherApp.Windows (Windows 8.1)**: projekt, který obsahuje nativního kódu Windows 8.1.  
  
    -   **WeatherApp.WinPhone (Windows Phone 8.1)**: projekt, který obsahuje nativní kód pro Windows Phone.  
  
    > [!NOTE]
    >  Jste volné odstraní všechny projekty pro platformu, která nejsou cílení. Pro účely tohoto návodu budeme budete odkazující na projektů Android, iOS a Windows Phone 8.1. Práce s UWP a Windows 8.1 projekty je velmi podobná práci s projektem Windows Phone 8.1.  
  
     V rámci každé nativnímu projektu mít přístup k nativní designer pro odpovídající platformu a můžete implementovat určité obrazovky platformy a funkce, podle potřeby.  
  
3.  Takto upgrade na nejnovější stabilní verze balíčku Xamarin.Forms NuGet ve vašem řešení. Doporučujeme, abyste to vždy, když vytvoříte nové řešení Xamarin:  
  
    -   Vyberte **nástroje > Správce balíčků NuGet > Správa balíčků NuGet pro řešení**.  
  
    -   V části **aktualizace** zkontrolujte **Xamarin.Forms** aktualizace a kontrola aktualizovat všechny projekty v řešení. (Poznámka: nechte žádné aktualizace pro Xamarin.Android.Support nezaškrtnuté.)  
  
    -   Aktualizace **verze** do **nejnovější stabilní** verzi, která je k dispozici.  
  
    -   Klikněte na tlačítko **aktualizace**.  
  
         ![Aktualizuje balíček Xamarin.Forms NuGet](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  
  
4.  Přidat **Newtonsoft.Json** a balíček NuGet do projektu PCL, který použijete ke zpracování informace získané z datové služby počasí:  
  
    -   V Správce balíčků NuGet (stále otevřen od kroku 3), vyberte **Procházet** kartě a vyhledejte **Newtonsoft**.  
  
    -   Vyberte **Newtonsoft.Json**.  
  
    -   Zkontrolujte **WeatherApp** projektu (Toto je pouze projektu, ve kterém je potřeba k instalaci balíčku).  
  
    -   Ujistěte se, **verze** pole je nastaveno **nejnovější stabilní** verze.  
  
    -   Klikněte na tlačítko **nainstalovat**.  
  
    -   ![Vyhledání a instalace balíčku Newtonsoft.Json NuGet](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
5.  Opakováním kroků 4 vyhledávat a instalovat **Microsoft.Net.Http** balíčku.  
  
6.  Sestavte řešení a ověřte, zda nejsou žádné chyby sestavení.  
  
##  <a name="dataservice"></a>Zápis kódu služby sdílených dat  
 **WeatherApp (přenositelností)** projektu je, kde budete psát kód pro knihovny přenosných tříd (PCL), který je sdílen na všech platformách. PCL je automaticky součástí aplikace balíčky sestavení iOS, Android a Windows Phone projekty.  
  
 Ke spuštění této ukázky musíte nejprve zaregistrovat pro bezplatné klíč rozhraní API v [http://openweathermap.org/appid](http://openweathermap.org/appid).  
  
 Následující kroky přidejte pak kód PCL pro přístup a ukládání dat z počasí služby:  
  
1.  Klikněte pravým tlačítkem myši **WeatherApp** projektu a vyberte **Přidat > třída...** . V **přidat novou položku** dialogové okno, název souboru **Weather.cs**. Tato třída budete používat k ukládání dat ze služby počasí data.  
  
2.  Nahradí celý obsah **Weather.cs** následujícím kódem:  
  
    ```csharp  
    namespace WeatherApp  
    {  
        public class Weather  
        {  
            public string Title { get; set; }  
            public string Temperature { get; set; }  
            public string Wind { get; set; }  
            public string Humidity { get; set; }  
            public string Visibility { get; set; }  
            public string Sunrise { get; set; }  
            public string Sunset { get; set; }  
  
            public Weather()  
            {  
                //Because labels bind to these values, set them to an empty string to  
                //ensure that the label appears on all platforms by default.  
                this.Title = " ";  
                this.Temperature = " ";  
                this.Wind = " ";  
                this.Humidity = " ";  
                this.Visibility = " ";  
                this.Sunrise = " ";  
                this.Sunset = " ";  
            }  
        }  
    }  
    ```  
  
3.  Přidejte jinou třídu do projektu PCL s názvem **DataService.cs** ve které budete používat zpracovat JSON data ze služby počasí data.  
  
4.  Nahradí celý obsah **DataService.cs** následujícím kódem:  
  
    ```csharp  
    using System.Threading.Tasks;  
    using Newtonsoft.Json;  
    using System.Net.Http;  
  
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
  
5.  Přidání třídy třetí PCL s názvem **základní** kam budete umísťovat sdílené obchodní logiky, například logiku, která tvoří řetězec dotazu s PSČ, zavolá službu data počasí a naplní instanci **počasí**třídy.  
  
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
                string key = "YOUR KEY HERE";  
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
  
7.  Sestavení **WeatherApp** PCL projektu a zkontrolujte, zda je správný kód.  
  
##  <a name="uicode"></a>Zahájit zápis sdíleného kódu uživatelského rozhraní  
 Xamarin.Forms vám umožňují implementovat sdílený kód uživatelského rozhraní PCL. Tímto postupem přidáte obrazovky PCL s tlačítkem na aktualizace textu jeho s daty vrácených dat počasí služby kódu přidaném v předchozí části:  
  
1.  Přidat **Forms Xaml – stránka** s názvem **WeatherPage.cs** kliknutím pravým tlačítkem myši **WeatherApp** projekt a výběrem **Přidat > novou položku...** . V **přidat novou položku** dialogové okno, vyhledávání v "Forms" vyberte **Forms Xaml – stránka**a pojmenujte ji **WeatherPage.cs**.  
  
     Xamarin.Forms je založené na jazyce XAML, takže tento krok vytvoří **WeatherPage.xaml** soubor souborem vnořené kódu **WeatherPage.xaml.cs**. To umožňuje generování uživatelského rozhraní pomocí XAML nebo kódu. Můžete to udělat některé i v tomto návodu.  
  
     ![Přidání nové stránky Xamarin.Forms XAML](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
2.  Přidání tlačítka na obrazovku WeatherPage, nahraďte obsah WeatherPage.xaml s následujícími službami:  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage">  
      <Button x:Name="getWeatherBtn" Text="Get Weather"/>  
    </ContentPage>  
    ```  
  
     Všimněte si, že název tlačítko musí být definován pomocí **x: Name** atributů tak, aby toto tlačítko, můžete odkazovat podle názvu z v souboru kódu na pozadí.  
  
3.  Přidání obslužné rutiny události pro tlačítka **místní** událostí, které chcete aktualizovat text tlačítka, nahraďte obsah **WeatherPage.xaml.cs** pomocí kódu níže. (Zaregistrované, můžete změnit na jiný kód zip "60601".)  
  
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
                this.Title = "Sample Weather App";  
                getWeatherBtn.Clicked += GetWeatherBtn_Clicked;  
  
                //Set the default binding to a default object for now  
                this.BindingContext = new Weather();  
            }  
  
            private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
            {  
                Weather weather = await Core.GetWeather("60601");  
                getWeatherBtn.Text = weather.Title;  
            }  
        }  
    }  
    ```  
  
4.  Chcete-li otevřít **WeatherPage** jako první obrazovce při spuštění aplikace, nahradí výchozí konstruktor v **App.cs** následujícím kódem:  
  
    ```csharp  
    public App()  
    {  
        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  Sestavte projekt WeatherApp PCL a ujistěte se, že kód není správný.  
  
##  <a name="test"></a>Testování aplikace pomocí emulátor sady Visual Studio pro Android  
 Teď můžete začít a spusťte aplikaci. Umožňuje spustit jenom Android verze teď chcete-li ověřit, že aplikace je získání dat ze služby počasí. Později také spustíte na iOS a Windows Phone verze po přidání další prvky uživatelského rozhraní. (Poznámka: Pokud používáte Visual Studio v systému Windows 7, budete stejným způsobem, ale místo toho bude Xamarin Player.)  
  
1.  Nastavte **WeatherApp.Droid** projekt jako spouštěný projekt pravým tlačítkem myši a výběrem **nastavit jako spouštěný projekt**.  
  
2.  Na panelu nástrojů Visual Studio se zobrazí **WeatherApp.Droid** uveden jako cílový projekt. Vyberte jeden z Android emulátorů pro ladění a stiskněte tlačítko **F5**. Doporučujeme použít jednu z **VS emulátoru** možnosti, které aplikace poběží v emulátor sady Visual Studio pro Android možnosti.  
  
     ![Výběr cíle ladění VS emulátoru](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")  
  
3.  Při spuštění aplikace v emulátoru, klikněte **získat počasí** tlačítko. Byste měli vidět text na tlačítko Aktualizovat na **Chicagu, IL**, který je *název* vlastnost dat získaný ze služby počasí.  
  
     ![Informace o počasí aplikace před a po klepnutím na tlačítko](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  
  
##  <a name="finish"></a>Dokončit rozhraní s přirozený vzhled a chování napříč platformami  
 Xamarin.Forms vykreslí nativní ovládací prvky uživatelského rozhraní pro každou platformu, tak, aby vaše aplikace automaticky obsahuje přirozený vzhled a chování. Zobrazení tohoto informace je zřejmé, můžeme dokončit rozhraní s vstupní pole pro PSČ a následně se zobrazí počasí data, která je vrácena ze služby.  
  
1.  Nahraďte obsah **WeatherPage.xaml** pomocí kódu níže. Všimněte si, že každý element, má název, pomocí **x: Name** atributu, jak je popsáno výše, aby elementu lze odkazovat z kódu. Xamarin.Forms také poskytuje řadu [možnosti rozložení](http://developer.xamarin.com/guides/xamarin-forms/controls/layouts/) (xamarin.com); zde pomocí WeatherPage [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/) (xamarin.com).  
  
    ```xaml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <ContentPage xmlns="http://xamarin.com/schemas/2014/forms"  
           xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"  
           x:Class="WeatherApp.WeatherPage">  
  
      <ContentPage.Resources>  
        <ResourceDictionary>  
          <Style x:Key="labelStyle" TargetType="Label">  
            <Setter Property="TextColor" Value="#a8a8a8" />  
            <Setter Property="FontSize" Value="Small" />  
          </Style>  
          <Style x:Key="fieldStyle" TargetType="Label">  
            <Setter Property="TextColor">  
              <OnPlatform x:TypeArguments="Color" iOS="Black" Android="White" WinPhone="White" />  
            </Setter>  
            <Setter Property="FontSize" Value="Medium" />  
          </Style>  
          <Style x:Key="fieldView" TargetType="ContentView">  
            <Setter Property="Padding" Value="10,0,0,0" />  
          </Style>  
        </ResourceDictionary>  
      </ContentPage.Resources>  
  
      <ContentPage.Content>  
        <ScrollView>  
          <StackLayout>  
            <StackLayout Orientation="Horizontal" HorizontalOptions="FillAndExpand"  
                  BackgroundColor="#545454">  
              <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">  
                <Label Text="Search by Zip Code" TextColor="White" FontAttributes="Bold"  
                    FontSize="Medium" />  
                <Label x:Name="zipCodeLabel" Text="Zip Code" Style="{StaticResource labelStyle}" />  
                <Entry x:Name="zipCodeEntry" />  
              </StackLayout>  
              <StackLayout Padding="0,0,0,10" VerticalOptions="End">  
                <Button x:Name="getWeatherBtn" Text="Get Weather" WidthRequest="185" BorderWidth="1" >  
                  <!-- Set iOS colors; use defaults on other platforms -->  
                  <Button.TextColor>  
                    <OnPlatform x:TypeArguments="Color" iOS="White"/>  
                  </Button.TextColor>  
                  <Button.BorderColor>  
                    <OnPlatform x:TypeArguments="Color" iOS="White"/>  
                  </Button.BorderColor>  
                </Button>  
              </StackLayout>  
            </StackLayout>  
            <StackLayout Padding="10,10,10,10" HorizontalOptions="Start">  
              <Label Text="Location" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label Text="{Binding Title}" Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Temperature" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="tempLabel" Text="{Binding Temperature}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Wind Speed" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="windLabel" Text="{Binding Wind}" Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Humidity" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="humidityLabel" Text="{Binding Humidity}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Visibility" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="visibilitylabel" Text="{Binding Visibility}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Time of Sunrise" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="sunriseLabel" Text="{Binding Sunrise}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
              <Label Text="Time of Sunset" Style="{StaticResource labelStyle}" />  
              <ContentView Style="{StaticResource fieldView}">  
                <Label x:Name="sunsetLabel" Text="{Binding Sunset}"  
                    Style="{StaticResource fieldStyle}" />  
              </ContentView>  
            </StackLayout>  
          </StackLayout>  
        </ScrollView>  
      </ContentPage.Content>  
    </ContentPage>  
    ```  
  
     Všimněte si použití **OnPlatform** značku Xamarin.Forms. **OnPlatform** vybere hodnotu vlastnosti, které jsou specifické pro aktuální platformě, na kterém je spuštěna aplikace (viz [externí syntaxe jazyka XAML](http://developer.xamarin.com/guides/xamarin-forms/user-interface/xaml-basics/essential_xaml_syntax/) (xamarin.com). Používáme ji sem nastavit požadovanou barvu písma pro datová pole: bílé pro Android a Windows Phone, černé v systému iOS. Můžete použít **OnPlatform** pro všechny vlastnosti a všechny typy dat, provádět úpravy specifické pro platformu kdekoli v vaší XAML. V souboru kódu na pozadí, můžete použít [Device.OnPlatform API](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) k tomuto účelu.  
  
2.  V **WeatherPage.xaml.cs**, nahraďte **GetWeatherBtn_Clicked** obslužné rutiny události pomocí kódu níže. Tento kód ověřuje, že je PSČ pole Položka, načte data pro tento kód zip, nastaví kontext vazby na celé obrazovce výsledné instanci počasí a poté nastaví text tlačítka na "Vyhledat znovu." Všimněte si, že každý popisek v uživatelském rozhraní sváže vlastnost třídy, počasí, proto když nastavíte na kontext vazby na obrazovce **počasí** instance, tyto popisky aktualizovat automaticky.  
  
    ```csharp  
    private async void GetWeatherBtn_Clicked(object sender, EventArgs e)  
    {  
        if (!String.IsNullOrEmpty(zipCodeEntry.Text))  
        {  
            Weather weather = await Core.GetWeather(zipCodeEntry.Text);  
            this.BindingContext = weather;  
            getWeatherBtn.Text = "Search Again";  
        }  
    }  
    ```  
  
3.  Spuštění aplikace na všechny tři platformy: Android, iOS a Windows Phone – pravým tlačítkem na příslušný projekt, výběrem sady jako projekt po spuštění a spuštění aplikace na zařízení nebo v emulátor ani simulátor. Zadejte platné PSČ USA (například 60601) a klikněte na tlačítko získat počasí zobrazte údaje o počasí pro danou oblast, jak je uvedeno níže. Samozřejmě budete muset mít Visual Studio připojené k počítači Mac OS X ve vaší síti pro projekt pro iOS.  
  
     ![Ukázky počasí aplikaci pro Android, iOS a Windows Phone](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Úplný zdrojový kód pro tento projekt je v [xamarin-forms-samples úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).