---
title: 'Postupy: použití průvodců se šablonami projektů | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- project templates [Visual Studio], wizards
- Visual Studio templates, wizards
- wizards [Visual Studio], project templates
- templates [Visual Studio], wizards
- IWizard interface
ms.assetid: 47ee26cf-67b7-4ff1-8a9d-ab11a725405c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d29d2a1313bdb4e8a5e8654068984893578af4a0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-wizards-with-project-templates"></a>Postupy: Použití průvodců se šablonami projektů
Visual Studio poskytuje <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> rozhraní, pokud je implementována, umožňuje spouštět vlastní kód, když uživatel vytvoří projekt ze šablony.  
  
 Přizpůsobení šablony projektu slouží k zobrazení vlastní uživatelské rozhraní, které shromažďuje vstupem uživatele k přizpůsobení šablony, přidejte další soubory do šablony nebo provedení dalších akcí, které jsou povoleny na projektu.  
  
 <xref:Microsoft.VisualStudio.TemplateWizard.IWizard> Metody rozhraní jsou volány v různých časech projektu je při vytváření, spouštění, jakmile uživatel klikne na tlačítko **OK** na **nový projekt** dialogové okno. Každá metoda rozhraní jmenuje k popisu bodu, kdy se nazývá. Například Visual Studio volá <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> okamžitě při spuštění a vytvořte tak projekt, takže je dobré umístění napsat vlastní kód shromažďovat vstup uživatele.  
  
## <a name="creating-a-project-template-project-with-a-vsix-project"></a>Vytvoření projektu šablony projektu s projektem VSIX  
 Spuštění vytvoření vlastní šablony s projektu šablony projektu., která je součástí sady Visual Studio SDK. V tomto postupu budeme používat projekt šablony projektu C#, ale je také projektu šablony projektu Visual Basic. Pak přidat projekt VSIX na řešení, které obsahuje šablony projektu projektu.  
  
1.  Vytvoření projektu šablony projektu C# (v sadě Visual Studio, **soubor > Nový > Projekt > Visual C# > Rozšíření > Šablona projektu C#**). Pojmenujte ji **MyProjectTemplate**.  
  
    > [!NOTE]
    >  Můžete být vyzváni k instalaci sady Visual Studio SDK. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
