---
title: "Testování UWP aplikace Windows a 8.1 Phone pomocí programových testů uživatelského rozhraní | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- uwp
author: gewarren
ms.openlocfilehash: ba0366ce882d1a4c2b715e621343dcbc0db6f457
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="test-windows-uwp-and-81-phone-apps-with-coded-ui-tests"></a>Testování UWP aplikace Windows a 8.1 Phone pomocí programových testů uživatelského rozhraní

Pomocí tohoto průvodce použijte pro vytvoření testů uživatelského rozhraní pro aplikace UWP, které běží na mobilní zařízení nebo emulátorů a aplikací založených na XAML Phone 8.1.

## <a name="create-a-simple-windows-phone-app"></a>Vytvoření jednoduché aplikace pro Windows Phone

1.  Vytvoření nového projektu pro prázdnou aplikaci pro Windows Phone pomocí šablony buď Visual C# nebo Visual Basic.

     ![Vytvoření nové aplikace pro Windows Phone](../test/media/cuit_phone_app_newproject.png "CUIT_Phone_App_NewProject")

2.  V Průzkumníku řešení otevřete MainPage.xaml. Z panelu nástrojů přetáhněte ovládací prvek tlačítko a ovládacího prvku textového pole na plochu návrháře.

     ![Přidání contols do MainPage.xaml](../test/media/cuit_phone_app_addcontrols.png "CUIT_Phone_App_AddControls")

3.  V okně vlastností název ovládacího prvku tlačítko.

     ![Název ovládacího prvku tlačítko](../test/media/cuit_phone_namebutton.png "CUIT_Phone_NameButton")

4.  Název ovládacího prvku textového pole.

     ![Název ovládacího prvku textbox](../test/media/cuit_phone_nametesxtbox.png "CUIT_Phone_NameTesxtBox")

5.  Na plochu návrháře dvakrát klikněte tlačítko – ovládací prvek a přidejte následující kód:

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

6.  Stisknutím klávesy F5 spusťte aplikace pro Windows Phone v emulátoru a ověřte, že funguje.

     ![Spuštění Windows Phone aplikace](../test/media/cuit_phone_runapp.png "CUIt_Phone_RunApp")

7.  Ukončete emulátor.

## <a name="deploy-the-windows-phone-app"></a>Nasazení Windows Phone aplikace

1.  Než programového testu uživatelského rozhraní můžete namapovat ovládací prvky aplikace, musíte k nasazení aplikace.

     ![Nasazení Windows Phone aplikace](../test/media/cuit_phone_deploy.png "CUIT_Phone_Deploy")

     Spustí se emulátor. Aplikace je nyní k dispozici pro testování.

     ![Aplikace nasazené na emulátoru](../test/media/cuit_phone_deployed.png "CUIT_Phone_Deployed")

     Zachovat emulátoru běží, zatímco vytvoření vaší programového testu uživatelského rozhraní.

## <a name="create-a-coded-ui-test-for-the-windows-phone-app"></a>Vytvoření programového testu uživatelského rozhraní pro aplikace Windows Phone

