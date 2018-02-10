---
title: "Vytvoření ovládacího prvku sady nástrojů WPF | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbox control
- toolbox
- wpf
ms.assetid: 9cc34db9-b0d1-4951-a02f-7537fbbb51ad
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c1a8338f0ebd964e5d039ffa8dff000a441523f8
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="creating-a-wpf-toolbox-control"></a>Vytvoření ovládacího prvku sady nástrojů WPF
Ovládací prvek sady nástrojů WPF (Windows Presentation Framework) šablona umožňuje vytvořit ovládacích prvků WPF, které jsou automaticky přidány do **sada nástrojů** při instalaci rozšíření. Toto téma ukazuje, jak vytvořit pomocí šablony **sada nástrojů** ovládací prvek, který distribuujete do jiných uživatelů.  
  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-wpf-toolbox-control"></a>Vytvoření ovládacího prvku sady nástrojů WPF  
  
#### <a name="create-an-extension-with-a-wpf-toolbox-control"></a>Vytváření rozšíření s ovládacím prvkem sady nástrojů WPF  
  
1.  Vytvoření projektu VSIX s názvem `MyToolboxControl`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Když se otevře projekt, přidejte **ovládací prvek sady nástrojů WPF** šablony položky s názvem `MyToolboxControl`. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **ovládací prvek sady nástrojů WPF**. V **název** pole v dolní části okna, změňte název souboru příkaz `MyToolboxControl.cs`.  
  
     Řešení nyní obsahuje uživatelského ovládacího prvku `ProvideToolboxControlAttribute` <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute> , přidá do ovládacího prvku **sada nástrojů**a **Microsoft.VisualStudio.ToolboxControl** Asset položku v manifestu VSIX pro  nasazení.  
  
#### <a name="to-create-the-control-ui"></a>Vytvoření ovládacího prvku uživatelského rozhraní  
  
1.  Otevřete MyToolboxControl.xaml v návrháři.  
  
     Návrhář ukazuje <xref:System.Windows.Controls.Grid> ovládací prvek, který obsahuje <xref:System.Windows.Controls.Button> ovládacího prvku.  
  
2.  Umožňuje uspořádejte rozložení mřížky. Když vyberete <xref:System.Windows.Controls.Grid> řídit, modré ovládací pruhy zobrazí v horní a levé hrany mřížky. Kliknutím řádky, můžete přidat řádků a sloupců do mřížky.  
  
3.  Přidáte podřízené ovládací prvky mřížky. Přetažením z můžete umístit podřízený ovládací prvek **sada nástrojů** na část mřížky, nebo nastavením jeho `Grid.Row` a `Grid.Column` atributů v XAML. Následující příklad přidá dva popisky na začátek řádku mřížky a tlačítko na druhém řádku.  
  
    ```xaml  
    <Grid>  
        <Label Grid.Row="0" Grid.Column="0" Name="label1" />  
        <Label Grid.Row="0" Grid.Column="1" Name="label2" />  
        <Button Name="button1" Click="button1_Click" Grid.Row="1" Grid.ColumnSpan="2" />  
    </Grid>  
    ```  
  
## <a name="renaming-the-control"></a>Přejmenování ovládacího prvku  
 Ve výchozím nastavení, zobrazí se vlastní ovládací prvek v **sada nástrojů** jako **MyToolboxControl** ve skupině s názvem **MyToolboxControl.MyToolboxControl**. Tyto názvy v souboru MyToolboxControl.xaml.cs, můžete změnit.  
  
1.  Otevřete MyToolboxControl.xaml.cs v zobrazení kódu.  
  
2.  Nalezena třída MyToolboxControl a přejmenujte jej na TestControl. (Nejrychlejší způsob, jak to udělat, je k přejmenování třídy, vyberte **přejmenovat** v místní nabídce a proveďte kroky. (Další informace o **přejmenovat** příkazů najdete v tématu [přejmenovat refaktoring (C#)](../ide/reference/rename.md).)
  
3.  Přejděte na `ProvideToolboxControl` atribut a změňte hodnotu první parametr **Test**. Toto je název skupiny, která bude obsahovat ovládacího prvku **sada nástrojů**.  
  
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
  
## <a name="building-testing-and-deployment"></a>Vytváření, testování a nasazení  
 Při ladění projektu, byste měli najít ovládací prvek nainstalovaný v **sada nástrojů** experimentální instance sady Visual Studio.  
  
#### <a name="to-build-and-test-the-control"></a>Pro sestavení a otestování ovládacího prvku  
  
1.  Projekt znovu sestavte a spusťte ladění.  
  
2.  V nové instanci sady Visual Studio vytvořte projekt aplikace WPF. Ujistěte se, že návrháře XAML je otevřený.  
  
3.  Najít váš ovládacího prvku **sada nástrojů** a přetáhněte ji na plochu návrháře.  
  
4.  Spusťte ladění aplikace WPF.  
  
5.  Ověřte, že zobrazuje vlastního ovládacího prvku.  
  
#### <a name="to-deploy-the-control"></a>K nasazení ovládacího prvku  
  
1.  Po sestavení otestované projektu naleznete ve složce \bin\debug\ projektu soubor VSIX.  
  
2.  Můžete jej nainstalovat na místním počítači tak, že dvojitým kliknutím na soubor VSIX a následující postup instalace. Chcete-li odinstalovat ovládacího prvku, přejděte na **nástroje nebo rozšíření a aktualizace** a vyhledejte rozšíření pro ovládací prvky a pak klikněte na **odinstalovat**.  
  
3.  Nahrajte soubor VSIX k síti nebo na webu.  
  
     Pokud nahrát soubor [Galerie sady Visual Studio](http://go.microsoft.com/fwlink/?LinkID=123847) web, můžete používat ostatní uživatelé **nástroje nebo rozšíření a aktualizace** v sadě Visual Studio najít ovládací prvek online a nainstalujte ji.