2.  Přidat nový projekt VSIX (**soubor > Nový > Projekt > Visual C# > Rozšíření > Projekt VSIX**) ve stejném řešení jako projekt šablony projektu (v **Průzkumníku řešení**, vyberte uzel řešení, klikněte pravým tlačítkem a vyberte **Přidat > Nový projekt**). Pojmenujte ji **MyProjectWizard.**  
  
3.  Nastavte VSIX projekt jako spouštěný projekt. V **Průzkumníku řešení**, vyberte uzel projektu VSIX, klikněte pravým tlačítkem a vyberte **nastavit jako spouštěný projekt**.  
  
4.  Šablony projektu přidejte jako prostředek VSIX projektu. V **Průzkumníku řešení**, pod uzlem projektu VSIX najít **source.extension.vsixmanifest** souboru. Dvojím kliknutím ho otevřete v editoru manifestu.  
  
5.  V manifestu editor, vyberte **prostředky** karty na levé straně okna.  
  
6.  V **prostředky** vyberte **nový**. V **přidat nový prostředek** okno, v poli typu vyberte **Microsoft.VisualStudio.ProjectTemplate**. V **zdroj** pole, vyberte **na projekt v aktuálním řešení**. V **projektu** pole, vyberte **MyProjectTemplate**. Pak klikněte na tlačítko **OK**.  
  
7.  Sestavte řešení a spuštění ladění. Zobrazí se druhé instance Visual Studio. (To může trvat několik minut.)  
  
8.  V druhé instanci sady Visual Studio pokuste se vytvořit nový projekt s novou šablonu. (**Soubor > Nový > Projekt > Visual C# > MyProject šablony**). Nový projekt by se třídy s názvem **Class1**. Nyní jste vytvořili vlastní šablonu projektu! Zastavte ladění nyní.  
  
## <a name="creating-a-custom-template-wizard"></a>Vytvoření vlastního průvodce šablony  
 Toto téma ukazuje postup vytvoření vlastního průvodce, který otevře formuláře Windows před vytvořením projektu. Formulář umožňuje uživatelům přidat parametr vlastní hodnotu, která se přidá do zdrojového kódu během vytváření projektu.  
  
1.  Nastavení projektu VSIX tak, aby ji vytvořit sestavení.  
  
2.  V **Průzkumníku**, vyberte uzel projektu VSIX. Níže Průzkumníku řešení, měli byste vidět **vlastnosti** okno. Pokud ho použít nechcete, vyberte **zobrazení > Vlastnosti – okno**, nebo stiskněte klávesu **F4**. V okně Vlastnosti, vyberte následující pole do `true`:  
  
    -   **IncludeAssemblyInVSIXContainer**  
  
    -   **IncludeDebugSymbolsInVSIXContainer**  
  
    -   **IncludeDebugSymbolsInLocalVSIXDeployment**  
  
3.  Přidejte sestavení jako prostředek do projektu VSIX. Otevřete soubor source.extension.vsixmanifest a vyberte **prostředky** kartě. V **přidat nový prostředek** okně pro **typ** vyberte **Microsoft.VisualStudio.Assembly**, pro **zdroj** vyberte **A projekt v aktuálním řešení**a pro **projektu** vyberte **MyProjectWizard**.  
  
4.  Přidejte následující odkazy na projekt VSIX. (V **Průzkumníku řešení**, v části VSIX projektu vyberte uzel **odkazy**, klikněte pravým tlačítkem a vyberte **přidat odkaz na**.) V **přidat odkaz na** dialogové okno, v **Framework** kartě, vyhledejte **System.Windows Forms** sestavení a vyberte ho. Nyní vybrat **rozšíření** kartě Najít **EnvDTE** sestavení a vyberte ho. Také umožňuje vyhledat **Microsoft.VisualStudio.TemplateWizardInterface** sestavení a vyberte ho. Click **OK**.  
  
5.  Do projektu VSIX přidejte třídu pro implementaci průvodce. (V Průzkumníku řešení klikněte pravým tlačítkem na uzel projektu VSIX a vyberte **přidat**, pak **nová položka**, pak **třída**.) Název třídy **WizardImplementation**.  
  
6.  Nahraďte kód v **WizardImplementationClass.cs** soubor s následujícím kódem:  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using Microsoft.VisualStudio.TemplateWizard;  
    using System.Windows.Forms;  
    using EnvDTE;  
  
    namespace MyProjectWizard  
    {  
        public class WizardImplementation:IWizard  
        {  
            private UserInputForm inputForm;  
            private string customMessage;  
  
            // This method is called before opening any item that   
            // has the OpenInEditor attribute.  
            public void BeforeOpeningFile(ProjectItem projectItem)  
            {  
            }  
  
            public void ProjectFinishedGenerating(Project project)  
            {  
            }  
  
            // This method is only called for item templates,  
            // not for project templates.  
            public void ProjectItemFinishedGenerating(ProjectItem   
                projectItem)  
            {  
            }  
  
            // This method is called after the project is created.  
            public void RunFinished()  
            {  
            }  
  
            public void RunStarted(object automationObject,  
                Dictionary<string, string> replacementsDictionary,  
                WizardRunKind runKind, object[] customParams)  
            {  
                try  
                {  
                    // Display a form to the user. The form collects   
                    // input for the custom message.  
                    inputForm = new UserInputForm();  
                    inputForm.ShowDialog();  
  
                    customMessage = UserInputForm.CustomMessage;  
  
                    // Add custom parameters.  
                    replacementsDictionary.Add("$custommessage$",   
                        customMessage);  
                }  
                catch (Exception ex)  
                {  
                    MessageBox.Show(ex.ToString());  
                }  
            }  
  
            // This method is only called for item templates,  
            // not for project templates.  
            public bool ShouldAddProjectItem(string filePath)  
            {  
                return true;  
            }          
        }  
    }  
    ```  
  
     **UserInputForm** odkazuje v tomto kódu se provede později.  
  
     `WizardImplementation` Třída obsahuje implementace metody pro každého člena <xref:Microsoft.VisualStudio.TemplateWizard.IWizard>. V tomto příkladu pouze <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> metoda provede úlohu. Všechny ostatní metody nedělat nic nebo vrátí `true`.  
  
     <xref:Microsoft.VisualStudio.TemplateWizard.IWizard.RunStarted%2A> Metoda přijímá čtyř parametrů:  
  
    -   <xref:System.Object> Parametr, který může být převeden do kořenového adresáře <xref:EnvDTE._DTE> objekt, které vám umožňují přizpůsobit projektu.  
  
    -   A <xref:System.Collections.Generic.Dictionary%602> parametr, který obsahuje kolekci všech předem definovaných parametrů v šabloně. Další informace o parametry šablony najdete v tématu [parametry šablony](../ide/template-parameters.md).  
  
    -   A <xref:Microsoft.VisualStudio.TemplateWizard.WizardRunKind> parametr, který obsahuje informace o jaký typ šablony je používán.  
  
    -   <xref:System.Object> Pole, které obsahuje sadu parametrů předaných průvodci Visual Studio.  
  
     Tento příklad přidá hodnotu parametru ze vstupní formuláře uživatele <xref:System.Collections.Generic.Dictionary%602> parametr. Všechny instance řetězce `$custommessage$` parametr v projektu se nahradí text zadaný uživatelem. Je nutné přidat následující sestavení do projektu: **systému** a **System.Drawing**.
  
7.  Nyní vytvoří **UserInputForm**. V **WizardImplementation.cs** soubor, přidejte následující kód na konci **WizardImplementation** třídy.  
  
    ```csharp  
    public partial class UserInputForm : Form  
        {  
            private static string customMessage;  
            private TextBox textBox1;  
            private Button button1;  
  
            public UserInputForm()  
            {  
                this.Size = new System.Drawing.Size(155, 265);   
  
                button1 = new Button();  
                button1.Location = new System.Drawing.Point(90, 25);  
                button1.Size = new System.Drawing.Size(50, 25);  
                button1.Click += button1_Click;  
                this.Controls.Add(button1);  
  
                textBox1 = new TextBox();  
                textBox1.Location = new System.Drawing.Point(10, 25);  
                textBox1.Size = new System.Drawing.Size(70, 20);  
                this.Controls.Add(textBox1);  
            }  
            public static string CustomMessage  
            {  
                get  
                {  
                    return customMessage;  
                }  
                set  
                {  
                    customMessage = value;  
                }     
            }  
            private void button1_Click(object sender, EventArgs e)  
            {  
                customMessage = textBox1.Text;  
                this.Close();
            }  
        }  
    ```  
  
     Formulář vstupu uživatele poskytuje jednoduchý formulář pro zadávání vlastního parametru. Tento formulář obsahuje textové pole s názvem `textBox1` a tlačítko s názvem `button1`. Při kliknutí na tlačítko text z textového pole je uložen v `customMessage` parametr.  
  
## <a name="connect-the-wizard-to-the-custom-template"></a>Připojit k šabloně vlastní Průvodce  
 Aby vaše vlastní projektu šablonu použít vlastní průvodce musíte k podepisování sestavení průvodce a přidejte některé řádky do šablony vlastních projektů uvědomit, kde najít implementace Průvodce při vytváření nového projektu.  
  
1.  Podepisování sestavení. V **Průzkumníku řešení**, vyberte VSIX projektu, klikněte pravým tlačítkem a vyberte **vlastnosti projektu**.  
  
2.  V **vlastnosti projektu** vyberte **podpisování** kartě v **podpisování** zkontrolujte **podepsání sestavení**. V **vyberte soubor klíče se silným názvem** pole, vyberte  **\<nový >**. V **vytvořit klíč se silným názvem** okno v **název souboru klíče** zadejte **key.snk**. Zrušte zaškrtnutí políčka **chránit Moje soubor klíče s heslem** pole.  
  
3.  V **Průzkumníku řešení**, vyberte projekt VSIX a vyhledávat **vlastnosti** okno.  
  
4.  Nastavte **výstup do výstupního adresáře sestavení kopie** do **true**. To umožňuje sestavení, které má být zkopírován do výstupního adresáře. Pokud je znovu sestavit řešení. Stále je obsažena v souboru VSIX. Potřebujete, aby bylo možné zjistit jeho podpisový klíč najdete v části sestavení.  
  
5.  Znovu sestavte řešení.  
  
6.  Teď můžete získat key.snk soubor v adresáři projektu MyProjectWizard (**\<vaše umístění disku > \MyProjectTemplate\MyProjectWizard\key.snk**). Zkopírujte soubor key.snk.  
  
7.  Přejděte do výstupního adresáře a najděte sestavení (**\<vaše umístění disku > \MyProjectTemplate/MyProjectWizard\bin\Debug\MyProjectWizard.dll**). Vložte soubor key.snk. (To není nezbytně nutné, ale jeho vám usnadní následující kroky.)  
  
8.  Otevřete okno příkazového řádku a přejděte do adresáře, ve kterém byla vytvořena sestavení.  
  
9. Najít **sn.exe** podepisování nástroj. Například na Windows 10 64bitový operační systém, typické cesta by být následující:  
  
     **C:\Program soubory (x86) \Microsoft SDKs\Windows\v10.0A\bin\NETFX 4.6.1 nástroje**  
  
     Pokud nemůžete najít nástroj, zkuste spustit **kde /R.  sn.exe** v příkazovém okně. Poznamenejte si cestu.  
  
10. Extrahujte veřejný klíč ze souboru key.snk. V okně příkazového řádku zadejte  
  
     **\<umístění sn.exe > \sn.exe -p key.snk outfile.key.**  
  
     Nezapomeňte obklopit cestu sn.exe v uvozovkách, pokud nejsou mezery v názvech adresářů!  
  
11. Získání tokenu veřejného klíče z Výstupní_soubor:  
  
     **\<umístění sn.exe > -t outfile.key \sn.exe.**  
  
     Nezapomeňte znovu, musí si uvozovky. Měli byste vidět řádek ve výstupu takto  
  
     **Token veřejného klíče má <token>**  
  
     Poznamenejte si tuto hodnotu.  
  
12. Přidáte odkaz na vlastní průvodce k souboru .vstemplate šablony projektu. V Průzkumníku řešení najít soubor s názvem MyProjectTemplate.vstemplate a otevřete jej. Po skončení \<TemplateContent > přidejte následující části:  
  
    ```xml  
    <WizardExtension>  
        <Assembly>MyProjectWizard, Version=1.0.0.0, Culture=Neutral, PublicKeyToken=token</Assembly>  
        <FullClassName>MyProjectWizard.WizardImplementation</FullClassName>  
    </WizardExtension>  
    ```  
  
     Kde **MyProjectWizard** je název sestavení, a **tokenu** je token, který jste zkopírovali v předchozím kroku.  
  
13. Uložte všechny soubory v projektu a sestavte znovu.  
  
## <a name="adding-the-custom-parameter-to-the-template"></a>Přidání parametr vlastní šablony  
 V tomto příkladu projekt použít jako šablonu zobrazí zprávu určenou ve formuláři vstupu uživatele vlastního průvodce.  
  
1.  V Průzkumníku řešení, přejděte na **MyProjectTemplate** projektu a otevřete **Class1.cs**.  
  
2.  V `Main` metoda aplikace, přidejte následující řádek kódu.  
  
    ```  
    Console.WriteLine("$custommessage$");  
    ```  
  
     Parametr `$custommessage$` se nahradí zadaný text ve formuláři vstupu uživatele při vytvoření projektu ze šablony.  
  
 Zde je soubor úplného kódu, než byl exportován do šablony.  
  
```csharp  
using System;  
using System.Collections.Generic;  
$if$ ($targetframeworkversion$ >= 3.5)using System.Linq;  
$endif$using System.Text;  
  
namespace $safeprojectname$  
{  
    public class Class1  
    {  
          static void Main(string[] args)  
          {  
               Console.WriteLine("$custommessage$");  
          }  
    }  
}  
```  
  
## <a name="using-the-custom-wizard"></a>Pomocí vlastní Průvodce  
 Nyní můžete vytvořit projekt z šablony a používat vlastní průvodce.  
  
1.  Znovu sestavte řešení a spusťte ladění. Druhou instanci sady Visual Studio by se zobrazit.  
  
2.  Vytvoření nového projektu MyProjectTemplate. (**Soubor > Nový > Projekt > Visual C# > MyProjectTemplate**)  
  
3.  V **nový projekt** dialogové okno, vyhledejte šablony, zadejte název a klikněte na tlačítko **OK**.  
  
     Otevře se Průvodce formulář vstupu uživatele.  
  
4.  Zadejte hodnotu pro parametr vlastní a klikněte na tlačítko.  
  
     Zavře formulář průvodce vstupu uživatele a projekt je vytvořený z šablony.  
  
5.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na soubor zdrojového kódu a klikněte na **kód zobrazení**.  
  
     Všimněte si, že `$custommessage$` byl nahrazen textem zadaným ve formuláři průvodce vstupu uživatele.  
  
## <a name="see-also"></a>Viz také  

<xref:Microsoft.VisualStudio.TemplateWizard.IWizard>   
[Přizpůsobení šablon](../ide/customizing-project-and-item-templates.md)  
[WizardExtension – element (šablony sady Visual Studio)](../extensibility/wizardextension-element-visual-studio-templates.md)  
[Balíčky NuGet ve šablony sady Visual Studio](/nuget/visual-studio-extensibility/visual-studio-templates)
