---
title: Vytvoření stránky Možnosti | Dokumentace Microsoftu
ms.date: 3/16/2019
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], creating
ms.assetid: 9f4e210c-4b47-4daa-91fa-1c301c4587f9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b0b8108470d5f9f14c76e422591a536648b5485e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350991"
---
# <a name="create-an-options-page"></a>Vytvoření stránky Možnosti

Tento návod vytvoří jednoduchou stránku Nástroje/možnosti, které používá mřížky vlastností sloužící ke zkoumání a nastavte vlastnosti.

 K uložení těchto vlastností a obnovení je ze souboru nastavení, postupujte podle těchto kroků a potom se podívejte [vytvoření kategorie nastavení](../extensibility/creating-a-settings-category.md).

 MPF poskytuje dvě třídy, které vám pomohou vytvořit stránky Možnosti nástrojů <xref:Microsoft.VisualStudio.Shell.Package> třídy a <xref:Microsoft.VisualStudio.Shell.DialogPage> třídy. Vytvoření balíčku VSPackage k poskytnutí kontejner pro tyto stránky tak vytváření podtříd `Package` třídy. Vytvoříte odvozením z každé stránky Možnosti nástrojů `DialogPage` třídy.

## <a name="prerequisites"></a>Požadavky

 Spouští se v sadě Visual Studio 2015, nenainstalujete sadu Visual Studio SDK ze služby Stažení softwaru. Je zahrnut jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).

## <a name="create-a-tools-options-grid-page"></a>Vytvoření stránky Možnosti nástrojů mřížky

 V této části vytvoříte jednoduchou mřížky vlastností Možnosti nástrojů. Tato mřížka slouží k zobrazení a změňte hodnotu vlastnosti.

### <a name="to-create-the-vsix-project-and-add-a-vspackage"></a>Vytvořte projekt VSIX a přidat VSPackage

