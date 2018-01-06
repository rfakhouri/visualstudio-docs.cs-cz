---
title: "Vývoj aplikací s nativní uživatelského rozhraní v sadě Visual Studio pomocí Xamarin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30f137e6-595d-4ce7-b8f5-415b07c1caa2
caps.latest.revision: "31"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: xamarin
ms.openlocfilehash: c135468e380bd65383f61aa69b906352a3febe47
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="build-apps-with-native-ui-using-xamarin-in-visual-studio"></a>Vývoj aplikací s nativní uživatelského rozhraní pomocí Xamarinu v sadě Visual Studio
Jakmile provedete kroky krok [nastavení a instalaci](../cross-platform/setup-and-install.md) a [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md), tento postup vám ukáže, jak vytvořit základní aplikaci Xamarin (zobrazené dole) s vrstvami nativní uživatelského rozhraní. Nativní uživatelského rozhraní sdíleného kódu se nachází v knihovny přenosných tříd (PCL) a jednotlivé platformy projekty obsahovat definice uživatelského rozhraní.  
  
 ![Aplikace Xamarin pro Android a Windows Phone](../cross-platform/media/cross-plat-xamarin-build-1.png "sestavení Xamarin Cross-Plat 1")  
  
 Můžete to udělat ji od sestavit tyto věci:  
  
