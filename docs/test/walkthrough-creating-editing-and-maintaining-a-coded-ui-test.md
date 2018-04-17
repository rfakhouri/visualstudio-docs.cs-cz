---
title: Vytvoření programového testu UI v sadě Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1861915f50961bb3b07513d69d9799717694e1be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-editing-and-maintaining-a-coded-ui-test"></a>Návod: Vytváření, upravování a údržba programového testu UI

V tomto návodu vytvoříte jednoduchou aplikaci Windows Presentation Foundation (WPF) pro demonstraci vytvoření, úpravy a správy programového testu uživatelského rozhraní. Návod poskytuje řešení pro opravu testů, které byly poškozeny různými chybami časování a refaktoringem ovládacích prvků.

## <a name="create-a-simple-wpf-application"></a>Vytvoření jednoduché aplikace WPF

1.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** zobrazí se dialogové okno.

2.  V **nainstalovaná** podokně rozbalte **Visual C#**a potom vyberte **Windows Desktop**.

3.  Výše v prostředním podokně, ověřte, že cílový framework rozevíracího seznamu je nastavena na **rozhraní .NET Framework 4.5**.

4.  V prostředním podokně, vyberte **aplikaci WPF** šablony.

5.  V **název** textového pole, typ **SimpleWPFApp**.

6.  Zvolte složku, do které bude projekt uložen. V **umístění** textové pole, zadejte název složky.

7.  Zvolte **OK**.

     WPF Designer pro sadu Visual Studio otevře a zobrazí hlavní okno MainWindow projektu.

8.  Pokud není panel nástrojů otevřen, otevřete jej. Vyberte **zobrazení** nabídce a potom zvolte **sada nástrojů**.

9. V části **všech ovládacích prvků WPF** část, přetáhněte **tlačítko**, **zaškrtávací políčko** a **ProgressBar** na MainWindow v návrhu ovládací prvek prostor.

10. Vyberte ovládací prvek Tlačítko. V okně vlastností změňte hodnotu **název** vlastnost z \<ne Name > na button1. Pak změňte hodnotu **obsahu** vlastnost z tlačítko Start.

11. Vyberte ovládací prvek Indikátor průběhu. V okně vlastností změňte hodnotu **název** vlastnost z \<ne Name > k progressBar1. Pak změňte hodnotu **maximální** vlastnost z **100** k **10000**.

12. Vyberte ovládací prvek Zaškrtávací políčko. V okně vlastností změňte hodnotu **název** vlastnost z \<ne název > checkBox1 a clear **hodnotu IsEnabled** vlastnost.

     ![Aplikace WPF jednoduché](../test/media/codedui_wpfapp.png "CodedUI_WPFApp")

13. Dvakrát klikněte na ovládací prvek tlačítko pro přidání obslužnou rutinu události kliknutí.

     V editoru kódu se zobrazí MainWindow.xmal.cs s kurzorem v nové metodě button1_Click.

14. V horní části třídy hlavního okna MainWindow přidejte delegáta. Delegát bude použit pro indikátor průběhu. Chcete-li přidat delegáta, přidejte následující kód:

    ```csharp
    public partial class MainWindow : Window
    {
            private delegate void ProgressBarDelegate(System.Windows.DependencyProperty dp, Object value);

        public MainWindow()
        {

            InitializeComponent();
        }
    ```

15. V metodě button1_Click přidejte následující kód:

    ```csharp
    private void button1_Click(object sender, RoutedEventArgs e)
    {
        double progress = 0;

        ProgressBarDelegate updatePbDelegate =
            new ProgressBarDelegate(progressBar1.SetValue);

        do
        {
            progress ++;

            Dispatcher.Invoke(updatePbDelegate,
                System.Windows.Threading.DispatcherPriority.Background,
                new object[] { ProgressBar.ValueProperty, progress });
            progressBar1.Value = progress;
        }
        while (progressBar1.Value != progressBar1.Maximum);

        checkBox1.IsEnabled = true;
    }
    ```

16. Uložte soubor.

### <a name="verify-the-wpf-application-runs-correctly"></a>Ověření správného běhu aplikace WPF