1. Každé rozšíření sady Visual Studio spustí nasazení projektu VSIX, který bude obsahovat rozšíření prostředků. Vytvoření [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSIX projekt s názvem `MyToolsOptionsExtension`. Šablona projektu VSIX v můžete najít **nový projekt** dialogové okno tak, že "vsix".

2. Přidat VSPackage přidáním šablonu položky balíčku Visual Studio s názvem `MyToolsOptionsPackage`. V **Průzkumníka řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat** > **nová položka**. V **dialogového okna Přidat novou položku**, přejděte na stránku **položky Visual C#**  > **rozšiřitelnost** a vyberte **balíček Visual Studio**. V **název** pole v dolní části dialogového okna, změňte název souboru, aby `MyToolsOptionsPackage.cs`. Další informace o tom, jak vytvořit VSPackage najdete v tématu [vytvoření rozšíření pomocí VSPackage](../extensibility/creating-an-extension-with-a-vspackage.md).

### <a name="to-create-the-tools-options-property-grid"></a>Chcete-li vytvořit mřížku vlastností Možnosti nástrojů

1. Otevřít *MyToolsOptionsPackage* souboru v editoru kódu.

2. Přidejte následující příkaz using.

   ```csharp
   using System.ComponentModel;
   ```

3. Deklarovat `OptionPageGrid` třídy a jsou odvozeny z <xref:Microsoft.VisualStudio.Shell.DialogPage>.

   ```csharp
   public class OptionPageGrid : DialogPage
   {  }
   ```

4. Použít <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> k `VSPackage` třídy s možností kategorie a název stránky možnosti pro OptionPageGrid přiřadit do třídy. Výsledek by měl vypadat nějak takto:

    ```csharp
    [PackageRegistration(UseManagedResourcesOnly = true)]
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)]
    [ProvideMenuResource("Menus.ctmenu", 1)]
    [Guid(GuidList.guidMyToolsOptionsPkgString)]
    [ProvideOptionPage(typeof(OptionPageGrid),
        "My Category", "My Grid Page", 0, 0, true)]
    public sealed class MyToolsOptionsPackage : Package
    ```

5. Přidat `OptionInteger` vlastnost `OptionPageGrid` třídy.

    - Použít <xref:System.ComponentModel.CategoryAttribute?displayProperty=fullName> přiřazení k vlastnosti kategorie mřížky vlastností.

    - Použít <xref:System.ComponentModel.DisplayNameAttribute?displayProperty=fullName> přiřadit pro vlastnost název.

    - Použít <xref:System.ComponentModel.DescriptionAttribute?displayProperty=fullName> přiřazení k vlastnosti popis.

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
    > Výchozí implementace <xref:Microsoft.VisualStudio.Shell.DialogPage> podporuje vlastnosti, které mají odpovídající převaděče nebo které jsou struktury nebo polí, která se dá rozšířit do vlastnosti, které mají odpovídající převaděče. Seznam převaděčů najdete v tématu <xref:System.ComponentModel> oboru názvů.

6. Sestavte projekt a spusťte ladění.

7. V experimentální instanci sady Visual Studio na **nástroje** klikněte na nabídku **možnosti**.

     V levém podokně byste měli vidět **kategorie Mé**. (Možnosti kategorie jsou uvedeny v abecedním pořadí, měl by se zobrazit o uprostřed v seznamu dolů.) Otevřít **kategorie Mé** a potom klikněte na tlačítko **stránku mřížky**. Možnosti mřížky se zobrazí v pravém podokně. Vlastnosti kategorie je **Moje možnosti**, a název vlastnosti není **možnost Moje celé číslo**. Popis vlastnosti **možnost Moje celé číslo**, zobrazí se v dolní části podokna. Změňte hodnotu z její počáteční hodnotu 256 na něco jiného. Klikněte na tlačítko **OK**a poté ji znovu otevřete **stránku mřížky**. Uvidíte, že je nová hodnota přetrvává.

     Možnosti stránky je dostupné také prostřednictvím vyhledávacího pole v sadě Visual Studio. Do vyhledávacího pole v horní části rozhraní IDE, zadejte **kategorie Mé** a zobrazí se vám **kategorie Mé -> stránku mřížky** ve výsledcích se objeví.

## <a name="create-a-tools-options-custom-page"></a>Vytvoření vlastní stránky Možnosti nástrojů

 V této části vytvoříte stránky Možnosti nástrojů pomocí vlastního uživatelského rozhraní. Na této stránce můžete zobrazit a změnit hodnotu vlastnosti.

1. Otevřít *MyToolsOptionsPackage* souboru v editoru kódu.

2. Přidejte následující příkaz using.

    ```csharp
    using System.Windows.Forms;
    ```

3. Přidat `OptionPageCustom` třídy těsně před `OptionPageGrid` třídy. Odvodit novou třídu z `DialogPage`.

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

4. Přidáte atribut GUID. Přidáte vlastnost řetězec možností:

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

5. Použít sekundy <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> do třídy balíčku VSPackage. Tento atribut přiřadí třídy s možností kategorie a název stránky možnosti.

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

6. Přidat nový **uživatelský ovládací prvek** s názvem MyUserControl do projektu.

7. Přidat **TextBox** ovládacího prvku do uživatelského ovládacího prvku.

     V **vlastnosti** klikněte na tlačítko na panelu nástrojů okno **události** tlačítko a pak dvakrát klikněte **ponechte** událostí. Novou obslužnou rutinu události se zobrazí v *MyUserControl.cs* kódu.

8. Přidejte veřejnou `OptionsPage` pole, `Initialize` metodu do třídy ovládacího prvku a aktualizujte obslužnou rutinu události možnost nastavit hodnota, která se obsah textového pole:

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

     `optionsPage` Pole obsahuje odkaz na nadřazený `OptionPageCustom` instance. `Initialize` Metoda zobrazí `OptionString` v **TextBox**. Obslužná rutina události zapíše aktuální hodnotu **textového pole** k `OptionString` při zaměření listy **textového pole**.

9. Ve zdrojovém souboru balíčku, přidejte přepsání pro `OptionPageCustom.Window` vlastnost `OptionPageCustom` třídy pro vytváření, inicializace a vrátit instanci `MyUserControl`. Třída by teď měl vypadat takto:

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

11. V experimentální instanci aplikace, klikněte na tlačítko **nástroje** > **možnosti**.

12. Najít **Moje kategorie** a potom **Moje vlastní stránku**.

13. Změňte hodnotu vlastnosti **řetězec možností**. Klikněte na tlačítko **OK**a poté ji znovu otevřete **vlastní stránku**. Uvidíte, že obsahuje trvalé novou hodnotu.

## <a name="access-options"></a>Možnosti přístupu

 V této části se získat hodnotu možnosti ze sady VSPackage, který je hostitelem přidružené stránky Možnosti nástrojů. Stejný postup můžete použít k získání hodnoty všechny veřejné vlastnosti.

1. Ve zdrojovém souboru balíčku, přidejte veřejnou vlastnost s názvem **OptionInteger** k **MyToolsOptionsPackage** třídy.

    ```csharp
    public int OptionInteger
    {
        get
        {
            OptionPageGrid page = (OptionPageGrid)GetDialogPage(typeof(OptionPageGrid));
            return page.OptionInteger;
        }
    }

    ```

     Tento kód volá <xref:Microsoft.VisualStudio.Shell.Package.GetDialogPage%2A> vytvořit nebo načíst `OptionPageGrid` instance. `OptionPageGrid` volání <xref:Microsoft.VisualStudio.Shell.DialogPage.LoadSettingsFromStorage%2A> načíst jeho možnosti, které jsou veřejné vlastnosti.

2. Nyní přidejte vlastní příkaz šablonu položky s názvem **MyToolsOptionsCommand** k zobrazení hodnoty. V **přidat novou položku** dialogové okno, přejděte na **Visual C#**  > **rozšiřitelnost** a vyberte **vlastního příkazu**. V **název** pole v dolní části okna, změňte název souboru příkazu *MyToolsOptionsCommand.cs*.

3. V *MyToolsOptionsCommand* souboru, nahraďte text příkazu `ShowMessageBox` metoda následujícím kódem:

    ```csharp
    private void ShowMessageBox(object sender, EventArgs e)
    {
        MyToolsOptionsPackage myToolsOptionsPackage = this.package as MyToolsOptionsPackage;
        System.Windows.Forms.MessageBox.Show(string.Format(CultureInfo.CurrentCulture, "OptionInteger: {0}", myToolsOptionsPackage.OptionInteger));
    }

    ```

4. Sestavte projekt a spusťte ladění.

5. V experimentální instanci na **nástroje** nabídky, klikněte na tlačítko **vyvolat MyToolsOptionsCommand**.

     Okno se zprávou zobrazí aktuální hodnotu `OptionInteger`.

## <a name="see-also"></a>Viz také:

- [Možnosti a stránky Možnosti](../extensibility/internals/options-and-options-pages.md)
