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
ms.openlocfilehash: 343d8c35433fe7d6fb454de5183bcc6a914d2a5e
ms.sourcegitcommit: b2942b8aa93bf73747790a05b67908c0b0108afe
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788016"
---
# <a name="walkthrough-create-a-simple-application-with-c-or-visual-basic"></a>Návod: Vytvoření jednoduché aplikace s C# nebo Visual Basic

V tomto návodu se seznámíte s mnoha nástrojů, dialogových oknech a návrhářích, které můžete použít při vývoji aplikací pomocí sady Visual Studio. Budete vytvářet aplikace "Hello, World", návrh uživatelského rozhraní, přidat kód a ladit chyby, zatímco informace o práci v integrovaném vývojovém prostředí ([IDE](visual-studio-ide.md)).

## <a name="configure-the-ide"></a>Nastavení integrovaného vývojového prostředí (IDE)

Při prvním spuštění aplikace Visual Studio, zobrazí se výzva k přihlášení. Tento krok je volitelný, v tomto návodu. Dále se může zobrazit dialogové okno, které vás požádá o zvolení nastavení pro vývoj a barevný motiv. Ponechte výchozí nastavení a zvolte **spusťte Visual Studio**.

![Zvolte dialogové okno nastavení](../ide/media/exploreide-settings.png)

Po spuštění sady Visual Studio, zobrazí se vám okna nástrojů, nabídky a panely nástrojů a prostor hlavního okna. Okna nástrojů jsou ukotveny na levé a pravé straně okna aplikace s **Snadné spuštění**, nabídek a běžný panel nástrojů v horní části. Ve střední části okna aplikace se nachází **úvodní stránka**. Při načítání řešení nebo projektu, v prostoru zobrazí editory a návrháře kde **úvodní stránka** je. Při vývoji aplikace strávíte nejvíce času v této centrální oblasti.

![Integrované vývojové prostředí s obecné nastavení](../ide/media/exploreide-idewithgeneralsettings.png)

## <a name="create-the-project"></a>Vytvoření projektu

Při vytváření aplikace v systému Visual Studio je třeba nejprve vytvořit projekt a řešení. V tomto příkladu vytvoříte projekt Windows Presentation Foundation (WPF).

1. Vytvořte nový projekt. Na panelu nabídek vyberte **souboru** > **nový** > **projektu**.

     ![V panelu nabídky zvolte soubor, nový, projekt](../ide/media/exploreide-filenewproject.png)

1. V **nový projekt** dialogového okna, vyberte **nainstalováno** > **Visual C#** (nebo **jazyka Visual Basic**) >  **Windows Desktop** kategorie a pak vyberte **aplikace WPF (.NET Framework)** šablony. Pojmenujte projekt **HelloWPFApp**.

     ![Šablona aplikace WPF v dialogovém okně Nový projekt sady Visual Studio](../ide/media/exploreide-newprojectcsharp.png)

1. Vyberte **OK**.

   Visual Studio vytvoří projekt aplikace HelloWPFApp a řešení, a **Průzkumníka řešení** zobrazuje různé soubory. **Návrhář WPF** ukazuje návrhové a XAML zobrazení *souboru MainWindow.xaml* v rozděleném zobrazení. Můžete snímků rozdělovač, abyste viděli víc nebo míň buď zobrazení. Můžete zobrazit pouze vizuální zobrazení nebo pouze zobrazení XAML. Následující položky se zobrazí v **Průzkumníka řešení**:

   ![Průzkumník řešení se soubory HelloWPFApp načíst](../ide/media/exploreide-hellowpfappfiles.png)

   > [!NOTE]
   > Další informace o XAML (eXtensible Application Markup Language), najdete v článku [přehled XAML pro WPF](/dotnet/framework/wpf/advanced/xaml-overview-wpf) stránky.

Poté, co jste projekt vytvořili, jej můžete upravit. S použitím **vlastnosti** okna (v **zobrazení** nabídky), můžete zobrazit a změnit možnosti položek projektu, ovládacích prvků a dalších položek v aplikaci.

### <a name="change-the-name-of-mainwindowxaml"></a>Změna názvu souboru MainWindow.xaml

Pojďme hlavního okna MainWindow konkrétnější název.

1. V **Průzkumníka řešení**vyberte *souboru MainWindow.xaml*. By se měla zobrazit **vlastnosti** okna, ale pokud ne, zvolte **zobrazení** nabídky a pak **okno vlastností** položky.

