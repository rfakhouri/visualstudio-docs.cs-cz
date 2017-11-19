---
title: "Návod: Ukládání uživatelských nastavení na stránce Start | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 754b9bf3-8681-4c77-b0a4-09146a4e1d2d
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7a7d8649e0d8cf83650da58386901e638ec14a2a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-saving-user-settings-on-a-start-page"></a>Návod: Ukládání uživatelských nastavení na stránce Start
Můžete zachovat uživatelská nastavení pro úvodní stránku. Podle tohoto návodu, můžete vytvořit ovládací prvek, který uloží nastavení registru, když uživatel klikne na tlačítko a potom načte nastavení pokaždé, když se načte stránce Start. Vzhledem k tomu, že šablona projektu – úvodní stránka obsahuje přizpůsobitelný uživatelského ovládacího prvku a výchozí spuštění stránky XAML volá tuto kontrolu, nemáte upravit stránce Start sám sebe.  
  
 Nastavení úložiště, která je vytvořena instance v tomto návodu je instance <xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore> rozhraní, která čte a zapisuje do následujícího umístění registru, když je volána: HKCU\Software\Microsoft\VisualStudio\14.0\\  *Název_kolekce*  
  
 Když je spuštěn v experimentální instanci sady Visual Studio, úložišti nastavení čte a zapisuje HKCU\Software\Microsoft\VisualStudio\14.0Exp\\*název_kolekce.*  
  
 Další informace o tom, jak zachovat nastavení najdete v tématu [rozšíření uživatelská nastavení a možnosti](../extensibility/extending-user-settings-and-options.md).  
  
## <a name="prerequisites"></a>Požadavky  
  
> [!NOTE]
>  Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
>   
>  Šablona projektu – úvodní stránka si můžete stáhnout pomocí **Správce rozšíření**.  
  
## <a name="setting-up-the-project"></a>Nastavení projektu  
  
#### <a name="to-configure-the-project-for-this-walkthrough"></a>Ke konfiguraci projektu v tomto návodu  
  
1.  Vytvoření projektu – úvodní stránka, jak je popsáno v [vytváření vlastní – úvodní stránka](creating-a-custom-start-page.md). Název projektu **SaveMySettings**.  
  
2.  V **Průzkumníku**, přidejte následující odkazy na sestavení do projektu StartPageControl:  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Sestavení Microsoft.VisualStudio.OLE.Interop  
  
    -   Microsoft.VisualStudio.Shell.Interop.11.0  
  
3.  Otevřete MyControl.xaml.  
  
4.  V podokně XAML, v nejvyšší úrovně <xref:System.Windows.Controls.UserControl> definice elementu, přidejte následující deklarace události po deklarace oboru názvů.  
  
    ```  
    Loaded="OnLoaded"  
    ```  
  
5.  V podokně návrhu klikněte na hlavní oblast ovládacího prvku a stiskněte klávesu DELETE.  
  
     Odebere se tak <xref:System.Windows.Controls.Border> elementu a veškerý obsah a nechá pouze nejvyšší úrovně <xref:System.Windows.Controls.Grid> elementu.  
  
6.  Z **sada nástrojů**, přetáhněte ji <xref:System.Windows.Controls.StackPanel> řízení k mřížce.  
  
7.  Nyní přetáhněte <xref:System.Windows.Controls.TextBlock>, <xref:System.Windows.Controls.TextBox>a potom tlačítko <xref:System.Windows.Controls.StackPanel>.  
  