1.  Na **ladění** nabídce vyberte možnost **spustit ladění** nebo stiskněte klávesu **F5**.

2.  Všimněte si, že ovládací prvek zaškrtávací políčko je zakázán. Zvolte **spustit**.

     Během několika sekund by měl indikátor průběhu ukazovat 100 %.

3.  Teď si můžete vybrat ovládací prvek zaškrtávací políčko.

4.  Ukončete aplikaci SimpleWPFApp.

### <a name="create-and-run-a-coded-ui-test-for-simplewpfapp"></a>Vytvoření a spuštění programového testu uživatelského rozhraní pro aplikaci SimpleWPFApp

1.  Vyhledejte SimpleWPFApp aplikaci, kterou jste vytvořili dříve. Ve výchozím nastavení, budou aplikace umístěné v C:\Users\\< uživatelské jméno\>\Documents\Visual Studio \<verze > \Projects\SimpleWPFApp\SimpleWPFApp\bin\Debug\SimpleWPFApp.exe

2.  Vytvořte pro aplikaci SimpleWPFApp zástupce na ploše. Klikněte pravým tlačítkem na SimpleWPFApp.exe a zvolte **kopie**. Na ploše, klikněte pravým tlačítkem a zvolte **Vložit zástupce**.

    > [!TIP]
    > Zástupce aplikace usnadňuje přidávání nebo úpravu programových testů uživatelského rozhraní pro vaši aplikaci, protože umožňuje rychlé spuštění aplikace.

3.  V Průzkumníku řešení klikněte pravým tlačítkem na řešení, zvolte **přidat** a pak vyberte **nový projekt**.

     **Přidat nový projekt** zobrazí se dialogové okno.

4.  V **nainstalovaná** podokně rozbalte **Visual C#**a potom vyberte **Test**.

5.  V prostředním podokně, vyberte **programového uživatelského rozhraní testovacího projektu** šablony.

6.  Zvolte **OK**.

     V Průzkumníku řešení nové programového uživatelského rozhraní testovacího projektu s názvem **CodedUITestProject1** se přidá do vašeho řešení.

     **Generovat kód pro programového testu uživatelského rozhraní** zobrazí se dialogové okno.

7.  Vyberte **záznam akcí, upravte mapování uživatelského rozhraní nebo přidání kontrolních výrazů** možnost a zvolte **OK**.

     Se zobrazí zdroje UIMap - Tvůrce programového testu uživatelského rozhraní a je minimalizován okně Visual Studio.

     Další informace o možnostech v dialogovém okně najdete v tématu [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md).

8.  Zvolte **spustit záznam** na zdroje UIMap - programového Tvůrce testu uživatelského rozhraní.

     ![Spusťte záznam](../test/media/cuit_builder_record.png "CUIT_Builder_Record")

     Je možné pozastavit záznamu v případě potřeby, například pokud budete muset řešit příchozí pošty.

     ![Pozastavení záznamu](../test/media/cuit_.png "CUIT_")

    > [!WARNING]
    > Všechny akce prováděné na ploše, bude zaznamenán. Pozastavení záznamu při provedení akce, které může vést k citlivá data nebudou zahrnuty do záznamu.

9. Spusťte SimpleWPFApp pomocí zástupce na ploše.

     Jako dříve Všimněte si, že ovládací prvek zaškrtávací políčko je zakázán.

10. Na SimpleWPFApp, zvolte **spustit**.

     Během několika sekund by měl indikátor průběhu ukazovat 100 %.

11. Zkontrolujte ovládací prvek zaškrtávací políčko, který je teď povolené.

12. Ukončete aplikaci SimpleWPFApp.

13. Na zdroje UIMap - Tvůrce programového testu uživatelského rozhraní, zvolte **generovat kód**.

14. V typu název metody **SimpleAppTest** a zvolte **přidat a generovat**. Během několika sekund se programový test uživatelského rozhraní zobrazí a přidá k řešení.

15. Zavřete zdroje UIMap - programového Tvůrce testu uživatelského rozhraní.

     V Editoru kódu se zobrazí soubor CodedUITest1.cs.

