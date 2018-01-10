---
title: "Testování pomocí programových testů uživatelského rozhraní Windows aplikace UWP | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: uwp
author: gewarren
ms.openlocfilehash: 7bbb703d753770444bb9f3641778d0b1a62fc374
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="test-windows-uwp-apps-with-coded-ui-tests"></a>Testování pomocí programových testů uživatelského rozhraní Windows aplikace UWP

Pomocí tohoto průvodce použijte pro vytvoření testů uživatelského rozhraní pro aplikace UWP a založených na XAML 8.1 aplikace. 
  
## <a name="create-a-simple-uwp-app"></a>Vytvoření jednoduché aplikace UWP  
  
1.  Pokud chcete spustit programové testy uživatelského rozhraní pro aplikace UWP založených na XAML, musíte [nastavení jedinečné vlastnosti automatizace identifikující každý ovládací prvek](../test/set-a-unique-automation-property-for-windows-store-controls-for-testing.md).  
  
     Na **nástroje** nabídky, přejděte na příkaz **možnosti** a potom zvolte **textového editoru**, pak **XAML**a v neposlední řadě **různé** .  
  
     Zaškrtněte políčko automaticky název interaktivní elementů při vytváření.  
  
     ![XAML různé možnosti](../test/media/cuit_windowsstoreapp_b.png "CUIT_WindowsStoreApp_B")  
  
