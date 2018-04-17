---
title: Přidání ovládacího prvku uživatele na úvodní stránce | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- start page dll
- custom start page
- start page assembly
ms.assetid: 5b7997db-af6f-4fa9-a128-bceb42bddaf1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2bec2b4ab834eb55bd34a80f9e6a30931e3cd325
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="adding-user-control-to-the-start-page"></a>Přidání uživatelského ovládacího prvku do úvodní stránky
Tento návod ukazuje, jak přidat odkaz na stránku vlastní spuštění knihovny DLL. V příkladu přidáme sestavení uživatelského ovládacího prvku uživatelského ovládacího prvku k řešení a pak odkazuje na sestavení vytvořené ze souboru XAML – úvodní stránka. Novou kartu hostitelem uživatelského ovládacího prvku, který funguje jako základní webový prohlížeč.  
  
 Můžete použít stejný postup pro přidání jakékoli sestavení, kterou lze volat ze souboru XAML.  
  
## <a name="adding-a-wpf-user-control-to-the-solution"></a>Přidávání do řešení uživatelský ovládací prvek WPF  
 Nejprve přidejte uživatelský ovládací prvek Windows Presentation Foundation (WPF) – úvodní stránka řešení.  
  
1.  Vytvoření – úvodní stránka pomocí jsme vytvořili [vytváření vlastní – úvodní stránka](../extensibility/creating-a-custom-start-page.md).  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení, klikněte na **přidat**a potom klikněte na **nový projekt**.  
  
3.  V levém podokně **nový projekt** dialogové okno, rozbalte seznam buď **jazyka Visual Basic** nebo **Visual C#** uzel a klikněte na tlačítko **Windows**. V prostředním podokně vyberte **knihovny ovládací prvek WPF uživatelského**.  
  
4.  Název ovládacího prvku `WebUserControl` a pak klikněte na **OK**.  
  
## <a name="implementing-the-user-control"></a>Implementace uživatelského ovládacího prvku  
 K implementaci uživatelský ovládací prvek WPF, uživatelské rozhraní (UI) v jazyce XAML a pak zapsat události kódu v C# nebo jiném jazyce .NET.  
  
#### <a name="to-write-the-xaml-for-the-user-control"></a>Zápis XAML uživatelského ovládacího prvku  
  
1.  Otevřete soubor XAML uživatelského ovládacího prvku. V \<mřížky > elementu, přidejte následující definice řádku do ovládacího prvku.  
  
    ```vb  
    <Grid.RowDefinitions>  
        <RowDefinition Height="Auto"/>  
        <RowDefinition Height="*" />  
    </Grid.RowDefinitions>  
  
    ```  
  
2.  V hlavní `Grid` elementu, přidejte následující nové `Grid` element, který obsahuje textové pole pro zadání webové adresy a tlačítko pro nastavení novou adresu.  
  
    ```xml  
    <Grid Grid.Row="0">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="*" />  
            <ColumnDefinition Width="Auto" />  
        </Grid.ColumnDefinitions>  
        <TextBox x:Name="UserSource" Grid.Column="0" />  
        <Button Grid.Column="1" x:Name="SetButton" Content="Set Address" Click="SetButton_Click" />  
    </Grid>  
    ```  
  
3.  Přidejte následující rámečku do nejvyšší úrovně `Grid` element právě po `Grid` element, který obsahuje tlačítko a textové pole.  
  
    ```vb  
    <Frame Grid.Row="1" x:Name="WebFrame" Source="http://www.bing.com" Navigated="WebFrame_Navigated" />  
    ```  
  
4.  Následující příklad ukazuje dokončené XAML uživatelského ovládacího prvku.  
  
    ```xml  
    <UserControl x:Class="WebUserControl.UserControl1"  
                 xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
                 xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
                 xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"   
                 xmlns:d="http://schemas.microsoft.com/expression/blend/2008"   
                 mc:Ignorable="d"   
                 d:DesignHeight="300" d:DesignWidth="300">  
        <Grid>  
            <Grid.RowDefinitions>  
                <RowDefinition Height="Auto"/>  
                <RowDefinition Height="*" />  
            </Grid.RowDefinitions>  
            <Grid Grid.Row="0">  
                <Grid.ColumnDefinitions>  
                    <ColumnDefinition Width="*" />  
                    <ColumnDefinition Width="Auto" />  
                </Grid.ColumnDefinitions>  
                <TextBox x:Name="UserSource" Grid.Column="0" />  
                <Button Grid.Column="1" x:Name="SetButton" Content="Set Address" Click="SetButton_Click" />  
            </Grid>  
            <Frame Grid.Row="1" x:Name="WebFrame" Source="http://www.bing.com" Navigated="WebFrame_Navigated" />  
        </Grid>  
    </UserControl>  
  
    ```  
  
#### <a name="to-write-the-code-behind-events-for-the-user-control"></a>Zapsat události kódu pro uživatelský ovládací prvek  
  