-   [Nastavit řešení](#solution)  
  
-   [Zápis kódu služby sdílených dat](#dataservice)  
  
-   [Návrh uživatelského rozhraní pro Android](#Android)  
  
-   [Návrh uživatelského rozhraní pro Windows Phone](#Windows)  
  
-   [Další kroky](#next)  
  
> [!TIP]
>  Můžete najít úplný zdrojový kód pro tento projekt v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).
>
>   Pokud máte problémy nebo dojde k chybám, odešlete prosím dotazy na [forums.xamarin.com](http://forums.xamarin.com). Mnoho chyb lze vyřešit aktualizací na nejnovější SDK vyžaduje Xamarin, které jsou popsány v [k vydání verze Xamarinu](https://developer.xamarin.com/releases/) pro každou platformu.    
  
> [!NOTE]
>  Dokumentaci pro vývojáře pro Xamarin také nabízí několik návody s rychlý start a podrobné informace, jak je uvedeno dále. Na těchto stránkách Ujistěte se, zda "Visual Studio" je vybrán v pravém horním rohu stránky zobrazíte návody pro Visual Studio specifické.  
>   
>  -   Xamarin aplikace s nativní uživatelského rozhraní:  
>   
>      -   [Hello, Android](https://developer.xamarin.com/guides/android/getting_started/hello,android/) (jednoduché aplikace s jednu obrazovku)  
>     -   [Hello, Android Multiobrazovka](https://developer.xamarin.com/guides/android/getting_started/hello,android_multiscreen/) (aplikace s navigace mezi obrazovkami)  
>     -   [Android návod fragmenty](http://developer.xamarin.com/guides/android/platform_features/fragments/fragments_walkthrough/) (používá se pro obrazovky a podrobností, mimo jiné)  
>     -   [Hello, iOS](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/)  
>     -   [Hello, iOS Multiscreen](https://developer.xamarin.com/guides/ios/getting_started/hello,_iOS_multiscreen/)  
> -   Aplikace Xamarin s Xamarin.Forms (sdílené uživatelského rozhraní)  
>   
>      -   [Hello, Xamarin.Forms](https://developer.xamarin.com/guides/cross-platform/xamarin-forms/getting-started/hello-xamarin-forms/quickstart/)  
>     -   [Hello, Multiobrazovka Xamarin.Forms](https://developer.xamarin.com/guides/cross-platform/xamarin-forms/getting-started/hello-xamarin-forms-multiscreen/)  
  
##  <a name="solution"></a>Nastavit řešení  
 Těchto kroků vytvořte Xamarin řešení s nativní uživatelského rozhraní, která obsahuje PCL pro sdílené kód a dvě přidání balíčků NuGet.  
  
1.  V sadě Visual Studio vytvořte novou **prázdná aplikace (nativní přenosné)** řešení a pojmenujte ji **WeatherApp**. Tuto šablonu lze snadno najít zadáním **nativní přenosné** do pole hledání.  
  
     Pokud tam není, možná budete muset nainstalovat Xamarin nebo povolit funkci Visual Studio 2015, najdete v části [nastavení a instalaci](../cross-platform/setup-and-install.md).  
  
2.  Po kliknutí na tlačítko OK, abyste vytvořili řešení, budete mít počtu jednotlivých projektů:  
  
    -   **WeatherApp (přenositelností)**: PCL, kde budete psát kód, který je sdílen napříč platformami, včetně běžné obchodní logiky a kód uživatelského rozhraní pomocí Xamarin.Forms.  
  
    -   **WeatherApp.Droid**: projekt, který obsahuje nativní kód pro Android. To je nastaven jako výchozí projekt po spuštění.  
  
    -   **WeatherApp.iOS**: projekt, který obsahuje kód nativní aplikace pro iOS.  
  
    -   **WeatherApp.WinPhone (Windows Phone 8.1)**: projekt, který obsahuje nativní kód pro Windows Phone.  
  
     V rámci každé nativnímu projektu mít přístup k nativní designer pro odpovídající platformu a můžete implementovat určité obrazovky platformy.  
  
3.  Přidat **Newtonsoft.Json** a balíček NuGet do projektu PCL, který použijete ke zpracování informace získané z datové služby počasí:  
  
    -   Klikněte pravým tlačítkem na **řešení 'WeatherApp'** v Průzkumníku řešení a vyberte **spravovat balíčky NuGet pro řešení...** .  
  
         V okně NuGet, vyberte **Procházet** kartě a vyhledejte **Newtonsoft**.  
  
    -   Vyberte **Newtonsoft.Json**.  
  
    -   Na pravé straně okna, zkontrolujte **WeatherApp** projektu (Toto je pouze projektu, ve kterém je potřeba k instalaci balíčku).  
  
    -   Ujistěte se, **verze** pole je nastaveno **nejnovější stabilní** verze.  
  
    -   Klikněte na tlačítko **nainstalovat**.  
  
    -   ![Vyhledání a instalace balíčku Newtonsoft.Json NuGet](../cross-platform/media/crossplat-xamarin-formsguide-5.png "CrossPlat Xamarin FormsGuide 5")  
  
4.  Zopakujte kroky 3 a najít a nainstalovat **Microsoft.Net.Http** balíčku.  
  
5.  Sestavte řešení a ověřte, zda nejsou žádné chyby sestavení.  
  
##  <a name="dataservice"></a>Zápis kódu služby sdílených dat  
 **WeatherApp (přenositelností)** projektu je, kde budete psát kód pro knihovny přenosných tříd (PCL), který je sdílen na všech platformách. PCL je automaticky součástí balíčků aplikací iOS, Android a Windows Phone sestavené projekty.  
  
 Následující kroky přidejte kód PCL pro přístup a ukládání dat z počasí služby:  
  
1.  Ke spuštění této ukázky musíte nejprve zaregistrovat pro bezplatné klíč rozhraní API v [http://openweathermap.org/appid](http://openweathermap.org/appid).  
  
2.  Klikněte pravým tlačítkem myši **WeatherApp** projektu a vyberte **Přidat > třída...** . V **přidat novou položku** dialogové okno, název souboru **Weather.cs**. Tato třída budete používat k ukládání dat ze služby počasí data.  
  
3.  Nahradí celý obsah **Weather.cs** následujícím kódem:  
  
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
  
4.  Přidejte jinou třídu do projektu PCL s názvem **DataService.cs** ve které budete používat zpracovat JSON data ze služby počasí data.  
  
5.  Nahradí celý obsah **DataService.cs** následujícím kódem:  
  
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
  
6.  Přidání třídy třetí PCL s názvem **základní** kam budete umísťovat sdílené obchodní logiky, například logiku, která tvoří řetězec dotazu s PSČ, zavolá službu data počasí a naplní instanci **počasí**třídy.  
  
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
                string key = "YOUR KEY HERE";  
                string queryString = "http://api.openweathermap.org/data/2.5/weather?zip="  
                    + zipCode + ",us&appid=" + key + "&units=imperial";  

                //Make sure developers running this sample replaced the API key
                if (key == "YOUR API KEY HERE")
                {
                    throw new ArgumentException("You must obtain an API key from openweathermap.org/appid and save it in the 'key' variable.");
                }
  
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
  
8.  Nahraďte *sem si klíč* v kódu pomocí klíč rozhraní API, které jste získali v kroku 1 (musí stále uvozovky kolem něj).  
  
9. MyClass.cs v PCL odstraňte, protože jsme nebude jej využívá.  
  
10. Sestavení **WeatherApp** PCL projektu a zkontrolujte, zda je správný kód.  
  
##  <a name="Android"></a>Návrh uživatelského rozhraní pro Android  
 Nyní jsme budete návrh uživatelského rozhraní, připojte ho k sdíleného kódu a pak spusťte aplikaci.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Návrh vzhledu a chování vaší aplikace  
  
1.  V **Průzkumníku řešení**, rozbalte **WeatherApp.Droid**>**prostředky**>**rozložení** složky a Otevřete **Main.axml**. Soubor se otevře v vizuálního návrháře. (Pokud se zobrazí chybě související s Java, najdete [příspěvku na blogu](http://forums.xamarin.com/discussion/32365/connection-to-the-layout-renderer-failed-in-xs-5-7-and-xamarinvs-3-9).)  
  
    > [!TIP]
    >  V projektu nejsou mnoho souborů. Prohlížení je je nad rámec tohoto tématu, ale pokud budete chtít do struktury projektu Android trochu další podrobné informace najdete v části [část 2 podrobné informace](http://developer.xamarin.com/guides/android/getting_started/hello,android/hello,android_deepdive/) Hello Android tématu na xamarin.com.  
  
2.  Vyberte a odstraňte výchozího tlačítka, který se zobrazí v návrháři.  
  
3.  Otevření panelu nástrojů s **zobrazení > jiných Windows > Sada nástrojů**.  
  
4.  Z **sada nástrojů**, přetáhněte ji **RelativeLayout** ovládacího prvku do návrháře. Tento ovládací prvek budete používat jako nadřazený kontejner pro další ovládací prvky.  
  
    > [!TIP]
    >  Pokud kdykoli asi není ke správnému zobrazení rozložení, soubor uložte a přepínání mezi **návrhu** a **zdroj** karet na aktualizovat.  
  
5.  V **vlastnosti** nastavte **pozadí** vlastnost (ve skupině styl) na `#545454`.  
  
6.  Z **sada nástrojů**, přetáhněte ji **TextView** na ovládací prvek **RelativeLayout** ovládacího prvku.  
  
7.  V **vlastnosti** okno, nastavte tyto vlastnosti (Poznámka: může pomoci seřadíte seznam podle abecedy pomocí tlačítka řazení v panelu nástrojů v okně Vlastnosti):  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**text**|**Vyhledávání podle PSČ**|  
    |**id**|`@+id/ZipCodeSearchLabel`|  
    |**layout_marginLeft**|`10dp`|  
    |**textColor**|`@android:color/white`|  
    |**stylu písma**|`bold`|  
  
    > [!TIP]
    >  Všimněte si, že mnoho vlastností nesmí obsahovat rozevírací seznam hodnot, které můžete vybrat.  Může být obtížné uhodnout jaké řetězcovou hodnotu pro danou vlastnost. Návrhy, zkuste vyhledávání pro název vlastnosti v [R.attr](http://developer.android.com/reference/android/R.attr.html) třídy stránky.  
    >   
    >  Navíc vyhledávání na webu rychlý často vede na stránku [http://stackoverflow.com/](http://stackoverflow.com/) kde ostatní používá stejnou vlastnost.  
  
     Pro odkaz, pokud přejdete na **zdroj** zobrazení, měli byste vidět následující kód pro tento element:  
  
    ```xml  
    <TextView  
        android:text="Search by Zip Code"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:id="@+id/ZipCodeSearchLabel"  
        android:layout_centerVertical="true"  
        android:layout_marginLeft="10dp"  
        android:textColor="@android:color/white"  
        android:textStyle="bold" />  
  
    ```  
  
8.  Z **sada nástrojů**, přetáhněte **TextView** na ovládací prvek **RelativeLayout** řízení a umístěte jej pod ZipCodeSearchLabel ovládacího prvku. To provedete vyřazení nový ovládací prvek na příslušné okraji existujícího ovládacího prvku; pomáhá zvětšení v poněkud návrháře pro tento.  
  
9. V **vlastnosti** okno, nastavte tyto vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**text**|**PSČ**|  
    |**id**|`@+id/ZipCodeLabel`|  
    |**layout_marginLeft**|`10dp`|  
    |**layout_marginTop**|`5dp`|  
  
     Kód v **zdroj** zobrazení by měl vypadat takto:  
  
    ```xml  
    <TextView  
        android:text="Zip Code"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/ZipCodeSearchLabel"  
        android:id="@+id/ZipCodeLabel"  
        android:layout_marginTop="5dp"  
        android:layout_marginLeft="10dp" />  
    ```  
  
10. Z **sada nástrojů**, přetáhněte **číslo** na ovládací prvek **RelativeLayout**, umístit níže **PSČ** popisek. Nastavte následující vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**id**|`@+id/zipCodeEntry`|  
    |**layout_marginLeft**|`10dp`|  
    |**layout_marginBottom**|`10dp`|  
    |**Šířka**|`165dp`|  
  
     Znovu kód:  
  
    ```xml  
    <EditText  
        android:inputType="number"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_below="@id/ZipCodeLabel"  
        android:id="@+id/zipCodeEntry"  
        android:layout_marginLeft="10dp"  
        android:layout_marginBottom="10dp"  
        android:width="165dp" />  
    ```  
  
11. Z **sada nástrojů**, přetáhněte **tlačítko** na **RelativeLayout** řízení a umístit je napravo od ovládacího prvku zipCodeEntry. Nastavte tyto vlastnosti:  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**id**|`@+id/weatherBtn`|  
    |**text**|**Získat informace o počasí**|  
    |**layout_marginLeft**|`20dp`|  
    |**layout_alignBottom**|`@id/zipCodeEntry`|  
    |**Šířka**|`165dp`|  
  
    ```xml  
    <Button    android:text="Get Weather"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_toRightOf="@id/zipCodeEntry"  
        android:id="@+id/weatherBtn"  
        android:layout_marginLeft="20dp"  
        android:layout_alignBottom="@id/zipCodeEntry"  
        android:width="165dp" />  
    ```  
  
12. Nyní máte dostatek zkušeností k vytvoření základní uživatelské rozhraní pomocí návrháře Android. Můžete také vytvořit uživatelského rozhraní tak, že přidáte kód přímo do souboru .asxml stránky. K sestavení rest UI tímto způsobem, přepněte do zobrazení zdroje v návrháři, a potom po následující kód *pod* `</RelativeLayout>` značky (Ano, který je pod značky... tyto elementy nejsou obsaženy v ReleativeLayout).  
  
    ```xml  
    <TextView  
            android:text="Location"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/locationLabel"  
            android:layout_marginLeft="10dp"  
            android:layout_marginTop="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/locationText"  
            android:layout_marginLeft="20dp"  
            android:layout_marginBottom="10dp" />  
        <TextView  
            android:text="Temperature"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/tempLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/tempText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Wind Speed"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/windLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/windText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Humidity"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/humidtyLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/humidityText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Visibility"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/visibilityLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/visibilityText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Time of Sunrise"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunriseLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunriseText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
        <TextView  
            android:text="Time of Sunset"  
            android:textAppearance="?android:attr/textAppearanceSmall"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunsetLabel"  
            android:layout_marginLeft="10dp" />  
        <TextView  
            android:textAppearance="?android:attr/textAppearanceMedium"  
            android:layout_width="match_parent"  
            android:layout_height="wrap_content"  
            android:id="@+id/sunsetText"  
            android:layout_marginBottom="10dp"  
            android:layout_marginLeft="20dp" />  
  
    ```  
  
13. Uložte tento soubor a přepněte do **návrhu** zobrazení. Uživatelské rozhraní by měl vypadat takto:  
  
     ![Uživatelské rozhraní pro aplikace pro Android](../cross-platform/media/xamarin_androidui.png "Xamarin_AndroidUI")  
  
14. Otevřete **MainActivity.cs** a odstraňování řádků v *OnCreate* metoda, která odkazují na výchozí tlačítko, která byla vyjmuta dříve. Až budete hotoví, kód by měl vypadat například takto:  
  
    ```  
    protected override void OnCreate (Bundle bundle)  
    {  
        base.OnCreate (bundle);  
  
        // Set our view from the "main" layout resource  
        SetContentView (Resource.Layout.Main);  
    }  
    ```  
  
15. Sestavení projektu pro Android zkontrolujte vaši práci. Všimněte si, že vytváření přidá řízení ID chcete **Resource.Designer.cs** tak, aby mohou odkazovat na ovládací prvky podle názvu v kódu.  
  
### <a name="consume-your-shared-code"></a>Využívat sdílené kódu  
  
1.  Otevřete **MainActivity.cs** soubor **WeatherApp** projektu v editoru kódu a nahraďte jeho obsah pomocí kódu níže. Tento kód zavolá `GetWeather` metoda, která jste definovali ve vašem sdíleného kódu. Poté v uživatelském rozhraní aplikace zobrazuje data, která se načítají z dané metody.  
  
    ```csharp  
    using System;  
    using Android.App;  
    using Android.Widget;  
    using Android.OS;  
  
    namespace WeatherApp.Droid  
    {  
        [Activity(Label = "Sample Weather App", MainLauncher = true, Icon = "@drawable/icon")]  
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
  
### <a name="run-the-app-and-see-how-it-looks"></a>Spusťte aplikaci a v tématu Jak vypadá  
  
1.  V **Průzkumníku řešení**, zajistěte, aby **WeatherApp.Droid** projektu je nastavit jako spouštěný projekt.  
  
2.  Vyberte příslušné zařízení nebo emulátoru target a pak spusťte aplikaci stisknutím klávesy F5.  
  
3.  Na zařízení nebo v emulátoru, zadejte platné PSČ Spojených států do pole pro úpravy (například: 60601) a stiskněte klávesu **získat počasí**. Potom se data počasí pro danou oblast zobrazí v ovládacích prvcích.  
  
     ![Počasí aplikace pro Android a Windows Phone](../cross-platform/media/xamarin_getstarted_results.png "Xamarin_GetStarted_Results")  
  
> [!TIP]
>  Úplný zdrojový kód pro tento projekt je v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).  
  
##  <a name="Windows"></a>Návrh uživatelského rozhraní pro Windows Phone  
 Nyní jsme budete návrh uživatelského rozhraní pro Windows Phone, připojte ho k sdíleného kódu a pak spusťte aplikaci.  
  
### <a name="design-the-look-and-feel-of-your-app"></a>Návrh vzhledu a chování vaší aplikace  
 Proces návrhu nativní uživatelského rozhraní Windows Phone v aplikaci Xamarin se neliší od jiných nativní aplikace Windows Phone. Z tohoto důvodu jsme nebude přejděte do podrobnosti na tomto místě o tom, jak používat návrháře. Najdete v části [vytvoření uživatelského rozhraní pomocí návrháře XAML](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md).  
  
 Místo toho jednoduše otevřete MainPage.xaml a nahradit všechny kód XAML následující:  
  
```xaml  
<Page  
    x:Class="WeatherApp.WinPhone.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:WeatherApp.WinPhone"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d"  
    Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
  
    <Grid>  
        <StackPanel HorizontalAlignment="Left" Height="40" Margin="10,0,0,0" VerticalAlignment="Top" Width="400">  
            <TextBlock x:Name="pageTitle" Text="Weather App" FontSize="30" />  
        </StackPanel>  
        <StackPanel HorizontalAlignment="Left" Height="120" Margin="10,40,0,0" VerticalAlignment="Top" Width="400" Background="#FF545454">  
  
            <TextBlock x:Name="zipCodeSearchLabel" TextWrapping="Wrap" Text="Search by Zip Code" FontSize="18" FontWeight="Bold" HorizontalAlignment="Left" Margin="10,10,0,0"/>  
            <TextBlock x:Name="zipCodeLabel" TextWrapping="Wrap" Text="Zip Code" Margin="10,5,0,0" FontSize="14" Foreground="#FFA8A8A8"/>  
            <StackPanel Orientation="Horizontal">  
                <TextBox x:Name="zipCodeEntry" Margin="10,10,0,0" Text="" VerticalAlignment="Top" InputScope="Number" Width="165" />  
                <Button x:Name="weatherBtn" Content="Get Weather" Width="165" Margin="20,0,0,0" Height="60" Click="GetWeatherButton_Click"/>  
            </StackPanel>  
        </StackPanel>  
        <StackPanel Margin="10,175,0,0">  
            <TextBlock x:Name="locationLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Location" VerticalAlignment="Top"/>  
            <TextBlock x:Name="locationText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="tempLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Temperature" VerticalAlignment="Top"/>  
            <TextBlock x:Name="tempText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="windLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Wind Speed" VerticalAlignment="Top"/>  
            <TextBlock x:Name="windText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="humidityLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Humidity" VerticalAlignment="Top"/>  
            <TextBlock x:Name="humidityText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="visibilityLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Temperature" VerticalAlignment="Top"/>  
            <TextBlock x:Name="visibilityText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunriseLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Time of Sunriweatherse" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunriseText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunsetLabel" HorizontalAlignment="Left" FontSize="14" Foreground="#FFA8A8A8" TextWrapping="Wrap" Text="Time of Sunset" VerticalAlignment="Top"/>  
            <TextBlock x:Name="sunsetText" Margin="10,0,0,10" HorizontalAlignment="Left" FontSize="18" TextWrapping="Wrap" VerticalAlignment="Top"/>  
        </StackPanel>  
    </Grid>  
</Page>  
```  
  
 V okně návrhu uživatelské rozhraní se zobrazí následující:  
  
 ![Windows Phone rozhraní aplikace](../cross-platform/media/xamarin_winphone_finalui.png "Xamarin_WinPhone_FinalUI")  
  
### <a name="consume-your-shared-code"></a>Využívat sdílené kódu  
  
1.  V návrháři, vyberte **získat počasí** tlačítko.  
  
2.  V **vlastnosti** okně zvolte tlačítko obslužné rutiny události (![ikonu obslužné rutiny událostí Visual Studio](../cross-platform/media/blend_vs_eventhandlers_icon.png "blend_VS_EventHandlers_icon")).  
  
     Tato ikona se zobrazí v horním rohu **vlastnosti** okno.  
  
3.  Vedle položky **klikněte na tlačítko** událost, typ **GetWeatherButton_Click**a potom stiskněte klávesu ENTER.  
  
     Tento postup vytvoří obslužnou rutinu události s názvem `GetWeatherButton_Click`. Editor kódu otevře a umístí kurzor uvnitř bloku kódu obslužná rutina události.  Poznámka: Pokud editor neotevře při stisknutí klávesy ENTER, právě dvakrát klikněte na název události.  
  
4.  Tuto obslužnou rutinu události nahraďte následujícím kódem.  
  
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
  
     Tento kód zavolá `GetWeather` metoda, která jste definovali ve vašem sdíleného kódu. Toto je stejnou metodu, kterou jste volali metodu v aplikacích pro Android. Tento kód také ukazuje data načtená z dané metody v ovládacích prvků uživatelského rozhraní aplikace.  
  
5.  V MainPage.xaml.cs, která je otevřená, odstraňte všechny kód uvnitř **OnNavigatedTo** metoda. Tento kód jednoduše zpracovává výchozího tlačítka, která byla odebrána, když jsme nahradili obsah MainPage.xaml.  
  
### <a name="run-the-app-and-see-how-it-looks"></a>Spusťte aplikaci a v tématu Jak vypadá  
  
1.  V **Průzkumníku řešení**, nastavte **WeatherApp.WinPhone** projekt jako spouštěný projekt.  
  
2.  Spusťte aplikaci stisknutím klávesy F5.  
  
3.  V emulátoru Windows Phone, zadejte do pole pro úpravy platné PSČ USA (například: 60601) a stiskněte klávesu **získat počasí**. Potom se data počasí pro danou oblast zobrazí v ovládacích prvcích.  
  
     ![Verze Windows spuštěné aplikaci](../cross-platform/media/xamarin_getstarted_results_windows.png "Xamarin_GetStarted_Results_Windows")  
  
> [!TIP]
>  Úplný zdrojový kód pro tento projekt je v [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather).  
  
##  <a name="next"></a>Další kroky  
 **Do řešení přidat uživatelského rozhraní pro iOS**  
  
 Tato ukázka rozšiřte přidáním nativní uživatelského rozhraní pro iOS. Pro to budete potřebovat pro připojení k Mac ve vaší místní síti, která má Xcode a Xamarin nainstalován. Až to uděláte, můžete použít Návrháře iOS přímo v sadě Visual Studio. Najdete v článku [mobile-samples úložišti na Githubu](https://github.com/xamarin/mobile-samples/tree/master/Weather) pro dokončené aplikace.  
  
 Najdete také [Hello, iOS](http://developer.xamarin.com/guides/ios/getting_started/hello,_iOS/hello,iOS_quickstart/) návod (xamarin.com). Všimněte si, že na této stránce si být jisti "sadou Visual Studio" je vybraný v pravém horním rohu stránky na xamarin.com tak, aby správnou sadu pokynů.  
  
 **Přidání kódu pro konkrétní platformu v sdílený projekt**  
  
 Sdílené kód v PCL je neutrální k platformě, protože PCL kompiluje jednou a součástí každého balíčku aplikace specifické pro platformu. Pokud chcete napsat sdílené kód, který používá Podmíněná kompilace izolovat kódu pro konkrétní platformu, můžete použít *sdílené* projektu. Další podrobnosti najdete v tématu [možnosti sdílení funkce ode](http://developer.xamarin.com/guides/cross-platform/application_fundamentals/building_cross_platform_applications/sharing_code_options/) (xamarin.com).  
  
## <a name="see-also"></a>Viz také  
 [Xamarin vývojáře lokality](http://developer.xamarin.com/)   
 [Centrum vývojářů pro Windows](https://dev.windows.com/en-us)   
 [Stručná referenční příručka plakát SWIFT a C#](http://aka.ms/scposter)