2.  Vytvoření nového projektu pro prázdný XAML na základě aplikace pro UPW pomocí šablony buď Visual C# nebo Visual Basic.  
  
     ![Vytvoření aplikace pro práci s &#40; XAML &#41; ] (../test/media/cuit_windowsstoreapp_newproject_blankstoreapp.png "CUIT_WindowsStoreApp_NewProject_BlankStoreApp")  
  
3.  V Průzkumníku řešení otevřete MainPage.xaml. Z panelu nástrojů přetáhněte ovládací prvek tlačítko a ovládacího prvku textového pole na plochu návrháře.  
  
     ![Návrh aplikace pro UPW](../test/media/cuit_windowsstoreapp_design.png "CUIT_WindowsStoreApp_Design")  
  
4.  Dvakrát klikněte tlačítko – ovládací prvek a přidejte následující kód:  
  
    ```csharp  
    private void button_Click_1(object sender, RoutedEventArgs e)  
    {  
        this.textBox.Text = this.button.Name;  
    }  
  
    ```  
  
    ```vb  
    Public NotInheritable Class MainPage  
        Inherits Page  
  
        Private Sub button_Click(sender As Object, e As RoutedEventArgs) Handles Button.Click  
            Me.textBox.Text = Me.button.Name  
        End Sub  
    End Class  
    ```  
  
5.  Stisknutím klávesy F5 spusťte svoji aplikaci pro UPW.  
  
## <a name="create-and-run-a-coded-ui-test-for-the-uwp-app"></a>Vytvoření a spuštění programového testu uživatelského rozhraní pro aplikace UWP  

[Vytvoření programové testy uživatelského rozhraní pro aplikace pro univerzální platformu Windows (UWP)](#uwpapps)
  
1.  Vytvořte nový projekt testu pro programové uživatelského rozhraní pro aplikace pro UPW.  
  
     ![Nový projekt programové uživatelského rozhraní tét &#40; Aplikace UWP &#41; ] (../test/media/cuit_windowsstore_newproject.png "CUIT_WindowsStore_NewProject")  
  
2.  Zvolte úpravu mapování uživatelského rozhraní pomocí nástroje kříž.  
  
     ![Zvolte Upravit mapovat uživatelského rozhraní nebo přidat kontrolní výrazy](../test/media/cuit_windowsstoreapp_createproject_gencodedialog.png "CUIT_WindowsStoreApp_CreateProject_GenCodeDialog")  
  
3.  Pomocí nástroje kříž v Tvůrce programového testu uživatelského rozhraní vyberte dlaždici aplikace, klikněte pravým tlačítkem na **AutomationId** a zvolte **hodnotu kopírování do schránky**. Hodnota ve schránce se použije později pro zápis akce spusťte aplikaci pro testování.  
  
     ![Kopírovat do schránky AutomationId](../test/media/cuit_windows_store_tileautomationid.png "CUIT_Windows_Store_TileAutomationID")  
  
4.  Ve spuštěné aplikaci UWP použijte nástroj kříž a vyberte ovládacího prvku tlačítko a ovládacího prvku textového pole. Po přidání všech ovládacích prvků, vyberte **přidání ovládacího prvku na ovládací prvek mapy uživatelského rozhraní** tlačítka na panelu nástrojů Tvůrce programového testu uživatelského rozhraní.  
  
     ![Přidání ovládacího prvku na mapy uživatelského rozhraní](../test/media/cuit_windowsstoreapp_uimap.png "CUIT_WindowsStoreApp_UIMap")  
  
5.  Vyberte **generovat kód** tlačítka na panelu nástrojů Tvůrce programového testu uživatelského rozhraní a pak zvolte **generování** k vytvoření kódu pro změny mapy ovládacího prvku uživatelského rozhraní.  
  
     ![Generování kódu pro mapu uživatelského rozhraní](../test/media/cuit_windowsstoreapp_generate.png "CUIT_WindowsStoreApp_Generate")  
  
6.  Klikněte na tlačítko a nastavte hodnotu do textového pole.  
  
     ![Klikněte na tlačítko – ovládací prvek nastavit hodnotu pole textbox](../test/media/cuit_windowsstoreapp_clickbutton.png "CUIT_WindowsStoreApp_ClickButton")  
  
7.  Pomocí nástroje kříž vyberte ovládacího prvku textového pole a pak vyberte **Text** vlastnost.  
  
     ![Vyberte vlastnost Text](../test/media/cuit_windowsstoreapp_selecttextproperty.png "CUIT_WindowsStoreApp_SelectTextProperty")  
  
8.  Přidáte kontrolní výrazy. Se používá v testu chcete-li ověřit správnost hodnota.  
  
     ![Zvolte testbox s křížové & č. 45; kříž a přidejte assertion](../test/media/cuit_windowsstoreapp_textbox_addassertion.png "CUIT_WindowsStoreApp_Textbox_AddAssertion")  
  
9. Přidejte a generování kódu pro kontrolní výraz.  
  
     ![Generovat kód pro textové pole assertion](../test/media/cuit_windowsstoreapp_textbox_generate_assertion.png "CUIT_WindowsStoreApp_Textbox_Generate_Assertion")  
  
10. **Visual C#**  
  
     V Průzkumníku řešení otevřete soubor UIMap.Designer.cs zobrazíte přidaného kódu pro metodu vyhodnocení a ovládací prvky.  
  
     **Visual Basic**  
  
     V Průzkumníku řešení otevřete soubor CodedUITest1.vb a v kódu metoda CodedUITestMethod1() testu, klikněte pravým tlačítkem na volání metody kontrolní výraz, který byl automaticky přidán `Me.UIMap.AssertMethod1()` a zvolte **přejít k definici**. Otevře se soubor UIMap.Designer.vb v editoru kódu, můžete zobrazit zobrazení přidaného kódu pro metodu vyhodnocení a ovládací prvky.  
  
    > [!WARNING]
    >  Neprovádějte žádné změny souboru UIMap.designer.cs nebo UIMap.Designer.vb přímo. Pokud to uděláte, budou změny provedené v souboru přepsány pokaždé, když se vygeneruje test.  
  
     **Assert – metoda**  
  
    ```csharp  
    public void AssertMethod1()  
    {  
        #region Variable Declarations  
        XamlEdit uITextBoxEdit = this.UIApp1Window.UITextBoxEdit;  
        #endregion  
  
        // Verify that the 'Text' property of 'textBox' text box equals 'button'  
        Assert.AreEqual(this.AssertMethod3ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text);  
    }  
    ```  
  
    ```vb  
    Public Sub AssertMethod1()  
        Dim uITextBoxEdit As XamlEdit = Me.UIApp2Window.UITextBoxEdit  
  
        'Verify that the 'Text' property of 'textBox' text box equals 'button'  
        Assert.AreEqual(Me.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text)  
    End Sub  
    ```  
  
     **Ovládací prvky**  
  
    ```csharp  
    #region Properties  
    public XamlButton UIButtonButton  
    {  
        get  
        {  
            if ((this.mUIButtonButton == null))  
            {  
                this.mUIButtonButton = new XamlButton(this);  
                #region Search Criteria  
                this.mUIButtonButton.SearchProperties[XamlButton.PropertyNames.AutomationId] = "button";  
                this.mUIButtonButton.WindowTitles.Add("App1");  
                #endregion  
            }  
            return this.mUIButtonButton;  
        }  
    }  
  
    public XamlEdit UITextBoxEdit  
    {  
        get  
        {  
            if ((this.mUITextBoxEdit == null))  
            {  
                this.mUITextBoxEdit = new XamlEdit(this);  
                #region Search Criteria  
                this.mUITextBoxEdit.SearchProperties[XamlEdit.PropertyNames.AutomationId] = "textBox";  
                this.mUITextBoxEdit.WindowTitles.Add("App1");  
                #endregion  
            }  
            return this.mUITextBoxEdit;  
        }  
    }  
    #endregion  
  
    #region Fields  
    private XamlButton mUIButtonButton;  
  
    private XamlEdit mUITextBoxEdit;  
    #endregion  
    ```  
  
    ```vb  
    #Region "Properties"  
    Public ReadOnly Property UIButtonButton() As XamlButton  
        Get  
            If (Me.mUIButtonButton Is Nothing) Then  
                Me.mUIButtonButton = New XamlButton(Me)  
                Me.mUIButtonButton.SearchProperties(XamlButton.PropertyNames.AutomationId) = "button"  
                Me.mUIButtonButton.WindowTitles.Add("App2")  
            End If  
            Return Me.mUIButtonButton  
        End Get  
    End Property  
  
    Public ReadOnly Property UITextBoxEdit() As XamlEdit  
        Get  
            If (Me.mUITextBoxEdit Is Nothing) Then  
                Me.mUITextBoxEdit = New XamlEdit(Me)  
                Me.mUITextBoxEdit.SearchProperties(XamlEdit.PropertyNames.AutomationId) = "textBox"  
                Me.mUITextBoxEdit.WindowTitles.Add("App2")  
            End If  
            Return Me.mUITextBoxEdit  
        End Get  
    End Property  
    #End Region  
  
    #Region "Fields"  
    Private mUIButtonButton As XamlButton  
  
    Private mUITextBoxEdit As XamlEdit  
    #End Region  
    ```  
  
11. V Průzkumníku řešení otevřete soubor CodedUITest1.cs nebo CodedUITest1.vb. Nyní můžete přidat kód do metody CodedUTTestMethod1 pro akce potřeba spuštění testu pomocí přidaných zdroje UIMap ovládacích prvků:  
  
    1.  Spusťte aplikaci pro UPW pomocí vlastnosti automatizace ID, které jste zkopírovali dříve do schránky:  
  
        ```csharp  
        XamlWindow.Launch("8ebca7c4-effe-4c86-9998-068daccee452_cyrqexqw8cc7c!App")  
        ```  
  
        ```vb  
        XamlWindow myAppWindow = XamlWindow.Launch("7254db3e-20a7-424e-8e05-7c4dabf4f28d_cyrqexqw8cc7c!App");  
        ```  
  
    2.  Přidejte gesto klepnout na ovládací prvek tlačítko:  
  
        ```csharp  
        Gesture.Tap(this.UIMap.UIApp1Window. UIButtonButton);  
        ```  
  
        ```vb  
        Gesture.Tap(Me.UIMap.UIApp2Window. UIButtonButton)  
        ```  
  
    3.  Ověřit, že po spuštění aplikace pochází volání metody assert, který byl automaticky vytvořen a klepněte na tlačítko gesto:  
  
        ```csharp  
        this.UIMap.AssertMethod1();  
        ```  
  
        ```vb  
        Me.UIMap.AssertMethod1()  
        ```  
  
     Po přidání kód, metodu CodedUITestMethod1 testů se zobrazí následující:  
  
    ```csharp  
    [TestMethod]  
    public void CodedUITestMethod1()  
    {  
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.  
  
        // Launch the app.  
        XamlWindow myAppWindow = XamlWindow.Launch("7254db3e-20a7-424e-8e05-7c4dabf4f28d_cyrqexqw8cc7c!App");  
  
        // Tap the button.  
        Gesture.Tap(this.UIMap.UIApp1Window.UIButtonButton);  
  
        this.UIMap.AssertMethod1();  
    }  
    ```  
  
    ```vb  
    <CodedUITest(CodedUITestType.WindowsStore)>  
    Public Class CodedUITest1  
  
        <TestMethod()>  
        Public Sub CodedUITestMethod1()  
            '              
            ' To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.  
            '  
  
            ' Launch the app.  
            XamlWindow.Launch("8ebca7c4-effe-4c86-9998-068daccee452_cyrqexqw8cc7c!App")  
  
            '// Tap the button.  
            Gesture.Tap(Me.UIMap.UIApp2Window.UIButtonButton)  
  
            Me.UIMap.AssertMethod1()  
        End Sub  
    ```  
  
12. Sestavte svůj test a pak spusťte test pomocí Průzkumníka testů.  
  
     ![Spustit programových testů uživatelského rozhraní z Průzkumníka testů](../test/media/cuit_windowsstoreapp_runtest.png "CUIT_WindowsStoreApp_RunTest")  
  
     Spustí aplikaci pro UPW, akce klepněte na tlačítko po dokončení a textové pole Text vlastnost je vyplněný a ověřené pomocí metody assert.  
  
     ![Spuštění programového testu UI](../test/media/cuit_windowsstoreapp_running.png "CUIT_WindowsStoreApp_Running")  
  
     Po dokončení testu Průzkumníka testů se zobrazí, že test proběhl úspěšně.  
  
     ![Předaný testovací zobrazí v Průzkumníku testování](../test/media/cuit_windowsstorapp_passedtest.png "CUIT_WindowsStorApp_PassedTest")  
  
## <a name="q--a"></a>Dotazy a odpovědi  
  
#### <a name="q-why-dont-i-see-the-option-to-record-my-coded-ui-test-in-the-generate-code-for-a-coded-ui-test-dialog"></a>Otázka: Proč se nezobrazí možnost zaznamenat Moje programového testu uživatelského rozhraní v generování kódu pro dialogové okno programových testů uživatelského rozhraní? **  
  
**A**: pro aplikace UWP není podporována možnost záznam.  
  
#### <a name="q-can-i-create-a-coded-ui-test-for-my-uwp-apps-based-on-winjs"></a>Otázka: je možné vytvořit programového testu uživatelského rozhraní pro Moje aplikace UWP podle WinJS? **  

**A**: Ne, jsou podporovány pouze na základě XAML aplikace.  
  
#### <a name="q-can-i-create-coded-ui-tests-for-my-uwp-apps-on-a-system-that-is-not-running-windows-81-or-windows-10"></a>Otázka: je možné vytvořit programové testy uživatelského rozhraní pro Moje aplikace UWP v systému, který není systémem Windows 8.1 nebo Windows 10? **  
  
**A**: Ne, programového uživatelského rozhraní testovacího projektu šablony jsou dostupné jenom na Windows 8.1 a Windows 10. Pokud chcete vytvořit automatizace pro univerzální platformu Windows (UWP) aplikace, budete potřebovat Windows 10.  

<a name="uwpapps"></a>  
#### <a name="q-how-do-i-create-coded-ui-tests-for-universal-windows-platform-uwp-apps"></a>Otázka: jak vytvářet programové testy uživatelského rozhraní pro aplikace pro univerzální platformu Windows (UWP)? **  
  
**A**: v závislosti na platformě, kde vaše aplikace pro UPW testujete, vytvoření projektu programových testů uživatelského rozhraní v jednom z těchto způsobů:  
  
- UWP aplikaci spuštěnou na místní počítač se spustí jako aplikace pro UPW. Abyste to mohli otestovat, musíte použít **programového uživatelského rozhraní testování projektu (Windows)** šablony. Tato šablona při vytvoření nového projektu, najdete **Windows**, **Universal** uzlu. Nebo se podívejte na **Windows**, **Windows 8**, **Windows** uzlu.  
  
- Aplikace pro UPW se systémem na mobilní zařízení nebo emulátoru se spustí jako telefonní aplikace. Abyste to mohli otestovat, musíte použít **programového uživatelského rozhraní testování projektu (Windows Phone)** šablony. Tato šablona při vytvoření nového projektu, najdete **Windows**, **Universal** uzlu. Nebo se podívejte na **Windows**, **Windows 8**, **Windows Phone** uzlu.  
  
Po vytvoření projektu, vytváření testu zůstává stejná jako předtím.  
  
#### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>Otázka: Proč nelze změnit kód v souboru UIMap.Designer? **  
  
**A**: změny kódu provedené v souboru UIMapDesigner.cs budou přepsány pokaždé, když generování kódu pomocí zdroje UIMap - Tvůrce programového testu uživatelského rozhraní. Pokud je třeba změnit zaznamenanou metodu, musíte ji zkopírovat do souboru UIMap.cs a přejmenovat ji. Soubor UIMap.cs lze použít k přepsání metod a vlastností v souboru UIMapDesigner.cs. Je třeba odebrat odkaz na původní metodu v kódovaném souboru UITest.cs a nahradit ji názvem přejmenované metody.  
  
## <a name="see-also"></a>Viz také  
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
 [Nastavení jedinečné vlastnosti automatizace pro ovládací prvky UWP za účelem testování](../test/set-a-unique-automation-property-for-windows-store-controls-for-testing.md)
