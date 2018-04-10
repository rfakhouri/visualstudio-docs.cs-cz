---
title: Vytvoření stránky Možnosti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], creating
ms.assetid: 9f4e210c-4b47-4daa-91fa-1c301c4587f9
caps.latest.revision: 62
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d0888a584e31c26c9f64cdcff70cc2f5dc8a1453
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="creating-an-options-page"></a>Vytvoření stránky Možnosti
Tento návod vytvoří jednoduchý nástroje/Možnosti stránky, která používá mřížkou vlastností sloužící ke zkoumání a nastavte vlastnosti.  
  
 Pokud chcete uložit tyto vlastnosti k a obnovit je z nastavení souboru, postupujte podle těchto kroků a zjistěte, [vytváření kategorie nastavení](../extensibility/creating-a-settings-category.md).  
  
 Sady MPF poskytuje dvě třídy, které vám pomůžou vytvořit stránek možnosti nástrojů <xref:Microsoft.VisualStudio.Shell.Package> – třída a <xref:Microsoft.VisualStudio.Shell.DialogPage> třídy. Můžete vytvořit VSPackage k vytvoření podtřídy třída balíčku zadejte kontejner pro tyto stránek. Při odvozování od třídy DialogPage vytváření každé stránce Možnosti nástroje.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-tools-options-grid-page"></a>Vytvoření stránky mřížky možnosti nástroje  
 V této části vytvoříte jednoduchý mřížkou vlastností Možnosti nástrojů. Pomocí této mřížky zobrazte a změňte hodnotu vlastnosti.  
  
#### <a name="to-create-the-vsix-project-and-add-a-vspackage"></a>Vytvoření projektu VSIX a přidání VSPackage  
  
1.  Každé rozšíření sady Visual Studio začíná projekt nasazení VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projektu s názvem `MyToolsOptionsExtension`. Můžete najít v šabloně projektů VSIX **nový projekt** dialogové okno pod **Visual C# nebo rozšíření**.  
  
2.  Přidat VSPackage přidáním šablonu položky balíček Visual Studio s názvem `MyToolsOptionsPackage`. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. V **dialogové okno Přidat novou položku**, přejděte na **Visual C# položky nebo rozšíření** a vyberte **balíček Visual Studio**. V **název** pole v dolní části dialogového okna, změňte název souboru `MyToolsOptionsPackage.cs`. Další informace o tom, jak vytvořit VSPackage najdete v tématu [vytváření rozšíření s VSPackage](../extensibility/creating-an-extension-with-a-vspackage.md).  
  
#### <a name="to-create-the-tools-options-property-grid"></a>Chcete-li vytvořit mřížku vlastností Možnosti nástrojů  
  
1.  Otevřete soubor MyToolsOptionsPackage v editoru kódu.  
  
2.  Přidejte následující příkaz using.  
  
    ```csharp  
    using System.ComponentModel;  
    ```  
  
3.  Deklarovat třídu OptionPageGrid a odvodí z <xref:Microsoft.VisualStudio.Shell.DialogPage>.  
  
    ```csharp  
    public class OptionPageGrid : DialogPage  
    {  }  
    ```  
  
