---
title: Kontrola vlastností XAML při ladění | Dokumentace Microsoftu
ms.date: 03/06/2017
ms.topic: conceptual
ms.assetid: 390edde4-7b8d-4c89-8d69-55106b7e6b11
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: abb045b2fb0a1a465d4a5c4eb9efb33b6559b40f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53856426"
---
# <a name="inspect-xaml-properties-while-debugging"></a>Kontrola vlastností XAML při ladění
Můžete získat v reálném čase přehled o spuštění kódu XAML pomocí **Live Visual Tree** a **Live Property Explorer**. Tyto nástroje vám poskytnou stromové zobrazení prvků uživatelského rozhraní aplikace XAML spuštěné a zobrazit vlastnosti modulu runtime libovolný prvek uživatelského rozhraní, které vyberete.  
  
 Tyto nástroje můžete použít v následujících konfigurací:  
  
|Typ aplikace|Operační systém a nástroje|  
|-----------------|--------------------------------|  
|Aplikace Windows Presentation Foundation (4.0 a vyšší)|Windows 7 a vyšší|  
|Univerzální aplikace pro Windows|Windows 10 a novější, s [Windows 10 SDK](https://dev.windows.com/en-us/downloads/windows-10-sdk)|  
  
## <a name="looking-at-elements-in-the-live-visual-tree"></a>Prohlížení prvky v živý vizuální strom  
 Pusťme se do práce s velmi jednoduchou aplikaci WPF, která má zobrazení seznamu a tlačítko. Pokaždé, když kliknete na tlačítko, jiná položka se přidá do seznamu. Sudým číslem položky se zobrazí šedě a lichých položky se žlutou.  
  
 Vytvořte nový C# aplikace WPF (Soubor > Nový > projekt, vyberte C# a najít aplikace WPF). Pojmenujte ji **TestXAML**.  
  
 Změna souboru MainWindow.xaml takto:  
  
```xaml  
<Window x:Class="TestXAML.MainWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:local="clr-namespace:TestXAML"  
    mc:Ignorable="d"  
     Title="MainWindow" Height="350" Width="525">  
    <Grid>  
        <Button x:Name="button" Background="LightBlue" Content="Add Item" HorizontalAlignment="Left" Margin="216,206,0,0" VerticalAlignment="Top" Width="75" Click="button_Click"/>  
        <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="100" VerticalAlignment="Top" Width="100" Margin="205,80,0,0"/>  
    </Grid>  
</Window>  
```  
  
 Do souboru MainWindow.xaml.cs přidejte následující obslužná rutina příkazu:  
  
```csharp 
int count;

private void button_Click(object sender, RoutedEventArgs e)  
{  
    ListBoxItem item = new ListBoxItem();  
    item.Content = "Item" + ++count;  
    if (count % 2 == 0)  
    {  
        item.Background = Brushes.LightGray;  
    }  
    else  
    {  
        item.Background = Brushes.LightYellow;  
    }  
    listBox.Items.Add(item);  
}  
```  
  
 Sestavte projekt a spusťte ladění. (Konfiguraci sestavení musí být ladění, vydání není. Další informace o konfiguracích sestavení naleznete v tématu [Principy konfigurací sestavení](../ide/understanding-build-configurations.md).)  
  
 Když v okně se zobrazí, klikněte na tlačítko **přidat položku** tlačítko kolikrát pár. By měl vypadat přibližně takto:  
  
 ![Hlavní okno aplikace](../debugger/media/livevisualtree-app.png "LiveVIsualTree aplikace")  
  
 Nyní otevřete **Live Visual Tree** okno (**ladit > Windows > Live Visual Tree**, nebo ho najít na levé straně rozhraní IDE). Přetáhněte z jeho pozici ukotvení, abychom se mohli podívat na toto okno a **Live vlastnosti** okna vedle sebe. V **Live Visual Tree** okna, rozbalte **ContentPresenter** uzlu. Měl by obsahovat uzly pro tlačítka a pole se seznamem. Rozbalte pole se seznamem (a potom **ScrollContentPresenter** a **ItemsPresenter**) k nalezení seznamu položky pole. V okně by měl vypadat nějak takto:  
  
 ![Položky ListBoxItem v živý vizuální strom](../debugger/media/livevisualtree-listboxitems.png "LiveVisualTree položky ListBoxItem")  
  
 Vraťte se do okna aplikace a přidejte několik více položek. Měli byste vidět další seznam položek pole se zobrazí v **Live Visual Tree**.  
  
 Nyní Pojďme se podívat na vlastnosti položky seznamu pole. Vyberte první pole položky seznamu v **Live Visual Tree** a klikněte na tlačítko **zobrazit vlastnosti** ikonu na panelu nástrojů. **Live Property Explorer** by se měla objevit. Všimněte si, že **obsahu** pole je "Item1" a **pozadí** pole je **#FFFFFFE0** (světle žlutá). Přejděte zpět **Live Visual Tree** a vyberte druhou položku seznamu. **Live Property Explorer** by se zobrazit, který **obsahu** pole je "Item2 –" a **pozadí** pole je **#FFD3D3D3** (světle šedá ).  
  
 Skutečné struktury XAML obsahuje mnoho prvků, které vás zajímají pravděpodobně ne přímo, a pokud dobře neznáte kód může být obtížné provést procházení stromu najít, co hledáte. Proto **Live Visual Tree** má několik možností, které umožňují pomocí uživatelského rozhraní aplikace můžete najít element, které chcete prověřit.  
  
 **Povolit výběr v běžící aplikaci**. Tento režim můžete povolit, pokud vyberete tlačítko zcela vlevo **Live Visual Tree** nástrojů. S tímto režimem na můžete vybrat v aplikaci prvku uživatelského rozhraní a **Live Visual Tree** (a **Live prohlížeč vlastnost**) automaticky aktualizuje na Zobrazit uzel ve stromu tohoto prvku, odpovídající a její vlastnosti.  
  
 **Zobrazit doplňky pro úpravy rozložení v běžící aplikaci**. Tento režim můžete povolit při výběru tlačítka, které je okamžitě napravo od povolit tlačítko pro výběr. Když **zobrazit doplňky pro úpravy rozložení** zapnutý, způsobí, že zobrazíte vodorovné a svislé čáry podél hranice vybraného objektu, abyste si mohli zobrazit, co to odpovídá, a také obdélníky znázorňující okrajů okna aplikace. Například zapnutí i **povolit výběr** a **rozložení zobrazení** zapnuto a vyberte **přidat položku** textový blok v aplikaci. Byste měli vidět text uzlu bloku v **Live Visual Tree** a text blok ve vlastnosti **Live prohlížeč vlastnost**, a také vodorovné a svislé čáry na rozsah bloku textu.  
  
 ![LivePropertyViewer v DisplayLayout](../debugger/media/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer DisplayLayout")  
  
 **Zobrazit náhled výběru**. Tento režim můžete aktivovat tak, že vyberete třetí tlačítko na panelu nástrojů v dynamickém vizuálním stromu nalevo. Tento režim zobrazuje XAML, ve kterém se deklaroval element, pokud máte přístup ke zdrojovému kódu aplikace. Vyberte **povolit výběr** a **náhled výběru**, a pak klikněte na tlačítko v naší aplikaci test. Otevře se soubor MainWindow.xaml v sadě Visual Studio a je kurzor umístěn na řádku, kde je definován na tlačítko.  
  
## <a name="using-xaml-tools-with-running-applications"></a>Pomocí nástrojů XAML se spouštěním aplikací  
 Tyto nástroje XAML můžete použít i v případě, že nemáte zdrojový kód. Po připojení k běžící aplikaci XAML, můžete použít **Live Visual Tree** na prvcích uživatelského rozhraní aplikace příliš. Tady je příklad, pomocí stejné WPF testovací aplikaci, kterou jsme použili dříve.  
  
1.  Spustit **TestXaml** aplikace v rámci konfigurace verze. Nelze připojit k procesu, který běží v **ladění** konfigurace.  
  
2.  Spusťte druhou instanci aplikace Visual Studio a klikněte na tlačítko **ladit > připojit k procesu**. Najít **TestXaml.exe** v seznamu dostupných procesů, a klikněte na tlačítko **připojit**.  
  
3.  Spuštění aplikace.  
  
4.  Ve druhé instanci aplikace Visual Studio, otevřete **Live Visual Tree** (**ladit > Windows > Live Visual Tree**). Měli byste vidět **TestXaml** prvky uživatelského rozhraní a měli být schopni s nimi manipulovat, protože při ladění aplikace přímo.