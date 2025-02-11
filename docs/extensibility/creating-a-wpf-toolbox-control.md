---
title: Vytvoření ovládacího prvku panel nástrojů WPF | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- toolbox control
- toolbox
- wpf
ms.assetid: 9cc34db9-b0d1-4951-a02f-7537fbbb51ad
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fc124c767ac9a84e62c17fb868e1dc114642f884
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66349035"
---
# <a name="create-a-wpf-toolbox-control"></a>Vytvoření ovládacího prvku panel nástrojů WPF

Šablony ovládacího prvku panelu nástrojů WPF (Windows Presentation Framework) umožňuje vytvořit ovládací prvky WPF, které jsou automaticky přidány do **nástrojů** při instalaci rozšíření. Tento návod ukazuje, jak použít šablonu k vytvoření **nástrojů** ovládacího prvku, které můžete distribuovat ostatním uživatelům.

Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-the-toolbox-control"></a>Vytvoření ovládacího prvku panelu nástrojů

### <a name="create-an-extension-with-a-wpf-toolbox-control"></a>Vytvoření rozšíření pomocí prvku sady nástrojů WPF

1. Vytvořte projekt VSIX s názvem `MyToolboxControl`. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".

2. Po otevření projektu, přidejte **ovládacího prvku panelu nástrojů WPF** šablony položky s názvem `MyToolboxControl`. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** > **nová položka**. V **přidat novou položku** dialogové okno, přejděte na **Visual C#**  > **rozšiřitelnost** a vyberte **ovládacího prvku panelu nástrojů WPF**. V **název** pole v dolní části okna, změňte název souboru příkazu *MyToolboxControl.cs*.

    Toto řešení nyní obsahuje uživatelský ovládací prvek, `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> , který přidá ovládací prvek **nástrojů**a **Microsoft.VisualStudio.ToolboxControl** položku prostředku v manifestu VSIX pro  nasazení.

#### <a name="to-create-the-control-ui"></a>Vytvoření ovládacího prvku uživatelského rozhraní

1. Otevřít *MyToolboxControl.xaml* v návrháři.

    Návrhář zobrazí <xref:System.Windows.Controls.Grid> ovládací prvek, který obsahuje <xref:System.Windows.Controls.Button> ovládacího prvku.

2. Upravte si rozložení mřížky. Když vyberete <xref:System.Windows.Controls.Grid> ovládací prvek, na horní a levé hrany mřížky se zobrazí modré ovládací panely. Kliknutím pruhy, můžete přidat řádků a sloupců do mřížky.

3. Přidejte podřízené ovládací prvky do mřížky. Podřízený ovládací prvek můžete umístit přetažením z **nástrojů** na oddíl v mřížce nebo nastavením jeho `Grid.Row` a `Grid.Column` atributů XAML. Následující příklad přidá dva popisky na horní řádek mřížky a tlačítko ve druhém řádku.

    ```xaml
    <Grid>
        <Label Grid.Row="0" Grid.Column="0" Name="label1" />
        <Label Grid.Row="0" Grid.Column="1" Name="label2" />
        <Button Name="button1" Click="button1_Click" Grid.Row="1" Grid.ColumnSpan="2" />
    </Grid>
    ```

## <a name="renaming-the-control"></a>Přejmenování ovládacího prvku

 Ve výchozím nastavení, zobrazí se váš ovládací prvek v **nástrojů** jako **MyToolboxControl** ve skupině s názvem **MyToolboxControl.MyToolboxControl**. Tyto názvy v můžete změnit *MyToolboxControl.xaml.cs* souboru.

1. Otevřít *MyToolboxControl.xaml.cs* v zobrazení kódu.

2. Najít `MyToolboxControl` třídy a přejmenujte jej na TestControl. (Nejrychlejší způsob, jak to provést, je pro tuto třídu přejmenovat vyberte **přejmenovat** v místní nabídce a proveďte nutné kroky. (Další informace o **přejmenovat** naleznete [přejmenovat refaktoringu (C#)](../ide/reference/rename.md).)

3. Přejděte `ProvideToolboxControl` atribut a změňte hodnotu prvním parametrem **Test**. Toto je název skupiny, která bude obsahovat ovládacího prvku **nástrojů**.

    Výsledný kód by měl vypadat takto:

    ```csharp
    [ProvideToolboxControl("Test", true)]
    public partial class TestControl : UserControl
    {
        public TestControl()
        {
            InitializeComponent();
        }
    }
    ```

## <a name="build-test-and-deployment"></a>Sestavování, testování a nasazení

 Při ladění projektu byste měli najít ovládací prvek nainstalovaný v **nástrojů** experimentální instance sady Visual Studio.

### <a name="to-build-and-test-the-control"></a>Pro vytváření a testování ovládacího prvku

1. Projekt znovu sestavte a spusťte ladění.

2. V nové instanci sady Visual Studio vytvořte projekt aplikace WPF. Ujistěte se, že je otevřený Návrhář XAML.

3. Najít ovládací prvek ve **nástrojů** a přetáhněte jej na návrhovou plochu.

4. Spusťte ladění aplikace WPF.

5. Ověřte, že se zobrazí váš ovládací prvek.

### <a name="to-deploy-the-control"></a>Nasazení ovládacího prvku

1. Po sestavení testovaného projektu můžete najít *VSIX* soubor * \bin\debug\* složky projektu.

2. Můžete ho nainstalovat na místním počítači dvojitým kliknutím *VSIX* Souborová služba a postupu instalace. Chcete-li odinstalovat ovládací prvek, přejděte na **nástroje** > **rozšíření a aktualizace** a vyhledejte rozšíření pro ovládací prvky a potom klikněte na **odinstalovat**.

3. Nahrát *VSIX* soubor k síti nebo na web.

    Pokud nahrajete soubor, který má [Visual Studio Marketplace](https://marketplace.visualstudio.com/) webové stránky, další uživatelé můžou používat **nástroje** > **rozšíření a aktualizace** v sadě Visual Studio najít ovládací prvek online a nainstalujte ho.
