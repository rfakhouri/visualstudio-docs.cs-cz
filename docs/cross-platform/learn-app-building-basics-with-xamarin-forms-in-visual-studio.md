---
title: "Další informace základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 01/19/2018
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d22b5186-9e03-4e85-afc9-7cbe28522a6d
caps.latest.revision: "11"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: xamarin
ms.openlocfilehash: 3a066156f66a4e89132010a8c83edc7029dbe19e
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="learn-app-building-basics-with-xamarinforms-in-visual-studio"></a>Další informace základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio
Jakmile provedete kroky krok [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md), tento postup vám ukáže, jak vytvořit základní aplikaci (zobrazené dole) s Xamarin.Forms. S Xamarin.Forms napíšete veškerý kód uživatelského rozhraní jednou v rozhraní .NET standardní knihovny tříd. Xamarin potom automaticky vykreslí nativní ovládacích prvků uživatelského rozhraní pro iOS, Android a Universal Windows platformy. Doporučujeme tuto metodu (nikoli projekt sdílené), protože .NET Standard knihovna obsahuje pouze rozhraní .NET API, které jsou podporovány v rámci všech cílových platforem a protože Xamarin.Forms umožňuje sdílet kód uživatelského rozhraní napříč platformami.  
  
 ![Ukázky počasí aplikaci pro Android, iOS a Windows](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Můžete to udělat ji od sestavit tyto věci:  
  
-   [Nastavit řešení](#solution)  
  
-   [Zápis kódu služby sdílených dat](#dataservice)  
  
-   [Zahájit zápis sdíleného kódu uživatelského rozhraní](#uicode)  
  
-   [Testování aplikace pomocí emulátor sady Visual Studio pro Android](#test)  
  
-   [Dokončit rozhraní s přirozený vzhled a chování napříč platformami](#finish)  
  
> [!TIP]
>  Můžete najít úplný zdrojový kód pro tento projekt v [xamarin-forms-samples úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).  
  
##  <a name="solution"></a>Nastavit řešení  
 Tyto kroky vytvářet řešení Xamarin.Forms, která obsahuje .NET standardní knihovny tříd pro sdílené kód a dvě přidání balíčků NuGet.  
  
1.  V sadě Visual Studio vytvořte novou **Multiplatformní aplikace (Xamarin.Forms)** řešení a pojmenujte ji **WeatherApp**. Pomocí příkazu Zobrazit šablony **Visual C#** a **napříč platformami** ze seznamu na levé straně.  
  
     Pokud tam není, možná budete muset nainstalovat Xamarin nebo Visual Studio 2017 funkci povolit, najdete v části [nastavení a instalaci](../cross-platform/setup-and-install.md).  
  
     ![Vytvoření nové prázdné aplikace &#40; Aplikace na platformě Xamarin.Forms napříč platformami &#41; projekt](../cross-platform/media/crossplat-xamarin-formsguide-2.png "CrossPlat Xamarin FormsGuide 2")

2.  Po kliknutí na tlačítko OK, máte možnost vybrat některé možnosti. Vyberte **prázdná aplikace**, **Xamarin.Forms** a **.NET Standard**:

     ![Vytvoření nového projektu mezi aplikace platformy](../cross-platform/media/crossplat-xamarin-formsguide-3.png "CrossPlat Xamarin FormsGuide 3")
  
3.  Po kliknutí na tlačítko OK, abyste vytvořili řešení, budete mít počtu jednotlivých projektů:  
  
    -   **WeatherApp**: .NET Standard knihovny, kde budete psát kód, který je sdílen napříč platformami, včetně běžné obchodní logiky a kód uživatelského rozhraní pomocí Xamarin.Forms.  
  
    -   **WeatherApp.Android**: projekt, který obsahuje nativní kód pro Android. To je nastaven jako výchozí projekt po spuštění.  
  
    -   **WeatherApp.iOS**: projekt, který obsahuje kód nativní aplikace pro iOS.  
  
    -   **WeatherApp.UWP**: projekt, který obsahuje kód Windows 10 UWP.  
  
    > [!NOTE]
    >  Jste volné odstraní všechny projekty pro platformu, která nejsou cílení.   
  
     V rámci každé nativnímu projektu mít přístup k nativní designer pro odpovídající platformu a můžete implementovat určité obrazovky platformy a funkce, podle potřeby.  
  
4.  Takto upgrade na nejnovější stabilní verze balíčku Xamarin.Forms NuGet ve vašem řešení. Doporučujeme, abyste to vždy, když vytvoříte nové řešení Xamarin:  
  
    -   Vyberte **nástroje > Správce balíčků NuGet > Správa balíčků NuGet pro řešení**.  
  
    -   V části **aktualizace** zkontrolujte **Xamarin.Forms** balíček a zkontrolujte aktualizovat všechny projekty v řešení. (Poznámka: nechte žádné aktualizace pro Xamarin.Android.Support nezaškrtnuté.)  
  
    -   Aktualizace **verze** do **nejnovější stabilní** verzi, která je k dispozici.  
  
    -   Klikněte na tlačítko **nainstalovat**.  
  
         ![Aktualizuje balíček Xamarin.Forms NuGet](../cross-platform/media/crossplat-xamarin-formsguide-4.png "CrossPlat Xamarin FormsGuide 4")  
  
5.  Přidat **Newtonsoft.Json** balíček NuGet, abyste **WeatherApp** projektu, který budete používat ke zpracování informace získané z datové služby počasí:  
  
    -   V Správce balíčků NuGet (stále otevřen z kroku 4), vyberte **Procházet** kartě a vyhledejte **Newtonsoft**.  
  
    -   Vyberte **Newtonsoft.Json**.  
  
    -   Zkontrolujte **WeatherApp** projektu (Toto je pouze projektu, ve kterém je potřeba k instalaci balíčku).  
  
    -   Ujistěte se, **verze** pole je nastaveno **nejnovější stabilní** verze.  
  
    -   Klikněte na tlačítko **nainstalovat**.  
  
    ![Vyhledání a instalace balíčku Newtonsoft.Json NuGet](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
6.  Opakujte krok 5 a najít a nainstalovat **Microsoft.Net.Http** balíčku.  
  
7.  Sestavte řešení a ověřte, zda nejsou žádné chyby sestavení.  
  
##  <a name="dataservice"></a>Zápis kódu služby sdílených dat  
 **WeatherApp** projektu je, kde budete psát kód pro knihovnu .NET Standard, který je sdílen na všech platformách. Tato knihovna je automaticky součástí aplikace balíčky sestavení iOS, Android a Windows projekty.  
  
 Pokud chcete tuto ukázku spustit, musíte nejprve zaregistrujete k bezplatné klíč rozhraní API v [http://openweathermap.org/appid](http://openweathermap.org/appid).  
  
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
  
5.  Přidejte třídu třetí k **WeatherApp** projektu s názvem **základní** kam budete umísťovat sdílené obchodní logiku. Tento kód forms řetězec dotazu s kódem zip, zavolá službu data počasí a naplní instanci **počasí** třídy.  
  
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
  
7.  Sestavení **WeatherApp** projekt knihovny zkontrolujte, zda je správný kód.  
  
##  <a name="uicode"></a>Zahájit zápis sdíleného kódu uživatelského rozhraní  
 Xamarin.Forms vám umožňují implementovat sdílený kód uživatelského rozhraní v knihovně .NET Standard. Tímto postupem přidáte na stránce do projektu s tlačítkem na aktualizace textu jeho s daty vrácených dat počasí služby kódu přidaném v předchozí části:  
  
1.  Přidat **obsahu stránce** s názvem **WeatherPage.cs** kliknutím pravým tlačítkem myši **WeatherApp** projekt a výběrem **Přidat > novou položku...** . V **přidat novou položku** dialogovém okně, vyberte **obsahu stránce**. Dejte pozor, abyste vyberte **obsahu stránce (C#)** nebo **zobrazení obsahu**. Pojmenujte ji **WeatherPage.cs**.  
  
     ![Přidání nové stránky Xamarin.Forms XAML](../cross-platform/media/crossplat-xamarin-formsguide-6.png "CrossPlat Xamarin FormsGuide 6")  
  
     Xamarin.Forms je založené na jazyce XAML, takže tento krok vytvoří **WeatherPage.xaml** soubor souborem vnořené kódu **WeatherPage.xaml.cs**. To umožňuje generování uživatelského rozhraní pomocí XAML nebo kódu. Můžete to udělat některé i v tomto návodu.  
  
2.  Přidání tlačítka na obrazovku WeatherPage, nahraďte obsah **WeatherPage.xaml** následujícím kódem:  
  
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
  
4.  Chcete-li otevřít **WeatherPage** jako první obrazovce při spuštění aplikace, nahradí výchozí konstruktor v **App.cs** následujícím kódem:  
  
    ```csharp  
    public App()  
    {
        InitializeComponent();

        MainPage = new NavigationPage(new WeatherPage());  
    }  
    ```  
  
5.  Sestavení **WeatherApp** projektu a zkontrolujte, zda je správný kód.  
  
##  <a name="test"></a>Testování aplikace pomocí emulátor sady Visual Studio pro Android  
 Teď můžete začít a spusťte aplikaci. Umožňuje spustit jenom Android verze teď chcete-li ověřit, že aplikace je získání dat ze služby počasí. Později také spustíte na iOS a verze UWP po přidání další prvky uživatelského rozhraní.   
  
1.  Nastavte **WeatherApp.Android** projekt jako spouštěný projekt pravým tlačítkem myši a výběrem **nastavit jako spouštěný projekt**.  
  
2.  Na panelu nástrojů Visual Studio se zobrazí **WeatherApp.Android** uveden jako cílový projekt. Vyberte jeden z Android emulátorů pro ladění a stiskněte tlačítko **F5**. Doporučujeme použít jednu z **Visual Studio** emulátoru možnosti, které bude aplikace spuštěna v emulátor sady Visual Studio pro Android.  
  
     ![Výběr cíli ladění emulátoru Android](../cross-platform/media/crossplat-xamarin-formsguide-7.png "CrossPlat Xamarin FormsGuide 7")  
  
3.  Při spuštění aplikace v emulátoru, klikněte **získat počasí** tlačítko. Byste měli vidět text na tlačítko Aktualizovat na **Chicagu**, který je *název* vlastnost dat získaný ze služby počasí.  
  
     ![Informace o počasí aplikace před a po klepnutím na tlačítko](../cross-platform/media/crossplat-xamarin-formsguide-8.png "CrossPlat Xamarin FormsGuide 8")  
  
##  <a name="finish"></a>Dokončit rozhraní s přirozený vzhled a chování napříč platformami  
 Xamarin.Forms vykreslí nativní ovládací prvky uživatelského rozhraní pro každou platformu, tak, aby vaše aplikace automaticky obsahuje přirozený vzhled a chování. Zobrazení tohoto informace je zřejmé, můžeme dokončit rozhraní s vstupní pole pro PSČ a následně se zobrazí počasí data, která je vrácena ze služby.  
  
1.  Nahraďte obsah **WeatherPage.xaml** pomocí kódu níže. Prvky, které jsou s názvem pomocí **x: Name** atributu, jak je popsáno výše, může být odkazován z kódu. Xamarin.Forms také poskytuje řadu [možnosti rozložení](http://developer.xamarin.com/guides/xamarin-forms/controls/layouts/) (xamarin.com). Zde je pomocí WeatherPage [mřížky](http://developer.xamarin.com/api/type/Xamarin.Forms.Grid/) (xamarin.com) a [StackLayout](http://developer.xamarin.com/api/type/Xamarin.Forms.StackLayout/) (xamarin.com).  
  
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
  
     I když není tady zobrazené, můžete použít **OnPlatform** značky a vyberte hodnotu vlastnosti, které jsou specifické pro aktuální platformě, na kterém je spuštěna aplikace (najdete v části [základní syntaxe XAML](http://developer.xamarin.com/guides/xamarin-forms/user-interface/xaml-basics/essential_xaml_syntax/) (xamarin.com). V souboru kódu na pozadí, můžete použít [Device.OnPlatform API](http://developer.xamarin.com/guides/xamarin-forms/platform-features/device/) k tomuto účelu.  
  
2.  V **WeatherPage.xaml.cs**, nahraďte **GetWeatherBtn_Clicked** obslužné rutiny události pomocí kódu níže. Tento kód ověřuje, že je PSČ pole Položka, načte data pro tento kód zip, nastaví kontext vazby na celou stránku výsledná **počasí** instance a poté nastaví text tlačítka na "Vyhledat znovu." Všimněte si, že každý popisek v uživatelském rozhraní se váže k vlastnost **počasí** třídy, tak při nastavení na obrazovce kontextu vazby na **počasí** instance, tyto popisky aktualizovat automaticky.  
  
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
  
3.  Spuštění aplikace na všech platformách tři – Android, iOS a Windows – tím pravým tlačítkem na příslušný projekt, výběr **nastavit jako spouštěný projekt**a spuštění aplikace na zařízení nebo v emulátor ani simulátor. Zadejte platné PSČ Spojených států pět číslic a stiskněte klávesu **získat počasí** tlačítko pro zobrazení dat počasí pro danou oblast, jak je uvedeno níže. Musíte mít Visual Studio připojené k počítači Mac OS X ve vaší síti pro projekt pro iOS.  
  
     ![Ukázky počasí aplikaci pro Android, iOS a Windows Phone](../cross-platform/media/crossplat-xamarin-formsguide-1.png "CrossPlat Xamarin FormsGuide 1")  
  
 Úplný zdrojový kód pro tento projekt je v [xamarin-forms-samples úložišti na Githubu](https://github.com/xamarin/xamarin-forms-samples/tree/master/Weather).