1. Změnit **název_souboru** vlastnost `Greetings.xaml`.

     ![Okno vlastností se zvýrazněným názvem souboru](../ide/media/exploreide-filenameinpropertieswindow.png)

     **Průzkumník řešení** odhalí název souboru je nyní *Greetings.xaml*, a teď s názvem souboru s vnořeným kódem *souboru Greetings.xaml.vb* nebo *Greetings.xaml.cs*. Souboru s tímto kódem je vnořený *.xaml* uzel souboru zobrazíte úzce souvisejí k sobě navzájem.

## <a name="design-the-user-interface-ui"></a>Návrh uživatelského rozhraní (UI)

Do této aplikace přidáme tři typy ovládacích prvků: <xref:System.Windows.Controls.TextBlock> řídit, dva <xref:System.Windows.Controls.RadioButton> ovládací prvky a <xref:System.Windows.Controls.Button> ovládacího prvku.

### <a name="add-a-textblock-control"></a>Přidejte ovládací prvek TextBlock

1. Otevřít **nástrojů** okno výběrem **zobrazení** nabídky a **nástrojů** položky.

2. V **nástrojů**, rozbalte **běžných ovládacích prvků WPF** uzel zobrazíte ovládací prvek TextBlock.

     ![Panel nástrojů s zvýrazněný ovládací prvek TextBlock](../ide/media/exploreide-textblocktoolbox.png)

3. Přidat ovládací prvek TextBlock do návrhové plochy kliknutím **TextBlock** položky a jeho přetažením na okno na návrhové ploše. Vycentrujte v horní části okna.

Okno aplikace by mělo vypadat jako na následujícím obrázku:

![TextBlock – ovládací prvek na formuláři Greetings](../ide/media/exploreide-greetingswithtextblockonly.png)

Značka XAML by měl vypadat přibližně jako v následujícím příkladu:

```xaml
<TextBlock HorizontalAlignment="Center" TextWrapping="Wrap" VerticalAlignment="Center" RenderTransformOrigin="4.08,2.312" Margin="237,57,221,238"><Run Text="TextBlock"/><InlineUIContainer><TextBlock TextWrapping="Wrap" Text="TextBlock"/>
```

### <a name="customize-the-text-in-the-text-block"></a>Úprava textu v textovém bloku

1. V XAML zobrazení najděte značku pro TextBlock a změňte atributu Text:

   ```xaml
   Text="Select a message option and then choose the Display button."
   ```

2. Uložte změny stisknutím kombinace kláves a v případě potřeby znovu Center ovládacím prvku TextBlock **Ctrl**+**S** nebo pomocí **souboru** položky nabídky.

V dalším kroku přidejte dva [RadioButton](/dotnet/framework/wpf/controls/radiobutton) ovládací prvky do formuláře.

### <a name="add-radio-buttons"></a>Přidání tlačítek přepínače

1. V **nástrojů**, vyhledejte **RadioButton** ovládacího prvku.

     ![Okno nástrojů s vybraným ovládacím prvkem ovládacího prvku RadioButton](../ide/media/exploreide-radiobuttontoolbox.png)

2. Přidejte dva ovládací prvky RadioButton návrhu surface výběrem **RadioButton** položky a jeho přetažením na okno na návrhové ploše. Přesunutí tlačítka (tak, že je vyberete a pomocí šipkových kláves) tak, aby tlačítek se zobrazí vedle sebe pod ovládacím prvkem TextBlock.

     Okno aplikace by mělo vypadat takto:

     ![Ve formuláři Greetings textblock a dvě přepínači (RadioButtons)](../ide/media/exploreide-greetingswithradiobuttons.png)

3. V **vlastnosti** okně levém ovládacího prvku RadioButton přepište **název** vlastností (vlastnost v horní části **vlastnosti** okno) k `HelloButton`.

     ![Okno vlastností ovládacího prvku RadioButton](../ide/media/exploreide-buttonproperties.png)

4. V **vlastnosti** okno pravého ovládacího prvku RadioButton, změna **název** vlastnost `GoodbyeButton`a pak uložte provedené změny.

Nyní můžete zadat text k zobrazení u obou ovládacích prvků RadioButton. Následující postup aktualizuje **obsahu** vlastnost ovládacího prvku RadioButton.