4.  Použít <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> k třídě VSPackage přiřadit k třídě služby možnosti kategorie a název stránky možnosti pro OptionPageGrid. Výsledek by měl vypadat takto:  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [Guid(GuidList.guidMyToolsOptionsPkgString)]  
    [ProvideOptionPage(typeof(OptionPageGrid),  
        "My Category", "My Grid Page", 0, 0, true)]  
    public sealed class MyToolsOptionsPackage : Package  
    ```  
  
5.  Přidat `OptionInteger` vlastnost, která má `OptionPageGrid` třídy.  
  
    -   Použít <xref:System.ComponentModel.CategoryAttribute?displayProperty=fullName> přiřadit k vlastnosti kategorie vlastnost mřížky.  
  
    -   Použít <xref:System.ComponentModel.DisplayNameAttribute?displayProperty=fullName> přiřadit pro vlastnost název.  
  
    -   Použít <xref:System.ComponentModel.DescriptionAttribute?displayProperty=fullName> přiřadit k vlastnosti popis.  
  
    ```csharp  
    public class OptionPageGrid : DialogPage  
    {  
        private int optionInt = 256;  
  
        [Category("My Category")]  
        [DisplayName("My Integer Option")]  
        [Description("My integer option")]  
        public int OptionInteger  
        {  
            get { return optionInt; }  
            set { optionInt = value; }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  Výchozí implementaci <xref:Microsoft.VisualStudio.Shell.DialogPage> podporuje vlastnosti, které mají odpovídající převaděče nebo které jsou struktury nebo pole, které lze rozšířit do vlastností, které mají odpovídající převaděče. Seznam převaděčů najdete v tématu <xref:System.ComponentModel> oboru názvů.  
  
6.  Sestavte projekt a spusťte ladění.  
  
7.  V experimentální instanci sady Visual Studio na **nástroje** nabídce klikněte na tlačítko **možnosti**.  
  
     V levém podokně byste měli vidět **Moje kategorie**. (Možnosti kategorie jsou uvedeny v abecedním pořadí, mělo by se zobrazit o polovině vzdálenosti směrem dolů seznamem.) Otevřete **Moje kategorie** a pak klikněte na **stránku mřížky**. V pravém podokně se zobrazí možnosti mřížky. Kategorie vlastnost **Moje možnosti**, a název vlastnosti je **Moje možnost celé číslo**. Popis vlastnost **Moje možnost celé číslo**, zobrazí se v dolní části podokna. Změňte hodnotu z její počáteční hodnoty 256 na něco jiného. Klikněte na tlačítko **OK**a poté znovu otevřete **stránku mřížky**. Uvidíte, že nová hodnota přetrvává.  
  
     Stránka možnosti je také k dispozici prostřednictvím Snadné spuštění sady Visual Studio. Zadejte v okně Snadné spuštění v pravém horním rohu okna IDE **Moje kategorie** a zobrazí se vám **Moje kategorie -> – Moje stránky mřížky** uvedené v rozevírací nabídce.  
  
## <a name="creating-a-tools-options-custom-page"></a>Vytváření vlastní možnosti nástroje stránky  
 V této části vytvoříte stránky Možnosti nástrojů s vlastní uživatelské rozhraní. Na této stránce zobrazte a změňte hodnotu vlastnosti.  
  
1.  Otevřete soubor MyToolsOptionsPackage v editoru kódu.  
  
2.  Přidejte následující příkaz using.  
  
    ```vb  
    using System.Windows.Forms;  
    ```  
  
3.  Přidat `OptionPageCustom` třídy těsně před `OptionPageGrid` třídy. Odvození novou třídu z `DialogPage`.  
  
    ```csharp  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
    }  
    ```  
  
4.  Přidáte atribut GUID. Přidáte vlastnost řetězec možností:  
  
    ```csharp  
    [Guid("00000000-0000-0000-0000-000000000000")]  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
    }  
    ```  
  
5.  Použít druhý <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> k třídě VSPackage. Tento atribut přiřadí třída služby možnosti kategorie a název stránky možnosti.  
  
    ```csharp  
    [PackageRegistration(UseManagedResourcesOnly = true)]  
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    [Guid(GuidList.guidMyToolsOptionsPkgString)]  
    [ProvideOptionPage(typeof(OptionPageGrid),  
        "My Category", "My Grid Page", 0, 0, true)]  
    [ProvideOptionPage(typeof(OptionPageCustom),  
        "My Category", "My Custom Page", 0, 0, true)]  
    public sealed class MyToolsOptionsPackage : Package  
    ```  
  
6.  Přidejte nový **uživatelský ovládací prvek** s názvem MyUserControl do projektu.  
  
7.  Přidat **TextBox** ovládacího prvku do uživatelského ovládacího prvku.  
  
     V **vlastnosti** okně na panelu nástrojů klikněte na tlačítko **události** tlačítko a potom dvakrát klikněte na **nechte** událostí. Novou obslužnou rutinu události se zobrazí v MyUserControl.cs kódu.  
  
8.  Přidat veřejné `OptionsPage` pole, `Initialize` metoda třída ovládacích prvků a aktualizace obslužné rutiny události možnost nastavit hodnotu obsahu textového pole:  
  
    ```csharp  
    public partial class MyUserControl : UserControl  
    {  
        public MyUserControl()  
        {  
            InitializeComponent();  
        }  
  
        internal OptionPageCustom optionsPage;  
  
        public void Initialize()  
        {  
            textBox1.Text = optionsPage.OptionString;  
        }  
  
        private void textBox1_Leave(object sender, EventArgs e)  
        {  
            optionsPage.OptionString = textBox1.Text;  
        }  
    }  
    ```  
  
     `optionsPage` Pole obsahuje odkaz na nadřazený `OptionPageCustom` instance. `Initialize` Metoda zobrazí `OptionString` v **TextBox**. Obslužné rutiny události zapíše aktuální hodnota **TextBox** k `OptionString` při zaměření nechá **textové pole**.  
  
9. V souboru kódu balíčku, přidejte přepsání pro `OptionPageCustom.Window` vlastnost k třídě OptionPageCustom k vytváření, inicializace a vrátit instanci třídy `MyUserControl`. Třída by měl nyní vypadat takto:  
  
    ```csharp  
    [Guid("00000000-0000-0000-0000-000000000000")]  
    public class OptionPageCustom : DialogPage  
    {  
        private string optionValue = "alpha";  
  
        public string OptionString  
        {  
            get { return optionValue; }  
            set { optionValue = value; }  
        }  
  
        protected override IWin32Window Window  
        {  
            get  
            {  
                MyUserControl page = new MyUserControl();  
                page.optionsPage = this;  
                page.Initialize();  
                return page;  
            }  
        }  
    }  
    ```  
  
10. Sestavte a spusťte projekt.  
  
11. V experimentální instance, klikněte na **Nástroje / možnosti**.  
  
12. Najít **Moje kategorie** a potom **Mé vlastní stránky**.  
  
13. Změňte hodnotu **řetězec možností**. Klikněte na tlačítko **OK**a poté znovu otevřete **Moje vlastní stránku**. Uvidíte, že nová hodnota má nastavené jako trvalé.  
  
## <a name="accessing-options"></a>Přístup k možnosti  
 V této části se získat hodnotu možnost z VSPackage, který je hostitelem přidružené stránka Možnosti nástrojů. Stejný postup lze použít k získání hodnoty všechny veřejné vlastnosti.  
  
1.  V souboru kódu balíčku, přidejte veřejnou vlastnost s názvem **OptionInteger** k **MyToolsOptionsPackage** třídy.  
  
    ```  
    public int OptionInteger  
    {  
        get  
        {  
            OptionPageGrid page = (OptionPageGrid)GetDialogPage(typeof(OptionPageGrid));  
            return page.OptionInteger;  
        }  
    }  
  
    ```  
  
     Tento kód zavolá <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> vytvořit nebo načíst `OptionPageGrid` instance. `OptionPageGrid` volání <xref:Microsoft.VisualStudio.Shell.DialogPage.LoadSettingsFromStorage%2A> načíst její možnosti, které jsou veřejné vlastnosti.  
  
2.  Nyní přidejte šablonu a vlastní příkaz položka s názvem **MyToolsOptionsCommand** zobrazení hodnoty. V **přidat novou položku** dialogové okno, přejděte na **Visual C# nebo rozšíření** a vyberte **vlastní příkaz**. V **název** pole v dolní části okna, změňte název souboru příkaz **MyToolsOptionsCommand.cs**.  
  
3.  V souboru MyToolsOptionsCommand, nahraďte text příkazu `ShowMessageBox` metoda následujícím kódem:  
  
    ```csharp  
    private void ShowMessageBox(object sender, EventArgs e)  
    {  
        MyToolsOptionsPackage myToolsOptionsPackage = this.package as MyToolsOptionsPackage;  
        System.Windows.Forms.MessageBox.Show(string.Format(CultureInfo.CurrentCulture, "OptionInteger: {0}", myToolsOptionsPackage.OptionInteger));  
    }  
  
    ```  
  
4.  Sestavte projekt a spusťte ladění.  
  
5.  V experimentální instanci na **nástroje** nabídky, klikněte na tlačítko **vyvolání MyToolsOptionsCommand**.  
  
     Okno se zprávou zobrazí aktuální hodnota `OptionInteger`.  
  
## <a name="see-also"></a>Viz také  
 [Možnosti a stránky Možnosti](../extensibility/internals/options-and-options-pages.md)