8.  Přidat **x: Name** atribut pro <xref:System.Windows.Controls.TextBox>a `Click` události <xref:System.Windows.Controls.Button>, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <StackPanel Width="300" HorizontalAlignment="Center" VerticalAlignment="Center">  
        <TextBlock Width="140" FontSize="14">Enter your setting</TextBlock>  
        <TextBox x:Name="txtblk" Margin="0, 5, 0, 10" Width="140" />  
        <Button Click="Button_Click" Width="100">Save My Setting</Button>  
    </StackPanel>  
    ```  
  
## <a name="implementing-the-user-control"></a>Implementace uživatelského ovládacího prvku  
  
#### <a name="to-implement-the-user-control"></a>K implementaci uživatelského ovládacího prvku  
  
1.  V podokně XAML, klikněte pravým tlačítkem myši `Click` atribut <xref:System.Windows.Controls.Button> elementu a pak klikněte na tlačítko **přejděte k obslužné rutině událostí**.  
  
     To otevře MyControl.xaml.cs a vytvoří se zakázaným inzerováním obslužnou rutinu pro `Button_Click` událostí.  
  
2.  Přidejte následující `using` příkazů do horní části souboru.  
  
     [!code-csharp[StartPageDTE#11](../extensibility/codesnippet/CSharp/walkthrough-saving-user-settings-on-a-start-page_1.cs)]  
  
3.  Přidat privátního `SettingsStore` vlastnost, jak je znázorněno v následujícím příkladu.  
  
    ```csharp  
    private IVsWritableSettingsStore _settingsStore = null;  
    private IVsWritableSettingsStore SettingsStore  
    {  
        get  
        {  
            if (_settingsStore == null)  
            {  
                // Get a reference to the DTE from the DataContext.   
                var typeDescriptor = DataContext as ICustomTypeDescriptor;  
                var propertyCollection = typeDescriptor.GetProperties();  
                var dte = propertyCollection.Find("DTE", false).GetValue(  
                    DataContext) as DTE2;  
  
                // Get the settings manager from the DTE.   
                var serviceProvider = new ServiceProvider(  
                    (Microsoft.VisualStudio.OLE.Interop.IServiceProvider)dte);  
                var settingsManager = serviceProvider.GetService(  
                    typeof(SVsSettingsManager)) as IVsSettingsManager;  
  
                // Write the user settings to _settingsStore.  
                settingsManager.GetWritableSettingsStore(  
                    (uint)__VsSettingsScope.SettingsScope_UserSettings,  
                    out _settingsStore);  
            }  
            return _settingsStore;  
        }  
    }  
    ```  
  
     Tato vlastnost nejdřív získá odkaz na <xref:EnvDTE80.DTE2> rozhraní, které obsahuje objekt modelu automatizace, z <xref:System.Windows.FrameworkElement.DataContext%2A> uživatelský ovládací prvek, a poté používá DTE získat instanci <xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsManager> rozhraní. Pak používá tuto instanci k vrácení nastavení aktuálního uživatele.  
  
4.  Vyplňte `Button_Click` událostí následujícím způsobem.  
  
    ```csharp  
    private void Button_Click(object sender, RoutedEventArgs e)  
    {  
        int exists = 0;  
        SettingsStore.CollectionExists("MySettings", out exists);  
        if (exists != 1)  
        {  
            SettingsStore.CreateCollection("MySettings");  
        }  
        SettingsStore.SetString("MySettings", "MySetting", txtblk.Text);  
    }  
    ```  
  
     Tento obsah textového pole zapíše do pole "MySetting" v kolekci "MySettings" v registru. Pokud kolekce neexistuje, vytvoří se.  
  
5.  Přidejte následující obslužnou rutinu pro `OnLoaded` událostí uživatelského ovládacího prvku.  
  
    ```csharp  
    private void OnLoaded(Object sender, RoutedEventArgs e)  
    {  
        string value;  
        SettingsStore.GetStringOrDefault(  
            "MySettings", "MySetting", "", out value);  
        txtblk.Text = value;  
    }  
    ```  
  
     Nastaví tato text do textového pole na aktuální hodnotu "MySetting".  
  
6.  Vytvoření uživatelského ovládacího prvku.  
  
7.  V **Průzkumníku**, otevřete source.extension.vsixmanifest.  
  
8.  V editoru manifestu nastavit **název produktu** k **uložit stránku spustit nastavení**.  
  
     Toto nastaví název stránce Start, jak se má zobrazit v **přizpůsobení úvodní stránka** v seznamu **možnosti** dialogové okno.  
  
9. Sestavení StartPage.xaml.  
  
## <a name="testing-the-control"></a>Testování ovládacího prvku  
  
#### <a name="to-test-the-user-control"></a>K testování uživatelského ovládacího prvku  
  
1.  Stiskněte klávesu F5.  
  
     Otevře se experimentální instanci sady Visual Studio.  
  
2.  V experimentální instanci na **nástroje** nabídky, klikněte na tlačítko **možnosti**.  
  
3.  V **prostředí** uzel, klikněte na tlačítko **spuštění**a pak na **přizpůsobení úvodní stránka** seznamu, vyberte **[nainstalovaná rozšíření] uložit Moje nastavení úvodní stránku** .  
  
     Click **OK**.  
  
4.  Zavřete stránku spustit, pokud je spuštěna a potom na **zobrazení** nabídky, klikněte na tlačítko **– úvodní stránka**.  
  
5.  Na stránce Start klikněte na **MůjOvládacíPrvek** kartě.  
  
6.  Do textového pole zadejte **Cat**a potom klikněte na **uložit Moje nastavení**.  
  
7.  Zavřete stránku spustit a znovu ho otevřete.  
  
     Slovo "Kočka" má být zobrazena v textovém poli.  
  
8.  Nahraďte je slovo "Kočka" slova "Pes". Neklikejte na tlačítko.  
  
9. Zavřete stránku spustit a znovu ho otevřete.  
  
     Slova "Pes" má být zobrazena v textovém poli to i v případě nastavení nebyla uložena. K tomu dojde, protože Visual Studio udržuje nástroje systému windows v paměti, i v případě, že budou uzavřeny, dokud nezavřete Visual Studio, sám sebe.  
  
10. Ukončete experimentální instanci sady Visual Studio.  
  
11. Stisknutím klávesy F5 znovu otevřete experimentální instanci.  
  
12. Slovo "Kočka" má být zobrazena v textovém poli.  
  
## <a name="next-steps"></a>Další kroky  
 Můžete upravit tento uživatelský ovládací prvek pro uložení a načtení libovolný počet vlastních nastavení za použití různých hodnot z různých obslužných rutin k získání a nastavení `SettingsStore` vlastnost. Také můžete použít jinou konzolu `propertyName` parametr pro každé volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsWritableSettingsStore.SetString%2A>, nepřepíše navzájem hodnoty v registru.  
  
## <a name="see-also"></a>Viz také  
 <xref:EnvDTE80.DTE2?displayProperty=fullName>     
 [Přidání příkazů sady Visual Studio na úvodní stránky](../extensibility/adding-visual-studio-commands-to-a-start-page.md)