### <a name="add-display-text-for-each-radio-button"></a>Zadat text k zobrazení u obou přepínačů

1. Na návrhové ploše otevřete místní nabídku pro HelloButton stisknutím klávesy pravým tlačítkem myši na HelloButton, zvolte **upravit Text**a pak zadejte `Hello`.

2. Otevřete místní nabídku pro GoodbyeButton stisknutím klávesy pravým tlačítkem myši na GoodbyeButton, zvolte **upravit Text**a pak zadejte `Goodbye`.

### <a name="set-a-radio-button-to-be-checked-by-default"></a>Přepínací tlačítko, které ve výchozím nastavení kontrolováno nastavení

V tomto kroku nastavíme HelloButton být vráceny ve výchozím nastavení se tak, aby jeden z obou přepínačů je vždycky vybraná.

V XAML zobrazení najděte značku pro HelloButton a přidat **IsChecked** atribut:

```xaml
IsChecked="True"
```

Je poslední prvek uživatelského rozhraní, které přidáte [tlačítko](/dotnet/framework/wpf/controls/button) ovládacího prvku.

### <a name="add-the-button-control"></a>Přidání ovládacího prvku tlačítko

1. V **nástrojů**, vyhledejte **tlačítko** ovládací prvek a jeho přetažením na formulář v nástrojích pro návrhové zobrazení ho přidat na návrhovou plochu pod ovládací prvky RadioButton.

2. V XAML zobrazení, změňte hodnotu **obsahu** ovládacího prvku tlačítko z `Content="Button"` k `Content="Display"`a následně změny uložte.

     Kód by měl vypadat podobně jako v následujícím příkladu:   `<Button Content="Display" HorizontalAlignment="Left" VerticalAlignment="Top" Width="75" Margin="215,204,0,0"/>`

     Okno aplikace by mělo vypadat jako na následujícím obrázku.

     ![Formulář Greetings s popisky ovládacích prvků](../ide/media/exploreide-greetingswithconrollabels.png)

### <a name="add-code-to-the-display-button"></a>Přidání kódu k tlačítku zobrazit

Po spuštění aplikace se zobrazí okno se zprávou poté, co uživatel zvolí přepínač a následně klikne **zobrazení** tlačítko. Objeví se jedno okno se zprávou pro Hello a druhé se zprávou pro Goodbye. Pokud chcete vytvořit toto chování, přidáte kód k `Button_Click` událost v *souboru Greetings.xaml.vb* nebo *Greetings.xaml.cs*.

1. Na návrhové ploše, poklikejte **zobrazení** tlačítko.

     *Souboru Greetings.XAML.vb* nebo *Greetings.xaml.cs* otevře s kurzorem `Button_Click` událostí.

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