[Vytvoření programové testy uživatelského rozhraní pro aplikace pro univerzální platformu Windows (UWP)](#uwpapps)

1.  Přidáte nový projekt programového testu uživatelského rozhraní k řešení s aplikací Windows Phone.

     ![Vytvoření nové programového testu uživatelského rozhraní pro Windows Phone](../test/media/cuit_phone_newproject.png "CUIT_Phone_NewProject")

2.  Zvolte úpravu mapování uživatelského rozhraní pomocí nástroje kříž.

     ![Generování programových uživatelského rozhraní test pomocí mezi&#45;kříž nástroj. ] (../test/media/cuit_phone_howgencodedialog.png "CUIT_Phone_HowGenCodeDialog")

3.  Vyberte aplikaci, použijte nástroj kříž, pak zkopírujte hodnotu pro aplikace **AutomationId** vlastnost, která se použije později a spusťte aplikaci v testu.

     ![Zkopírujte hodnotu AutomationId aplikace](../test/media/cuit_phone_getautomationid.png "CUIT_Phone_GetAutomationId")

4.  V emulátoru spusťte aplikaci a pomocí nástroje kříž vyberte ovládací prvek tlačítko. Přidejte do mapy ovládacího prvku uživatelského rozhraní ovládacího prvku tlačítko.

     ![Použít mezi&#45;kříž nástroj pro mapování ovládacích prvků](../test/media/cuit_phone_mapbuttoncontrol.png "CUIT_Phone_MapButtonControl")

5.  Přidání ovládacího prvku textového pole pro ovládací prvek mapy uživatelského rozhraní, opakujte předchozí krok.

     ![Použít mezi&#45;kříž nástroj a mapy textbox – ovládací prvek](../test/media/cuit_phone_maptextboxcontrol.png "CUIT_Phone_MapTextBoxControl")

6.  Generovat kód pro vytvoření kód pro změny mapy ovládacího prvku uživatelského rozhraní.

     ![Generování kódu z Tvůrce](../test/media/cuit_phone_generatecode.png "CUIT_Phone_GenerateCode")

7.  Pomocí nástroje kříž vyberte ovládacího prvku textového pole a pak vyberte **Text** vlastnost.

     ![Vyberte vlastnost Text](../test/media/cuit_phone_textproperty.png "CUIT_Phone_TextProperty")

8.  Přidáte kontrolní výrazy. Se používá v testu chcete-li ověřit správnost hodnota.

     ![Přidat kontrolní výraz k testovací](../test/media/cuit_phone_addassertion.png "CUIT_Phone_AddAssertion")

9. Přidejte a generovat kód pro metodu vyhodnocení.

     ![Generovat kód pro kontrolní výraz](../test/media/cuit_phone_generatecodeassertion.png "CUIT_Phone_GenerateCodeAssertion")

10. **Visual C#**

     V Průzkumníku řešení otevřete soubor UIMap.Designer.cs zobrazíte kód, který jste právě přidali pro metodu vyhodnocení a ovládací prvky.

     **Visual Basic**

     V Průzkumníku řešení otevřete soubor CodedUITest1.vb. V CodedUITestMethod1() testování metoda kódu, klikněte pravým tlačítkem na volání metody kontrolní výraz, který byl automaticky přidán `Me.UIMap.AssertMethod1()` a zvolte **přejít k definici**. Otevře se soubor UIMap.Designer.vb v editoru kódu, můžete zobrazit kód, který jste přidali pro metodu vyhodnocení a ovládací prvky.

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
        Assert.AreEqual(this.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text);
    }
    ```

    ```vb
    Public Sub AssertMethod1()
        Dim uITextBoxEdit As XamlEdit = Me.UIApp1Window.UITextBoxEdit

        'Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(Me.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text)
    End Sub
    ```

     **Ovládací prvky**

    ```csharp
    #region Properties
    public virtual AssertMethod1ExpectedValues AssertMethod1ExpectedValues
    {
        get
        {
            if ((this.mAssertMethod1ExpectedValues == null))
            {
                this.mAssertMethod1ExpectedValues = new AssertMethod1ExpectedValues();
            }
            return this.mAssertMethod1ExpectedValues;
        }
    }

    public UIApp1Window UIApp1Window
    {
        get
        {
            if ((this.mUIApp1Window == null))
            {
                this.mUIApp1Window = new UIApp1Window();
            }
            return this.mUIApp1Window;
        }
    }
    #endregion

    #region Fields
    private AssertMethod1ExpectedValues mAssertMethod1ExpectedValues;

    private UIApp1Window mUIApp1Window;
    #endregion
    ```

    ```vb
    #Region "Properties"
    Public ReadOnly Property UIButtonButton() As XamlButton
        Get
            If (Me.mUIButtonButton Is Nothing) Then
                Me.mUIButtonButton = New XamlButton(Me)
                Me.mUIButtonButton.SearchProperties(XamlButton.PropertyNames.AutomationId) = "button"
            End If
            Return Me.mUIButtonButton
        End Get
    End Property

    Public ReadOnly Property UITextBoxEdit() As XamlEdit
        Get
            If (Me.mUITextBoxEdit Is Nothing) Then
                Me.mUITextBoxEdit = New XamlEdit(Me)
                Me.mUITextBoxEdit.SearchProperties(XamlEdit.PropertyNames.AutomationId) = "textBox"
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

11. V Průzkumníku řešení otevřete soubor CodedUITest1.cs nebo CodedUITest1.vb. Teď můžete přidat kód do metody CodedUTTestMethod1 pro akce potřebné ke spuštění testu. Pomocí ovládacích prvků, které byly přidány do zdroje UIMap přidat kód:

    1.  Spuštění aplikace Windows Phone pomocí vlastnosti automatizace ID, které jste zkopírovali dříve do schránky:

        ```csharp
        XamlWindow myAppWindow = XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App");
        ```

        ```vb
        XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App");
        ```

    2.  Přidejte gesto klepnout na ovládací prvek tlačítko:

        ```csharp
        Gesture.Tap(this.UIMap.UIApp1Window.UIButtonButton);
        ```

        ```vb
        Gesture.Tap(Me.UIMap.UIApp1Window.UIButtonButton)
        ```

    3.  Ověřit, že po spuštění aplikace pochází volání metody assert, který byl automaticky vytvořen a klepněte na tlačítko gesto:

        ```csharp
        this.UIMap.AssertMethod1();
        ```

        ```vb
        Me.UIMap.AssertMethod1()
        ```

     Po přidání kód metody testu CodedUITestMethod1 by měl vypadat takto:

    ```csharp
    [TestMethod]
    public void CodedUITestMethod1()
    {
        // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.

        // Launch the app.
        XamlWindow myAppWindow = XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App");

        // Tap the button.
        Gesture.Tap(this.UIMap.UIApp1Window.UIButtonButton);

        this.UIMap.AssertMethod1();
    }
    ```

    ```vb
    <CodedUITest>
    Public Class CodedUITest1

        <TestMethod()>
        Public Sub CodedUITestMethod1()
            '
            ' To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
            '
            ' Launch the app.
            XamlWindow.Launch("ed85f6ff-2fd1-4ec5-9eef-696026c3fa7b_cyrqexqw8cc7c!App")

            '// Tap the button.
            Gesture.Tap(Me.UIMap.UIApp1Window.UIButtonButton)

            Me.UIMap.AssertMethod1()
        End Sub
    ```

## <a name="run-the-coded-ui-test"></a>Spuštění programových testů uživatelského rozhraní

1.  Sestavte svůj test a pak spusťte test pomocí Průzkumníka testů.

     ![Sestavení a spuštění testu pomocí Průzkumníka testů](../test/media/cuit_phone_runtestexplorer.png "CUIT_Phone_RunTestExplorer")

     Spuštění aplikace Windows Phone, akce klepněte na tlačítko po dokončení a textové pole Text vlastnost je vyplněný a ověřené pomocí metody assert.

     ![Probíhá test produktu Windows Phone](../test/media/cuit_phone_runtestexplorerrunning.png "CUIT_Phone_RunTestExplorerRunning")

     Po dokončení testu Průzkumníka testů potvrdí, že test proběhl úspěšně.

     ![Průzkumník výsledky testu](../test/media/cuit_phone_runtestexplorerresults.png "CUIT_Phone_RunTestExplorerResults")

##  <a name="TestingPhoneAppsCodedUI_DataDriven"></a> Použití řízené daty programové testy uživatelského rozhraní pro aplikace z Windows Phone
 K testování různých podmínkách, programového testu uživatelského rozhraní lze spustit několikrát s různými sadami data.

 Řízené daty testy programového uživatelského rozhraní pro Windows Phone jsou definovány pomocí atributu DataRow na testovací metoda. V následujícím příkladu, x a y pomocí hodnoty 1 a 2 pro první iterace a -1 -2 pro druhý iterace testu.

```
[DataRow(1, 2, DisplayName = "Add positive numbers")]
[DataRow(-1, -2, DisplayName = "Add negative numbers")]
[TestMethod]
public void DataDrivingDemo_MyTestMethod(int x, int y)

```

## <a name="q--a"></a>Dotazy a odpovědi

### <a name="q-do-i-have-to-deploy-the-windows-phone-app-in-the-emulator-in-order-to-map-ui-controls"></a>Otázka: je nutné k nasazení aplikace Windows Phone v emulátoru účely mapování ovládacích prvků uživatelského rozhraní?
 **A**: Ano, Tvůrce programového testu uživatelského rozhraní vyžaduje, aby emulátor používat a do zařízení nasadit aplikaci. V opačném případě vyvolají chybová zpráva s oznámením, že nebyla nalezena žádná spuštěného emulátoru.

###  <a name="TestingPhoneAppsCodedUI_EmulatorDevice"></a> Otázka: je možné testy provést u pouze emulátoru, nebo můžete I taky použít fyzické zařízení?
 **A**: buď možnost je podporována. Změna typu emulátoru nebo zařízení, vyberte v panelu nástrojů zařízení je vybrána cíle pro spuštění testu. Pokud je vybrané zařízení, musí být připojené k jednomu z portů USB počítače Phone Blue zařízení.

 ![Vyberte verzi emulátoru nebo fyzická zařízení](../test/media/cuit_phone_testtarget.png "CUIT_Phone_TestTarget")

### <a name="q-why-dont-i-see-the-option-to-record-my-coded-ui-test-in-the-generate-code-for-a-coded-ui-test-dialog"></a>Otázka: Proč nevidíte možnost zaznamenat Moje programového testu uživatelského rozhraní v generování kódu pro dialogové okno programových testů uživatelského rozhraní
 **A**: není podporována možnost záznam pro aplikace Windows Phone.

### <a name="q-can-i-create-a-coded-ui-test-for-my-windows-phone-apps-based-on-winjs-silverlight-or-html5"></a>Otázka: je možné vytvořit programového testu uživatelského rozhraní pro Moje aplikace Windows Phone na základě WinJS, Silverlight nebo HTML5?
 **A**: Ne, jsou podporovány pouze na základě XAML aplikace.

### <a name="q-can-i-create-coded-ui-tests-for-my-windows-phone-apps-on-a-system-that-is-not-running-windows-81-or-windows-10"></a>Otázka: je možné vytvořit programové testy uživatelského rozhraní pro Moje aplikace Windows Phone v systému, který není systémem Windows 8.1 nebo Windows 10?
 **A**: Ne, programového uživatelského rozhraní testovacího projektu šablony jsou dostupné jenom na Windows 8.1 a Windows 10. Pokud chcete vytvořit automatizace pro univerzální platformu Windows (UWP) aplikace, budete potřebovat Windows 10.

<a name="uwpapps"></a>
### <a name="q-how-do-i-create-coded-ui-tests-for-universal-windows-platform-uwp-apps"></a>Otázka: jak vytvořit programové testy uživatelského rozhraní pro aplikace pro univerzální platformu Windows (UWP)?
 **A**: v závislosti na platformě, kde vaše aplikace pro UPW testujete, vytvoření projektu programových testů uživatelského rozhraní v jednom z těchto způsobů:

-   UWP aplikaci spuštěnou na místní počítač se spustí jako aplikace pro UPW. Abyste to mohli otestovat, musíte použít **programového uživatelského rozhraní testování projektu (Windows)** šablony. Tato šablona při vytvoření nového projektu, najdete **Windows**, **Universal** uzlu. Nebo se podívejte na **Windows**, **Windows 8**, **Windows** uzlu.

-   Aplikace pro UPW se systémem na mobilní zařízení nebo emulátoru se spustí jako telefonní aplikace. Abyste to mohli otestovat, musíte použít **programového uživatelského rozhraní testování projektu (Windows Phone)** šablony. Tato šablona při vytvoření nového projektu, najdete **Windows**, **Universal** uzlu. Nebo se podívejte na **Windows**, **Windows 8**, **Windows Phone** uzlu.

 Po vytvoření projektu, vytváření testu zůstává stejná jako předtím.

### <a name="q-can-i-select-controls-that-are-outside-the-emulator"></a>Otázka: je možné vybrat ovládací prvky, které jsou mimo emulátoru?
 **A**: Tvůrce Ne, nerozpozná je.

### <a name="q-can-i-use-the-coded-ui-test-builder-to-map-controls-using-a-physical-phone-device"></a>Otázka: je možné použít Tvůrce programového testu uživatelského rozhraní pro mapování ovládacích prvků pomocí fyzických phone zařízení?
 **A**: Ne, Tvůrce mapují prvky uživatelského rozhraní Pokud byla aplikace nasazena do emulátoru.

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>Otázka: Proč nelze změnit kód v souboru UIMap.Designer?
 **A**: změny kódu provedené v souboru UIMapDesigner.cs budou přepsány pokaždé, když generování kódu pomocí zdroje UIMap - Tvůrce programového testu uživatelského rozhraní. Pokud je třeba změnit zaznamenanou metodu, musíte ji zkopírovat do souboru UIMap.cs a přejmenovat ji. Soubor UIMap.cs lze použít k přepsání metod a vlastností v souboru UIMapDesigner.cs. Je třeba odebrat odkaz na původní metodu v kódovaném souboru UITest.cs a nahradit ji názvem přejmenované metody.

### <a name="q-can-i-run-a-coded-ui-test-on-my-windows-phone-app-from-the-command-line"></a>Otázka: Mohu spustit programového testu uživatelského rozhraní v mé aplikace Windows Phone z příkazového řádku?
 **A**: Ano, použít souboru runsettings k určení cílového zařízení pro spuštění testu. Příklad:

 **vstest.Console.exe /settings:devicetarget.runsettings "pathToYourCodedUITestDll"**

 Ukázkový soubor runsettings:

```
<?xml version="1.0" encoding="utf-8"?>
<RunSettings>
<MSPhoneTest>
<!--to specify test execution on device, use a TargetDevice option as follows-->
<TargetDevice>Device</TargetDevice>
<!--to specify an emulator instead, use a TargetDevice option like below-->
<!--<TargetDevice>Emulator 8.1 WVGA 4 inch 512MB</TargetDevice>-->
</MSPhoneTest>
</RunSettings>
```

### <a name="q-what-are-the-differences-between-coded-ui-tests-for-xaml-based-uwp-apps-and-windows-phone-apps"></a>Otázka: co jsou rozdíly mezi programové testy uživatelského rozhraní pro aplikace UWP založených na XAML a aplikací Windows Phone?
 **A**: Toto jsou některé klíčové rozdíly:

|Funkce|Aplikace UWP|Aplikace Windows Phone|
|-------------|------------------------|------------------------|
|Cíl pro spouštění testů|Místním nebo vzdáleném počítači. Vzdálené počítače lze zadat, pokud používáte ke spuštění testů automatizované testovacího případu.|Emulátoru nebo zařízení. Zobrazit, [Otázka: může testy provést v emulátoru pouze nebo I taky použít fyzické zařízení?](#TestingPhoneAppsCodedUI_EmulatorDevice) v tomto tématu.|
|Spuštění z příkazového řádku|Není zapotřebí zadat cílový soubor s nastavením.|Vyžaduje k určení cílového souboru Runsettings.|
|Specializované třídy pro ovládacích prvků prostředí|<xref:Microsoft.VisualStudio.TestTools.UITesting.DirectUIControls.DirectUIControl>|<xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl>|
|Webové zobrazení ovládacího prvku aplikace XAML|Podporované, pokud používáte Html * specializuje třídy pro interakci s elementů HTML. V tématu <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>.|Není podporováno.|
|Spuštění automatizovaných testů z MTM|Podporováno.|Není podporováno.|
|Testy řízené daty|V tématu [řízené daty testy](../test/creating-a-data-driven-coded-ui-test.md) informace o používání externí zdroje dat a zdroj dat atributu u metoda testu.|Data jsou zadané vložené, pomocí atributu DataRow na testovací metoda. V tématu [řízené daty pomocí programových testů uživatelského rozhraní pro aplikace z Windows Phone](#TestingPhoneAppsCodedUI_DataDriven) v tomto tématu.|

 Informace o programové testy uživatelského rozhraní pro aplikace UWP najdete v tématu [aplikací pro UPW Windows Test pomocí programových testů uživatelského rozhraní](../test/test-windows-store-8-1-apps-with-coded-ui-tests.md).

## <a name="external-resources"></a>Externí zdroje
 Správa životního cyklu aplikací Visual Studio Microsoft blog: [pomocí programových uživatelského rozhraní k testování aplikací založených na XAML Windows Phone](http://blogs.msdn.com/b/visualstudioalm/archive/2014/04/05/using-coded-ui-to-test-xaml-based-windows-phone-apps.aspx?PageIndex=2#comments)

## <a name="see-also"></a>Viz také
 [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