16. Uložte projekt.

### <a name="run-the-coded-ui-test"></a>Spuštění programového testu uživatelského rozhraní

1.  Z **Test** nabídce zvolte **Windows** a potom zvolte **Průzkumníka testů**.

2.  Z **sestavení** nabídce zvolte **sestavit řešení**.

3.  V souboru CodedUITest1.cs vyhledejte **CodedUITestMethod** metodu, klikněte pravým tlačítkem a vyberte **spuštění testů**, nebo spuštění testu z Průzkumníka testů.

     V průběhu programového testu uživatelského rozhraní je zobrazena aplikace SimpleWPFApp. Provádí kroky, které jste učinili v předchozí proceduře. Ale pokud test se pokusí zaškrtněte políčko pro ovládací prvek zaškrtávací políčko, okno výsledky testu zobrazuje, test se nezdařilo. To je proto test pokusí zaškrtněte políčko ale neví o tom, že ovládací prvek zaškrtávací políčko je zakázána, dokud indikátor průběhu je 100 % dokončení. Můžete to vyřešit a podobné problémy s použitím různých `UITestControl.WaitForControlXXX()` metody, které jsou k dispozici pro programové testování uživatelského rozhraní. Následující postup popisuje, pomocí `WaitForControlEnabled()` metoda opravit problém, který tento test selhání. Další informace najdete v tématu [provedení programového uživatelského rozhraní testy počkejte pro konkrétní události při přehrávání](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).

### <a name="edit-and-rerun-the-coded-ui-test"></a>Úprava a opětovné spuštění programového testu uživatelského rozhraní

1.  V okně Průzkumníka testů vyberte neúspěšných testů a **trasování zásobníku** zvolte první odkaz na **UIMap.SimpleAppTest()**.

2.  Otevře se soubor UIMap.Designer.cs se zvýrazněným chybovým místem v kódu:

    ```csharp
    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

3.  Chcete-li tento problém, můžete provést programového testu UI čekat na ovládací prvek zaškrtávací políčko Povolit než budete pokračovat na tento řádek pomocí `WaitForControlEnabled()` metoda.

    > [!WARNING]
    > Neupravujte soubor UIMap.Designer.cs. Jakékoli změny kódu v souboru UIMapDesigner.cs budou při každém vytvoření kódu pomocí nástroje UIMap – Tvůrce programového testu UI přepsány. Pokud je třeba změnit zaznamenanou metodu, musíte ji zkopírovat do souboru UIMap.cs a přejmenovat ji. Soubor UIMap.cs lze použít k přepsání metod a vlastností v souboru UIMapDesigner.cs. Je třeba odebrat odkaz na původní metodu v kódovaném souboru UITest.cs a nahradit ji názvem přejmenované metody.

4.  V Průzkumníku řešení, vyhledejte **UIMap.uitest** v projektu programových testů uživatelského rozhraní.

5.  Otevřete místní nabídku pro **UIMap.uitest** a zvolte **otevřete**.

     Programový test uživatelského rozhraní se zobrazí v Editoru programového testu uživatelského rozhraní. Nyní můžete zobrazit a upravit programový test uživatelského rozhraní.

6.  V **akci uživatelského rozhraní** podokně, vyberte znovu zkompiluje metodu testu (SimpleAppTest), které chcete přesunout do souboru UIMap.cs nebo UIMap.vb usnadňuje funkce vlastní kód, který nebude přepsána při testovacího kódu.

7.  Vyberte **přesunout kód** tlačítka na panelu nástrojů editoru programových testů UI.

8.  Zobrazí se dialogové okno aplikace Microsoft Visual Studio. Upozorňuje vás, že metoda bude přesunuta ze souboru UIMap.uitest do souboru UIMap.cs a že již nebude možné upravit metodu pomocí funkce Editor programového testu uživatelského rozhraní. Zvolte **Ano**.

     Testovací metoda je odebrána ze souboru UIMap.uitest a v podokně Akce uživatelského rozhraní se již nezobrazí. Chcete-li upravit přesunutý soubor testu, otevřete soubor UIMap.cs z Průzkumníku řešení.

9. Na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojů vyberte **Uložit**.

     Aktualizace testovací metody jsou uloženy do souboru UIMap.Designer.

    > [!WARNING]
    > Po přesunutí metody ji nemůžete nadále upravovat pomocí Editoru programového testu uživatelského rozhraní. Musíte přidat vlastní kód a spravovat jej pomocí Editoru kódu.

10. Přejmenujte metodu z `SimpleAppTest()` na `ModifiedSimpleAppTest()`

11. Přidejte do souboru následující příkaz Using:

    ```csharp
    using Microsoft.VisualStudio.TestTools.UITesting.WpfControls;
    ```

12. Přidejte následující `WaitForControlEnabled()` metoda před problematické řádek kódu identifikuje dříve:

    ```csharp
    uICheckBoxCheckBox.WaitForControlEnabled();

    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