1.  V Návrháři XAML, dvakrát klikněte **nastavit adresu** tlačítko, které jste přidali do ovládacího prvku.  
  
     UserControl1.cs soubor se otevře v editoru kódu.  
  
2.  Obslužné rutiny události SetButton_Click vyplňte takto.  
  
    ```csharp  
    private void SetButton_Click(object sender, RoutedEventArgs e)  
    {  
        try  
        {  
            this.WebFrame.Source = new Uri(this.UserSource.Text, UriKind.Absolute);  
        }  
        catch (Exception error)  
        {  
            MessageBox.Show(error.Message);  
        }  
    }  
    ```  
  
     Tento kód nastaví webovou adresu, kterou je zadán v textovém poli jako cíl pro webový prohlížeč. Pokud adresa není platná, kód vrátí chybu.  
  
3.  Musíte také zpracovat událost WebFrame_Navigated:  
  
    ```csharp  
    private void WebFrame_Navigated(object sender, EventArgs e)  
    { }  
    ```  
  
4.  Sestavte řešení.  
  
## <a name="adding-the-user-control-to-the-start-page"></a>Přidání uživatelského ovládacího prvku do úvodní stránky  
 Chcete-li k dispozici pro projekt – úvodní stránka tohoto ovládacího prvku v souboru projektu – úvodní stránka, přidejte odkaz na nové knihovny ovládacího prvku. Potom můžete přidat ovládací prvek pro spuštění stránky XAML značek.  
  
1.  V **Průzkumníku řešení**, v projektu – úvodní stránka, klikněte pravým tlačítkem na **odkazy** a pak klikněte na **přidat odkaz na**.  
  
2.  Na **projekty** vyberte **WebUserControl** a pak klikněte na **OK**.  
  
3.  Na **sestavení** nabídky, klikněte na tlačítko **sestavit řešení**.  
  
     Sestavování řešení zpřístupňuje uživatelského ovládacího prvku IntelliSense pro další soubory v řešení.  
  
 Přidání ovládacího prvku do kódu stránky XAML spuštění, přidejte obor názvů odkaz na sestavení a pak umístit ovládací prvek na stránce.  
  
#### <a name="to-add-the-control-to-the-markup"></a>Přidání ovládacího prvku do kód  
  
1.  V **Průzkumníku**, otevřete soubor XAML – úvodní stránka.  
  
2.  V **XAML** podokně, přidejte následující deklarace oboru názvů do nejvyšší úrovně <xref:System.Windows.Controls.Grid> elementu.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3.  V **XAML** podokně, posuňte se \<mřížky > části.  
  
     Oddíl obsahuje <xref:System.Windows.Controls.TabControl> element v <xref:System.Windows.Controls.Grid> elementu.  
  
4.  Přidat \<TabControl > element obsahující \<TabItem > obsahující odkaz na váš uživatelský ovládací prvek.  
  
    ```xml  
  
    <TabItem Header="Web" Height="Auto">  
        <vsc:UserControl1 />  
    </TabItem>  
  
    ```  
  
 Nyní můžete otestovat ovládacího prvku.  
  
## <a name="testing-a-manually-created-custom-start-page"></a>Testování ručně vytvořené vlastní stránky Start  
  
1.  Kopírování souboru XAML a všechny podpůrné textových souborů nebo značek souborů do **%USERPROFILE%\My Documents\Visual Studio 2015\StartPages\\**  složky.  
  
2.  Pokud všechny ovládací prvky nebo typy v sestavení, které nejsou nainstalované Visual Studio, odkazuje na úvodní stránky, zkopírujte sestavení a vložte je do * sady Visual Studio instalační složky ***\Common7\IDE\PrivateAssemblies\\** .  
  
3.  Na příkazovém řádku Visual Studio, zadejte **devenv /rootsuffix Exp** otevřete experimentální instanci sady Visual Studio.  
  
4.  V experimentální instance, přejděte do **Nástroje / možnosti / prostředí nebo spuštění** a vyberte souboru XAML z **přizpůsobení úvodní stránka** rozevíracího seznamu.  
  
5.  Na **zobrazení** nabídky, klikněte na tlačítko **– úvodní stránka**.  
  
     Má být zobrazena vlastní úvodní stránky. Pokud chcete změnit všechny soubory, musíte Ukončete experimentální instanci, proveďte požadované změny, zkopírovat a vložit změněné soubory a pak znovu otevřete experimentální instanci Chcete-li zobrazit změny.  
  
## <a name="see-also"></a>Viz také  
 [Ovládací prvky kontejneru WPF](http://msdn.microsoft.com/en-us/a0177167-d7db-4205-9607-8ae316952566)   
 [Návody: Přidání vlastního souboru XAML na úvodní stránku](../extensibility/walkthrough-adding-custom-xaml-to-the-start-page.md)