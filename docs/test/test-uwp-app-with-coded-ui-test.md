---
title: Testování aplikací UWP pomocí programových testů uživatelského rozhraní
ms.date: 05/31/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- uwp
ms.openlocfilehash: 081c61cb0d5a2db28b04ebdd12fd53713b41363f
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34694117"
---
# <a name="create-a-coded-ui-test-to-test-a-uwp-app"></a>Vytvoření programové uživatelského rozhraní testu aplikace UWP

Tento článek vysvětluje postup vytvoření programového testu UI pro univerzální platformu Windows (UWP) aplikace.

## <a name="create-a-uwp-app-to-test"></a>Vytvořit aplikaci UWP k testování

Prvním krokem je vytvoření jednoduché aplikace pro UPW, ke spuštění testu proti.

1. V sadě Visual Studio vytvořte nový projekt pomocí **prázdná aplikace (univerzální pro Windows)** šablonu pro Visual C# nebo Visual Basic.

     ![Šablony prázdnou aplikaci pro univerzální systému Windows](../test/media/blank-uwp-app-template.png)

1. V **nový projekt univerzální platformu Windows** dialogovém okně, vyberte **OK** přijmout výchozí verze platformy.

1. Z **Průzkumníku řešení**, otevřete *MainPage.xaml*.

   Soubor se otevře v **návrháře XAML**.

1. Přetáhněte ovládací prvek tlačítko a ovládacím prvku textbox z **sada nástrojů** na plochu návrháře.

     ![Návrh aplikace pro UPW](../test/media/toolbox-controls.png)

1. Zadejte název pro ovládací prvky. Vyberte ovládacího prvku textového pole a potom v **vlastnosti** okno, zadejte **textBox** v **název** pole. Vyberte ovládací prvek tlačítko a potom v **vlastnosti** okno, zadejte **tlačítko** v **název** pole.

1. Dvakrát klikněte tlačítko – ovládací prvek a přidejte následující kód k tělu `Button_Click` metoda. Tento kód jednoduše nastaví text do textového pole název prvku tlačítka jenom k Řekněte nám něco k ověření s programového testu uživatelského rozhraní, které vytvoříme později.

   ```csharp
   this.textBox.Text = this.button.Name;
   ```

   ```vb
   Me.textBox.Text = Me.button.Name
   ```

1. Stiskněte klávesu **Ctrl**+**F5** a spusťte aplikaci. Měli byste vidět něco jako následující:

   ![Aplikace pro UPW s tlačítko a textové pole](media/uwp-app.png)

## <a name="create-a-coded-ui-test"></a>Vytvoření programového testu UI

1. Chcete-li do řešení přidat testovacího projektu, klikněte pravým tlačítkem na řešení v **Průzkumníku řešení** a zvolte **přidat** > **nový projekt**.