13. V souboru CodedUITest1.cs vyhledejte **CodedUITestMethod** metoda a buď komentář nebo přejmenujte odkaz na původní metodou SimpleAppTest() a nahraďte ji metodou nové ModifiedSimpleAppTest():

    ```csharp
    [TestMethod]
            public void CodedUITestMethod1()
            {
                // To generate code for this test, select "Generate Code for Coded UI Test" from the shortcut menu and select one of the menu items.
                // For more information on generated code, see http://go.microsoft.com/fwlink/?LinkId=179463
                //this.UIMap.SimpleAppTest();
                this.UIMap.ModifiedSimpleAppTest();
            }
    ```

14. Na **sestavení** nabídce zvolte **sestavit řešení**.

15. Klikněte pravým tlačítkem myši **CodedUITestMethod** metoda a vyberte **spuštění testů**.

16. Tentokrát programového testu UI úspěšném dokončení všech kroků v testu a **předané** se zobrazí v okně Průzkumníka testů.

### <a name="refactor-a-control-in-the-simplewpfapp"></a>Refaktorování ovládacího prvku v aplikaci SimpleWPFApp

1.  V souboru MainWindow.xaml v položce Návrhář vyberte ovládací prvek Tlačítko.

2.  V horní části okna vlastností, změnit **název** hodnotu vlastnosti z button1 buttonA.

3.  Na **sestavení** nabídce zvolte **sestavit řešení**.

4.  Spusťte Průzkumníka testů **CodedUITestMethod1**.

     Test se nezdaří, protože programový test uživatelského rozhraní nemůže najít ovládací prvek Tlačítko, který byl původně namapován ve třídě UIMap jako Tlačítko1. Refaktoring může tímto způsobem ovlivnit programové testy uživatelského rozhraní.

5.  V okně Průzkumníka testů v **trasování zásobníku** zvolte první odkaz vedle položky **(UIMpa.ModifiedSimpleAppTest)**.

     Otevře se soubor UIMap.cs. Místo chyby bude v kódu zvýrazněno:

    ```csharp
    // Click 'Start' button
    Mouse.Click(uIStartButton, new Point(27, 10));
    ```

     Všimněte si, že používá řádek kódu dříve v tomto postupu `UiStartButton`, což je název zdroje UIMap předtím, než byla rozdělili.

     Chcete-li tento problém vyřešit, můžete pomocí položky Tvůrce programového testu UI přidat refaktorovaný ovládací prvek do třídy UIMap. Testu kódu pro použití kódu, můžete aktualizovat, jak je předvedeno v dalším postupu.

### <a name="map-refactored-control-and-edit-and-rerun-the-coded-ui-test"></a>Mapování refaktorovaného ovládacího prvku a úprava a opětovné spuštění programového testu uživatelského rozhraní

1.  V souboru CodedUITest1.cs v **CodedUITestMethod1()** metoda, klikněte pravým tlačítkem, vyberte **generovat kód pro programového testu uživatelského rozhraní** a potom zvolte **Tvůrce testu programového uživatelského rozhraní použijte**.

     Zdroje UIMap - Tvůrce programového testu uživatelského rozhraní se zobrazí.

2.  Pomocí zástupce na ploše, které jste vytvořili dříve, spusťte aplikaci SimpleWPFApp, kterou jste vytvořili dříve.

