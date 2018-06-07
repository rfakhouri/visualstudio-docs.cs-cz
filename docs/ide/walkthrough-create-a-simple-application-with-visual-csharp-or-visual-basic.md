---
title: 'Návod: Vytvoření jednoduché aplikace s C# nebo Visual Basic'
ms.date: 10/03/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: f84339c7-d617-4f56-bfcd-af2215c347ba
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3efb5315b3adb02f74b41d193a6b9173f38ec992
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749554"
---
# <a name="walkthrough-create-a-simple-application-with-c-or-visual-basic"></a>Návod: Vytvoření jednoduché aplikace s C# nebo Visual Basic

Provedením tohoto návodu budete seznámit se s řadu nástrojů, dialogová okna a návrhářů, které můžete použít při vývoji aplikací pomocí sady Visual Studio. Budete vytvořit jednoduchou aplikaci "Hello, World", návrh uživatelského rozhraní, přidejte kód a ladění chyb, zatímco informace o práci v integrované vývojové prostředí (IDE).

## <a name="configure-the-ide"></a>Nastavení integrovaného vývojového prostředí (IDE)

Při prvním spuštění sady Visual Studio, budete vyzváni k přihlášení. Tento krok je volitelný pro účely tohoto postupu. Dále se může zobrazit dialogové okno s dotazem, zvolte nastavení pro vývoj a barvu motivu. Ponechejte výchozí hodnoty a zvolte **spuštění sady Visual Studio**.

![Zvolte dialogové okno nastavení](../ide/media/exploreide-settings.png)

Po spuštění sady Visual Studio se zobrazí okna nástrojů, v nabídkách a panely nástrojů a místo na hlavní okno. Nástroje systému windows jsou ukotveno na levé a pravé straně okna aplikace s **Snadné spuštění**, panelu nabídek a standardním panelu nástrojů v horní části. V centru okna aplikace **– úvodní stránka**. Při načítání řešení nebo projekt, zobrazit v prostoru editory a návrhářů, kde **– úvodní stránka** je. Při vývoji aplikace, budete tráví většinu doby v této oblasti centrální.

![IDE s obecné nastavení](../ide/media/exploreide-idewithgeneralsettings.png)

## <a name="create-the-project"></a>Vytvoření projektu

Při vytváření aplikace v systému Visual Studio je třeba nejprve vytvořit projekt a řešení. V tomto příkladu vytvoříte projekt Windows Presentation Foundation (WPF).

1. Vytvořte nový projekt. Na panelu nabídek vyberte **soubor** > **nový** > **projektu**.

     ![Na panelu nabídek vyberte soubor, nový, projektu](../ide/media/exploreide-filenewproject.png)

1. V **nový projekt** dialogovém okně, vyberte **nainstalovaná** > **Visual C#** (nebo **jazyka Visual Basic**) >  **Windows Desktop** kategorie a potom vyberte **aplikace WPF (rozhraní .NET Framework)** šablony. Název projektu **HelloWPFApp**.

     ![Šablony aplikace WPF v dialogovém okně Nový projekt sady Visual Studio](../ide/media/exploreide-newprojectcsharp.png)

1. Vyberte **OK**.