Dále budeme ladit aplikaci, pro vyhledávání chyb a testování, že oba zprávami zobrazila správně. V následujících pokynech se dozvíte, jak sestavit a spustit ladicí program, ale později si může přečíst [sestavení aplikace WPF (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf) a [ladění WPF](../debugger/debugging-wpf.md) Další informace.

### <a name="find-and-fix-errors"></a>Vyhledání a oprava chyb

V tomto kroku zjistíte chybu, která jsme dříve způsobili změnou názvu *souboru MainWindow.xaml* souboru.

#### <a name="start-debugging-and-find-the-error"></a>Spustit ladění a vyhledání chyby

1. Spusťte ladicí program výběrem **ladění**, pak **spustit ladění**.

     ![V nabídce ladění spustit ladění – příkaz](../ide/media/exploreide-startdebugging.png)

     A **režim přerušení** okna se zobrazí a **výstup** okno znamená, že došlo k IOException: Nelze najít zdroj "mainwindow.xaml".

2. Zastavit ladicí program výběrem **ladění** > **Zastavit ladění**.

     ![V nabídce ladění Zastavit ladění – příkaz](../ide/media/exploreide-stopdebugging.png)

Jsme přejmenovali *souboru MainWindow.xaml* k *Greetings.xaml* na začátku tohoto návodu, ale kód stále odkazuje na *souboru MainWindow.xaml* jako spouštěcího identifikátoru URI pro aplikaci , takže projekt nemůže spustit.

#### <a name="specify-greetingsxaml-as-the-startup-uri"></a>Určení souboru Greetings.xaml jako spouštěcího identifikátoru URI

1. V **Průzkumníka řešení**, otevřete *App.xaml* souboru (v jazyce C# projekt) nebo *Application.xaml* souboru (v projektu jazyka Visual Basic).

2. Změna `StartupUri="MainWindow.xaml"` k `StartupUri="Greetings.xaml"`a následně změny uložte.

Znovu spusťte ladicí program (stiskněte **F5**). Měli byste vidět **Greetings** okna aplikace. Teď zavřete okno aplikace chcete zastavit ladění.

### <a name="debug-with-breakpoints"></a>Ladění se zarážkami

Během ladění přidáním zarážek lze otestovat kód. Zarážky lze přidat zvolením **ladění** > **Přepnout zarážku**, kliknutím do levého okraje editoru vedle řádku kódu, kde chcete, aby se zarážka objevila, nebo stisknutím klávesy  **F9**.

#### <a name="add-breakpoints"></a>Přidání zarážky

1. Otevřít *souboru Greetings.xaml.vb* nebo *Greetings.xaml.cs*a vyberte následující řádek: `MessageBox.Show("Hello.")`

2. Přidáte zarážku z nabídky vyberte **ladění**, pak **Přepnout zarážku**.

     ![Přepnout zarážku – příkaz v nabídce ladění](../ide/media/exploreide-togglebreakpoint.png)

     Na levém okraji okna editoru se vedle řádku kódu zobrazí červený kruh.

3. Vyberte následující řádek: `MessageBox.Show("Goodbye.")`.

4. Stisknutím klávesy **F9** klíče pro přidání zarážky a potom stiskněte klávesu **F5** pro spuštění ladění.

5. V **Greetings** okna, vyberte **Hello** přepínač a klikněte na tlačítko **zobrazení** tlačítko.

     Na řádku `MessageBox.Show("Hello.")` je zvýrazněn žlutě. V dolní části rozhraní IDE, automatické hodnoty, místní hodnoty a sledování systému windows jsou ukotveny na levé straně a okna zásobník volání, zarážky, příkaz, okamžité a výstup jsou ukotveny na pravé straně.

6. V panelu nabídky zvolte **ladění** > **Krokovat s Vystoupením**.

     Aplikace pokračuje v provádění a zobrazí se okno se zprávou obsahující slovo "Hello".

7. Zvolte **OK** tlačítko na okno zpráv zavřete ho.

8. V **Greetings** okna, vyberte **Goodbye** přepínač a klikněte na tlačítko **zobrazení** tlačítko.

     Na řádku `MessageBox.Show("Goodbye.")` je zvýrazněn žlutě.

9. Zvolte **F5** klíč pro pokračování v ladění. Když se objeví okno se zprávou, klikněte **OK** tlačítko na okno zpráv zavřete ho.

10. Zavřete okno aplikace chcete zastavit ladění.

11. V panelu nabídky zvolte **ladění** > **zakázat všechny zarážky**.

### <a name="build-a-release-version-of-the-application"></a>Sestavení verze pro vydání aplikace

Teď, když jste ověřili, že vše funguje, si můžete připravit sestavení pro vydání aplikace.

1. V hlavní nabídce vyberte **sestavení** > **Vyčistit řešení** k odstranění pomocných a výstupních souborů, které byly během předchozích sestavení vytvořeny. To není nezbytné, ale jeho vyčistí výstupy sestavení ladění.

     ![Příkaz Vyčistit řešení v nabídce sestavení](../ide/media/exploreide-cleansolution.png)

2. Změňte nastavení sestavení aplikace hellowpfapp z **ladění** k **vydání** pomocí ovládacího prvku rozevíracího seznamu na panelu nástrojů (stavu "Ladění" aktuálně).

     ![Standardní panel nástrojů s vybrané verze](../ide/media/exploreide-releaseversion.png)

3. Sestavte řešení výběrem **sestavení** > **sestavit řešení**.

     ![V nabídce sestavení sestavit řešení – příkaz](../ide/media/exploreide-buildsolution.png)

Blahopřejeme k dokončení tohoto návodu! Můžete najít *.exe* vytvořeným v adresáři řešení a projektu (*...\HelloWPFApp\HelloWPFApp\bin\Release*).

## <a name="see-also"></a>Viz také:

- [Co je nového v sadě Visual Studio 2017](../ide/whats-new-in-visual-studio.md)
- [Tipy pro vyšší produktivitu](../ide/productivity-tips-for-visual-studio.md)