3.  Na zdroje UIMap - Tvůrce programového testu uživatelského rozhraní, přetáhněte nástroj záměrný kříž, který **spustit** na SimpleWPFApp tlačítko.

     **Spustit** tlačítko ohraničeno blue pole a Tvůrce programového testu uživatelského rozhraní trvá několik sekund, zpracování dat pro vybraný ovládací prvek a zobrazí vlastnosti ovládacích prvků. Všimněte si, že **AutomationUId** jmenuje **buttonA**.

4.  Ve vlastnostech ovládacího prvku vyberte šipku v levém horním rohu a rozbalte mapování ovládacího prvku uživatelského rozhraní. Všimněte si, že **UIStartButton1** je vybrána.

5.  Na panelu nástrojů vyberte **přidání ovládacího prvku na ovládací prvek mapy uživatelského rozhraní**.

     Stav v dolní části okna ověřuje akce zobrazením **vybrané řízení se přidal do mapy ovládacího prvku uživatelského rozhraní**.

6.  Na zdroje UIMap - Tvůrce programového testu uživatelského rozhraní, zvolte **generovat kód**.

     Tvůrce programový Test uživatelského rozhraní – generování kódu se zobrazí s poznámku označující, že není vyžadováno žádné nové metody a že kódu se budou generovat pouze změny se mapy ovládacího prvku uživatelského rozhraní.

7.  Zvolte **generovat**.

8.  Ukončete aplikaci SimpleWPFApp.exe.

9. Zavřete zdroje UIMap - Tvůrce testu programové uživatelského rozhraní.

     Zdroje UIMap - Tvůrce programového testu uživatelského rozhraní trvá několik sekund, proces kontrolní mechanismus uživatelského rozhraní mapovat změny.

10. V Průzkumníku řešení otevřete soubor UIMap.Designer.cs.

11. V souboru UIMap.Designer.cs najděte vlastnost UIStartButton1. Upozornění `SearchProperties` je nastaven na `"buttonA"`:

    ```csharp
    public WpfButton UIStartButton1
            {
                get
                {
                    if ((this.mUIStartButton1 == null))
                    {
                        this.mUIStartButton1 = new WpfButton(this);
                        #region Search Criteria
                        this.mUIStartButton1.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
                        this.mUIStartButton1.WindowTitles.Add("MainWindow");
                        #endregion
                    }
                    return this.mUIStartButton1;
                }
            }
    ```

     Nyní můžete upravit programový test uživatelského rozhraní tak, aby používal nově namapovaný ovládací prvek. Jak bylo uvedeno v předchozím postupu, pokud chcete přepsat jakékoliv metody nebo vlastnosti v programovém testu uživatelského rozhraní, musíte tak učinit v souboru UIMap.cs.

12. V souboru UIMap.cs přidejte konstruktor a zadejte `SearchProperties` vlastnost `UIStartButton` vlastnost na používání `AutomationID` vlastnosti s hodnotou `"buttonA":`

    ```csharp
    public UIMap()
            {
                this.UIMainWindowWindow.UIStartButton.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
            }
    ```

13. Na **sestavení** nabídce zvolte **sestavit řešení**.

14. V Průzkumníku Test spusťte CodedUITestMethod1.

     Tentokrát programový test uživatelského rozhraní úspěšně dokončí všechny kroky v testu.  V okně výsledky testů se zobrazí stav **předané**.

## <a name="external-resources"></a>Externí zdroje

### <a name="videos"></a>Videa

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Začínáme s testy programového uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230573)

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [údržbu a ladění programové testy uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230574)

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [ruční kódování programové testy uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230575)

### <a name="faq"></a>Nejčastější dotazy

[Programové testy uživatelského rozhraní – nejčastější dotazy](https://social.msdn.microsoft.com/Forums/en-US/3a74dd2c-cef8-4923-abbf-7a91f489e6c4/faqs?forum=vsautotest)

## <a name="see-also"></a>Viz také

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Úpravy programových testů uživatelského rozhraní pomocí Editoru programových testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)