Visual Studio vytvoří projekt HelloWPFApp a řešení, a **Průzkumníku řešení** ukazuje různé soubory. **WPF Designer** zobrazuje zobrazení návrhu a zobrazení XAML *MainWindow.xaml* v rozděleném zobrazení. Můžete Vysuňte rozdělovače a zobrazit více nebo méně buď zobrazení. Můžete zobrazit jenom vizuální zobrazení nebo pouze zobrazení XAML. (Další informace najdete v tématu [vývojáři aplikace WPF Designer pro Windows Forms](http://msdn.microsoft.com/47ad0909-e89b-4996-b4ac-874d929f94ca).) Následující položky se zobrazí v **Průzkumníku řešení**:

![Průzkumník řešení se soubory HelloWPFApp načíst](../ide/media/exploreide-hellowpfappfiles.png)

Poté, co jste projekt vytvořili, jej můžete upravit. Pomocí **vlastnosti** okno (v nalezen **zobrazení** nabídky), můžete zobrazit a změnit možnosti pro položky projektu, ovládací prvky a další položky v aplikaci.

### <a name="change-the-name-of-mainwindowxaml"></a>Změňte název MainWindow.xaml

Můžeme poskytnout MainWindow více určitý název.

1. V **Průzkumníku řešení**, vyberte *MainWindow.xaml*. Měli byste vidět **vlastnosti** okno, ale pokud nemáte, vyberte **zobrazení** nabídky a potom **vlastnosti – okno** položky.

1. Změna **název souboru** vlastnost `Greetings.xaml`.

     ![Vlastnosti – okno s názvem souboru zvýrazněná](../ide/media/exploreide-filenameinpropertieswindow.png)

     **Průzkumník řešení** ukazuje, že název souboru je nyní *Greetings.xaml*, a má teď název souboru vnořené kódu *Greetings.xaml.vb* nebo *Greetings.xaml.cs*. Tento soubor kód je vnořený pod *XAML* souboru uzel a zobrazit jsou úzce související se vzájemně k sobě.

## <a name="design-the-user-interface-ui"></a>Návrh uživatelského rozhraní (UI)

Přidáme tři typy ovládacích prvků do této aplikace: <xref:System.Windows.Controls.TextBlock> řídit, dva <xref:System.Windows.Controls.RadioButton> ovládací prvky a <xref:System.Windows.Controls.Button> ovládacího prvku.

### <a name="add-a-textblock-control"></a>Přidání ovládacího prvku TextBlock

1. Otevřete **sada nástrojů** okno a vybrat **zobrazení** nabídky a **sada nástrojů** položky.

2. V **sada nástrojů**, rozbalte **běžných ovládacích prvků WPF** uzlu zobrazíte TextBlock ovládacího prvku.

     ![Sada nástrojů pomocí ovládacího prvku TextBlock zvýrazněná](../ide/media/exploreide-textblocktoolbox.png)

3. Přidání ovládacího prvku TextBlock na návrhovou plochu výběrem **TextBlock** položku a přetáhněte ji do okna na návrhovou plochu. Center ovládacího prvku v horní části okna.

Okno aplikace by mělo vypadat jako na následujícím obrázku:

![TextBlock pozdrav ovládací prvek](../ide/media/exploreide-greetingswithtextblockonly.png)

Značka XAML by měla vypadat následovně:

```xaml
<TextBlock HorizontalAlignment="Center" TextWrapping="Wrap" VerticalAlignment="Center" RenderTransformOrigin="4.08,2.312" Margin="237,57,221,238"><Run Text="TextBlock"/><InlineUIContainer><TextBlock TextWrapping="Wrap" Text="TextBlock"/>
```

### <a name="customize-the-text-in-the-text-block"></a>Přizpůsobení textu v bloku textu

1. V zobrazení jazyka XAML vyhledejte kód pro TextBlock a změnit atribut Text:

   ```xaml
   Text="Select a message option and then choose the Display button."
   ```

2. Znovu center TextBlock v případě potřeby a uložte změny stisknutím **Ctrl**+**S** nebo pomocí **souboru** položku nabídky.

V dalším kroku přidáte dva [RadioButton](/dotnet/framework/wpf/controls/radiobutton) ovládacích prvků formuláře.

### <a name="add-radio-buttons"></a>Přidání přepínačů

1. V **sada nástrojů**, Najít **RadioButton** ovládacího prvku.

     ![Sada nástrojů okno s vybrané RadioButton – ovládací prvek](../ide/media/exploreide-radiobuttontoolbox.png)

2. Přidání dvou ovládacích prvků RadioButton na návrh surface výběrem **RadioButton** položku a přetáhněte ji do okna na návrhovou plochu. Přesunout tlačítka (tak, že je vyberete a pomocí klávesy se šipkami) tak, aby se zobrazí tlačítka vedle sebe v ovládacím prvku TextBlock.

     Okno aplikace by mělo vypadat takto:

     ![Formulář pozdrav textblock a dvě přepínací tlačítka](../ide/media/exploreide-greetingswithradiobuttons.png)

3. V **vlastnosti** okně levém RadioButton – ovládací prvek, změny **název** vlastnost (vlastnost v horní části **vlastnosti** okno) k `HelloButton`.

     ![RadioButton vlastnosti – okno](../ide/media/exploreide-buttonproperties.png)

4. V **vlastnosti** okna pro správné ovládací prvek přepínač, změny **název** vlastnost `GoodbyeButton`a potom uložte změny.

Nyní můžete zadat text k zobrazení u obou ovládacích prvků RadioButton. Následující postup aktualizace **obsahu** vlastnost pro ovládací prvek přepínač.

### <a name="add-display-text-for-each-radio-button"></a>Přidání zobrazení textu pro každý přepínač

1. Návrhové ploše otevřete místní nabídky pro HelloButton stisknutím kombinace kláves pravým tlačítkem myši na HelloButton, zvolte **upravit Text**a potom zadejte `Hello`.

2. Otevřete místní nabídku pro GoodbyeButton stisknutím kombinace kláves pravým tlačítkem myši na GoodbyeButton, zvolte **upravit Text**a potom zadejte `Goodbye`.

### <a name="set-a-radio-button-to-be-checked-by-default"></a>Nastavit přepínací tlačítko, které se ve výchozím nastavení zaškrtnuto.

V tomto kroku vytvoříme HelloButton ke kontrole ve výchozím nastavení tak, aby mezi dvěma přepínačů je vždycky vybraná.

V zobrazení jazyka XAML, vyhledejte kód pro HelloButton a přidat **IsChecked** atribut:

```xaml
IsChecked="True"
```

Je posledním elementu uživatelského rozhraní, který přidáte [tlačítko](/dotnet/framework/wpf/controls/button) ovládacího prvku.

### <a name="add-the-button-control"></a>Přidání ovládacího prvku tlačítko

1. V **sada nástrojů**, Najít **tlačítko** řízení a poté jej přidejte do návrhové plochy v rámci kontrol RadioButton přetažením do formuláře v zobrazení návrhu.

2. V zobrazení jazyka XAML, změňte hodnotu **obsahu** pro ovládací prvek tlačítko z `Content="Button"` k `Content="Display"`a potom uložte změny.

     Kód by měl podobat následujícímu příkladu:   `<Button Content="Display" HorizontalAlignment="Left" VerticalAlignment="Top" Width="75" Margin="215,204,0,0"/>`

     Okno aplikace by mělo vypadat jako na následujícím obrázku.

     ![Formulář pozdrav s popisky ovládacího prvku](../ide/media/exploreide-greetingswithconrollabels.png)

### <a name="add-code-to-the-display-button"></a>Přidejte kód pro tlačítko zobrazení

Při spuštění této aplikace, zobrazí se okno se zprávou po uživatel vybere přepínače a potom vybere **zobrazení** tlačítko. Objeví se jedno okno se zprávou pro Hello a druhé se zprávou pro Goodbye. Pokud chcete vytvořit toto chování, přidáte kód, který `Button_Click` událost v *Greetings.xaml.vb* nebo *Greetings.xaml.cs*.

1. Na návrhové ploše, poklikejte **zobrazení** tlačítko.

     *Greetings.XAML.vb* nebo *Greetings.xaml.cs* otevře, umístěte kurzor v `Button_Click` událostí.

    ```vb
    Private Sub Button_Click_1(sender As Object, e As RoutedEventArgs)

    End Sub
    ```

    ```csharp
    private void Button_Click_1(object sender, RoutedEventArgs e)
    {

    }
    ```

2. Zadejte následující kód:

    ```vb
    If HelloButton.IsChecked = True Then
        MessageBox.Show("Hello.")
    ElseIf GoodbyeButton.IsChecked = True Then
        MessageBox.Show("Goodbye.")
    End If
    ```

    ```csharp
    if (HelloButton.IsChecked == true)
    {
         MessageBox.Show("Hello.");
    }
    else if (GoodbyeButton.IsChecked == true)
    {
        MessageBox.Show("Goodbye.");
    }
    ```

3. Uložte aplikaci.

## <a name="debug-and-test-the-application"></a>Ladění a testování aplikace

Dále budete ladění aplikace vyhledejte chyby a otestovat obou polí zprávu zobrazovat správně. Následující pokyny vám pomohou s sestavení a spuštění ladicího programu, ale později můžou číst [sestavit aplikaci WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf) a [ladění WPF](../debugger/debugging-wpf.md) Další informace.

### <a name="find-and-fix-errors"></a>Vyhledání a oprava chyb

V tomto kroku naleznete chybu, která jsme způsobené dříve Změna názvu *MainWindow.xaml* souboru.

#### <a name="start-debugging-and-find-the-error"></a>Spuštění ladění a vyhledejte chyby

1. Spuštění ladicího programu výběrem **ladění**, pak **spustit ladění**.

     ![Spuštění ladění příkazu v nabídce ladění](../ide/media/exploreide-startdebugging.png)

     A **rozdělit režimu** se zobrazí v okně a **výstup** okno znamená, že došlo k výjimce IOException: Nelze najít prostředek 'mainwindow.xaml'.

2. Zastavení ladicího programu výběrem **ladění** > **Zastavte ladění**.

     ![Zastavte ladění příkazu v nabídce ladění](../ide/media/exploreide-stopdebugging.png)

Nemůžeme přejmenovat *MainWindow.xaml* k *Greetings.xaml* na začátku tohoto návodu, ale kód stále odkazuje na *MainWindow.xaml* jako počáteční identifikátor URI pro aplikaci , takže nelze spustit projekt.

#### <a name="specify-greetingsxaml-as-the-startup-uri"></a>Zadejte Greetings.xaml jako počáteční identifikátor URI

1. V **Průzkumníku řešení**, otevřete *App.xaml* souboru (v projektu C#) nebo *Application.xaml* souboru (v projektu jazyka Visual Basic).

2. Změna `StartupUri="MainWindow.xaml"` k `StartupUri="Greetings.xaml"`a potom uložte změny.

Ladicí program spustit znovu (stiskněte **F5**). Měli byste vidět **pozdrav** okno aplikace. Nyní zavřete okno aplikace a zastavte ladění.

### <a name="debug-with-breakpoints"></a>Ladění pomocí zarážek

Kód můžete testovat během ladění tak, že přidáte některé zarážky. Můžete přidat zarážky výběrem **ladění** > **Přepnout zarážku**, kliknutím na levém okraji editoru vedle řádek kódu, kde chcete zalomení nebo stisknutím  **F9**.

#### <a name="add-breakpoints"></a>Přidat zarážky

1. Otevřete *Greetings.xaml.vb* nebo *Greetings.xaml.cs*a vyberte následující řádek: `MessageBox.Show("Hello.")`

2. Přidejte zarážku z nabídky výběrem **ladění**, pak **Přepnout zarážku**.

     ![Přepnout zarážku – příkaz v nabídce ladění](../ide/media/exploreide-togglebreakpoint.png)

     Na levém okraji okna editoru se vedle řádku kódu zobrazí červený kruh.

3. Vyberte následující řádek: `MessageBox.Show("Goodbye.")`.

4. Stiskněte **F9** klíče přidat zarážky a potom stiskněte klávesu **F5** spustit ladění.

5. V **Přivítání** okně zvolte **Hello** přepínač a potom vyberte **zobrazení** tlačítko.

     Na řádku `MessageBox.Show("Hello.")` zvýrazněn žlutě. V dolní části rozhraní IDE, automobily, lokální a sledovat windows jsou ukotveny na levé straně a windows zásobníkem volání, zarážky, příkazu, Immediate a výstup se ukotven společně na pravé straně.

6. Na řádku nabídek zvolte **ladění** > **Krokovat s Vystoupením**.

     Obnoví spuštění aplikace a zobrazí se okno se zprávou slovem "Hello".

7. Vyberte **OK** tlačítka v okně se zprávou a tím ho zavřete.

8. V **pozdrav** okně zvolte **Shledanou** přepínač a potom vyberte **zobrazení** tlačítko.

     Na řádku `MessageBox.Show("Goodbye.")` zvýrazněn žlutě.

9. Vyberte **F5** klíče a pokračujte ladění. Jakmile se zobrazí okno se zprávou, vyberte **OK** tlačítka v okně se zprávou a tím ho zavřete.

10. Zavřete okno aplikace a zastavte ladění.

11. Na řádku nabídek zvolte **ladění** > **zakažte všechny zarážky**.

### <a name="build-a-release-version-of-the-application"></a>Sestavení verze pro vydání aplikace

Teď, když ověříte, že vše funguje, můžete připravit sestavení pro vydání aplikace.

1. V hlavní nabídce vyberte **sestavení** > **Vyčistit řešení** odstranit zprostředkující soubory a výstupní soubory, které byly vytvořeny během předchozí sestavení. Není to nutné, ale ho vyčistí výstupy ladění sestavení.

     ![Příkaz Vyčistit řešení v nabídce sestavení](../ide/media/exploreide-cleansolution.png)

2. Změnit konfiguraci sestavení HelloWPFApp z **ladění** k **verze** pomocí ovládacího prvku rozevíracího seznamu na panelu nástrojů (zobrazuje "Debug" aktuálně).

     ![Verze vybrané standardním panelu nástrojů](../ide/media/exploreide-releaseversion.png)

3. Sestavte řešení tak, že zvolíte **sestavení** > **sestavit řešení**.

     ![V nabídce sestavení sestavit řešení – příkaz](../ide/media/exploreide-buildsolution.png)

Blahopřejeme k dokončení tohoto návodu! Můžete najít *.exe* jste vytvořili v části adresáře řešení a projektu (*...\HelloWPFApp\HelloWPFApp\bin\Release*).

## <a name="see-also"></a>Viz také:

- [Co je nového ve Visual Studio 2017](../ide/whats-new-in-visual-studio.md)
- [Tipy pro vyšší produktivitu](../ide/productivity-tips-for-visual-studio.md)