1. V **nový projekt** dialogovém okně, vyberte **programového projektu testování uživatelského rozhraní (Universal Windows)** šablony. Můžete najít v šabloně **univerzální pro Windows** kategorii v **Visual C#** nebo **jazyka Visual Basic**.

     ![Nový projekt programových testů uživatelského rozhraní](../test/media/coded-ui-test-project-uwp-template.png)

   > [!NOTE]
   > Pokud nevidíte **programového uživatelského rozhraní testování projektu (Universal Windows)** šablony, budete muset [nainstalovat součást programového testu uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#install-the-coded-ui-test-component).

1. V **generovat kód pro programové testování uživatelského rozhraní** dialogovém okně, vyberte **ručně upravte test**.

     ![Generování kódu pro dialog s programových testů uživatelského rozhraní](../test/media/manually-edit-the-test.png)

1. Pokud vaše aplikace pro UPW ještě není spuštěná, spusťte ji stisknutím **Ctrl**+**F5**.

1. Otevřete **Tvůrce programového testu uživatelského rozhraní** dialogové okno umístěním kurzoru v `CodedUITestMethod1` metoda a pak vyberete **Test** > **generovat kód pro programového testu uživatelského rozhraní**  >  **Použití programových Tvůrce testu uživatelského rozhraní**.

1. Přidání ovládacích prvků mapy ovládacího prvku uživatelského rozhraní. Použití **Tvůrce programového testu uživatelského rozhraní** kříž nástroj pro výběr ovládacího prvku tlačítko v aplikaci pro UPW. V **přidat kontrolní výrazy** dialogové okno, rozbalte **mapy ovládacího prvku uživatelského rozhraní** podokně Pokud potřebné a pak vyberte **přidání ovládacího prvku na ovládací prvek mapy uživatelského rozhraní**.

     ![Přidání ovládacího prvku na mapy uživatelského rozhraní](../test/media/add-control-to-ui-control-map.png)

1. Opakujte předchozí krok pro přidání ovládacího prvku textbox mapy ovládacího prvku uživatelského rozhraní.

1. V **Tvůrce programového testu uživatelského rozhraní** dialogovém okně, vyberte **generovat kód** nebo stiskněte klávesu **Ctrl**+**G**. Potom vyberte **generování** k vytvoření kódu pro změny mapy ovládacího prvku uživatelského rozhraní.

     ![Generování kódu pro mapu uživatelského rozhraní](../test/media/generate-code-dialog.png)

1. Chcete-li ověřit, že se text do textového pole text změní na **tlačítko** při kliknutí na tlačítko, klikněte na tlačítko.

     ![Klikněte na tlačítko – ovládací prvek nastavit hodnotu pole textbox](../test/media/uwp-app-button-textbox.png)

1. Přidáte kontrolní výrazy ověření text v ovládacím prvku textbox. Pomocí nástroje kříž vyberte ovládacího prvku textového pole a pak vyberte **Text** vlastnost **přidat kontrolní výrazy** dialogové okno. Pak vyberte **přidat kontrolní** nebo stiskněte klávesu **Alt**+**A**. V **zprávy při vyhodnocení výrazu se nezdařilo** zadejte **hodnotu pole Textbox neočekávané.** a pak vyberte **OK**.

     ![Zvolte textové pole s kříž a přidat kontrolní výraz](../test/media/add-assertion-for-text.png)

1. Generovat kód pro test pro kontrolní výraz. V **Tvůrce programového testu uživatelského rozhraní** dialogovém okně, vyberte **generovat kód**. V **generovat kód** dialogovém okně, vyberte **přidat a generovat**.

     ![Generovat kód pro textové pole assertion](../test/media/add-and-generate-assert-method.png)

   V **Průzkumníku řešení**, otevřete *UIMap.Designer.cs* zobrazíte přidaného kódu pro metodu vyhodnocení a ovládací prvky.

   > [!TIP]
   > Pokud používáte Visual Basic, otevřete *CodedUITest1.vb*. Potom v `CodedUITestMethod1()` testování metoda kódu, klikněte pravým tlačítkem na volání metody assert `Me.UIMap.AssertMethod1()` a zvolte **přejít k definici**. *UIMap.Designer.vb* otevře v editoru kódu a můžete zobrazit přidaného kódu pro metodu vyhodnocení a ovládací prvky.

    > [!WARNING]
    > Nelze změnit *UIMap.designer.cs* nebo *UIMap.Designer.vb* soubory přímo. Pokud tak učiníte, změny budou přepsány při vygenerování testu.

    Metody assert vypadá takto:

    ```csharp
    public void AssertMethod1()
    {
        #region Variable Declarations
        XamlEdit uITextBoxEdit = this.UIUWPAppWindow.UITextBoxEdit;
        #endregion

        // Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(this.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text, "Textbox value is unexpected.");
    }
    ```

    ```vb
    Public Sub AssertMethod1()
        Dim uITextBoxEdit As XamlEdit = Me.UIApp2Window.UITextBoxEdit

        'Verify that the 'Text' property of 'textBox' text box equals 'button'
        Assert.AreEqual(Me.AssertMethod1ExpectedValues.UITextBoxEditText, uITextBoxEdit.Text, "Textbox value is unexpected.")
    End Sub
    ```
1. Dále je potřeba získat **AutomationId** z UWP [aplikace](#create-a-simple-universal-windows-app) , jsme chcete otestovat. Otevřete Windows **spustit** nabídky zobrazíte dlaždici pro aplikaci. Přetáhněte nástroj kříž ![cílovou ikonu](media/target-icon.png) z **Tvůrce programového testu uživatelského rozhraní** dialogovém dlaždici pro vaši aplikaci. Když pole blue obklopuje dlaždici, uvolněte myši.

   ![Nástroj kříž](media/cross-hair-tool.png)

   **Přidat kontrolní výrazy** se zobrazí dialogové okno **AutomationId** pro vaši aplikaci. Klikněte pravým tlačítkem na **AutomationId** a zvolte **hodnotu kopírování do schránky**.

   ![AutomationID v dialogovém okně Přidat kontrolní výraz](../test/media/automation-id.png)

1. Přidejte kód do metody testu spusťte aplikaci UWP. V **Průzkumníku řešení**, otevřete *CodedUITest1.cs* nebo *CodedUITest1.vb*. Výše volání `AssertMethod1`, přidat kód pro spuštění aplikace UPW:

   ```csharp
   XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App")
   ```

   ```vb
   XamlWindow myAppWindow = XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App");
   ```

   ID automatizace v příkladu kódu nahraďte hodnotu, kterou jste zkopírovali do schránky v předchozím kroku.

   > [!IMPORTANT]
   > Trim – začátek ID automatizace odebrat znaky, jako **P ~**. Pokud nemáte trim tyto znaky, vyvolá test `Microsoft.VisualStudio.TestTools.UITest.Extension.PlaybackFailureException` při pokusu o spuštění aplikace.

1. Dál přidejte kód do metody testu klikněte na tlačítko. Na řádku po `XamlWindow.Launch`, přidejte gesto klepnout na ovládací prvek tlačítko:

   ```csharp
   Gesture.Tap(this.UIMap.UIUWPAppWindow.UIButtonButton);
   ```

   ```vb
   Gesture.Tap(Me.UIMap.UIUWPAppWindow.UIButtonButton)
   ```

   Po přidání kód kompletní `CodedUITestMethod1` metoda test by měl vypadat takto:

   ```csharp
   [TestMethod]
   public void CodedUITestMethod1()
   {
       XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App");

       Gesture.Tap(this.UIMap.UIUWPAppWindow.UIButtonButton);

       // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
       this.UIMap.AssertMethod1();
   }
   ```

   ```vb
   <CodedUITest(CodedUITestType.WindowsStore)>
   Public Class CodedUITest1

       <TestMethod()>
       Public Sub CodedUITestMethod1()

           ' Launch the app.
           XamlWindow.Launch("af5ecd75-f252-45a1-9e7e-c6f1d8f054ff_0q1pp7qrjexbp!App")

           '// Tap the button.
           Gesture.Tap(Me.UIMap.UIUWPAppWindow.UIButtonButton)

           Me.UIMap.AssertMethod1()
       End Sub
   ```

1. Sestavení k testovacímu projektu a pak otevřete **testování Explorer** výběrem **testování** > **Windows** > **testování Explorer**.

1. Vyberte **spustit všechny** ke spuštění testu.

   Otevře aplikaci, na tlačítko je stisknuté a textové pole **Text** se naplní vlastnost. Metody assert ověří textového pole **Text** vlastnost.

   Po dokončení testu **testování Explorer** obrazovek, které test proběhl úspěšně.

   ![Předaný testů se zobrazí v Průzkumníka testů](../test/media/test-explorer-coded-ui-test-passed.png)

## <a name="q--a"></a>Dotazy a odpovědi

### <a name="q-why-dont-i-see-the-option-to-record-my-coded-ui-test-in-the-generate-code-for-a-coded-ui-test-dialog"></a>Otázka: Proč nevidíte možnost zaznamenat Moje programového testu uživatelského rozhraní v generování kódu pro dialogové okno programových testů uživatelského rozhraní

**A**: pro aplikace UWP není podporována možnost záznam.

### <a name="q-can-i-create-a-coded-ui-test-for-my-uwp-apps-based-on-winjs"></a>Otázka: je možné vytvořit programového testu uživatelského rozhraní pro Moje aplikace UWP podle WinJS?

**A**: Ne, jsou podporovány pouze aplikací založených na XAML.

### <a name="q-why-cant-i-modify-the-code-in-the-uimapdesigner-file"></a>Otázka: Proč nelze změnit kód v souboru UIMap.Designer?

**A**: všechny změny v kódu *UIMapDesigner.cs* soubor se přepíše pokaždé, když generování kódu pomocí **Tvůrce programového testu uživatelského rozhraní**. Pokud máte zaznamenaná metodu, zkopírujte ho do *UIMap.cs* souborů a přejmenujte ji. *UIMap.cs* soubor lze použít k přepsání metody a vlastnosti v *UIMapDesigner.cs* souboru. Odeberte odkaz na původní metody v *CodedUITest.cs* a nahraďte název přejmenované metody.

## <a name="see-also"></a>Viz také:

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Nastavit vlastnosti jedinečné automatizace pro ovládací prvky UWP](../test/set-a-unique-automation-property-for-windows-store-controls-for-testing.md)