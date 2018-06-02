---
title: Vytvoření programového testu UI v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 8f811905fb6fed0e0cbc061128622c72bf09fc07
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692324"
---
# <a name="walkthrough-create-edit-and-maintain-a-coded-ui-test"></a>Návod: Vytváření, úpravy a údržbu programového testu uživatelského rozhraní

V tomto návodu dozvíte, jak vytvořit, upravit a udržovat programové uživatelského rozhraní testu aplikace Windows Presentation Framework (WPF). Průvodce poskytuje řešení pro odstranění testy, které zrušili různé problémy načasování a refaktoring ovládacích prvků.

## <a name="create-a-wpf-app"></a>Vytvoření aplikace WPF

1.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom vyberte **projektu**.

     **Nový projekt** zobrazí se dialogové okno.

2.  V **nainstalovaná** podokně rozbalte **Visual C#** a potom vyberte **Windows Desktop**.

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

### <a name="run-the-wpf-app"></a>Spusťte aplikaci WPF

1.  Na **ladění** nabídce vyberte možnost **spustit ladění** nebo stiskněte klávesu **F5**.

2.  Všimněte si, že ovládací prvek zaškrtávací políčko je zakázán. Zvolte **spustit**.

     Během několika sekund by měl indikátor průběhu ukazovat 100 %.

3.  Teď si můžete vybrat ovládací prvek zaškrtávací políčko.

4.  Ukončete aplikaci SimpleWPFApp.

## <a name="create-a-shortcut-to-the-wpf-app"></a>Vytvoření zástupce aplikace WPF

1.  Vyhledejte SimpleWPFApp aplikaci, kterou jste vytvořili dříve.

2.  Vytvořte pro aplikaci SimpleWPFApp zástupce na ploše. Klikněte pravým tlačítkem na *SimpleWPFApp.exe* a zvolte **kopie**. Na ploše, klikněte pravým tlačítkem a zvolte **Vložit zástupce**.

    > [!TIP]
    > Zástupce aplikace usnadňuje přidat nebo upravit programové testy uživatelského rozhraní pro vaši aplikaci, protože vám umožňuje rychle začít aplikace.

## <a name="create-a-coded-ui-test-for-simplewpfapp"></a>Vytvoření programového testu UI pro SimpleWPFApp

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na řešení, zvolte **přidat** a pak vyberte **nový projekt**.

     **Přidat nový projekt** zobrazí se dialogové okno.

1. V **nainstalovaná** podokně rozbalte **Visual C#** a potom vyberte **Test**.

1. V prostředním podokně, vyberte **programového uživatelského rozhraní testovacího projektu** šablony.

   > [!NOTE]
   > Pokud nevidíte **programového projekt testování uživatelského rozhraní** šablony, budete muset [nainstalovat součást programového testu uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md#install-the-coded-ui-test-component).

1. Zvolte **OK**.

     Nový projekt testů uživatelského rozhraní s názvem programového **CodedUITestProject1** se přidá do vašeho řešení.

     **Generovat kód pro programového testu uživatelského rozhraní** zobrazí se dialogové okno.

1. Vyberte **záznam akcí, upravte mapování uživatelského rozhraní nebo přidání kontrolních výrazů** možnost a zvolte **OK**.

     **Zdroje UIMap - Tvůrce programového testu uživatelského rozhraní** otevře se dialogové okno a je minimalizovaná okna Visual Studio.

     Další informace o možnostech v dialogovém okně najdete v tématu [vytváření programových testů uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md).

1. Zvolte **záznam Start** na **zdroje UIMap - Tvůrce programového testu uživatelského rozhraní** dialogové okno.

     ![Spustit záznam](../test/media/cuit_builder_record.png)

     Je možné pozastavit záznamu v případě potřeby, například pokud budete muset řešit příchozí pošty.

     ![Pozastavení záznamu](../test/media/cuit_.png)

    > [!WARNING]
    > Všechny akce prováděné na ploše, bude zaznamenán. Pozastavení záznamu při provedení akce, které může vést k citlivá data nebudou zahrnuty do záznamu.

1. Spusťte SimpleWPFApp pomocí zástupce na ploše.

     Jako dříve Všimněte si, že ovládací prvek zaškrtávací políčko je zakázán.

1. Na SimpleWPFApp, zvolte **spustit**.

     Během několika sekund by měl indikátor průběhu ukazovat 100 %.

1. Zkontrolujte ovládací prvek zaškrtávací políčko, který je teď povolené.

1. Ukončete aplikaci SimpleWPFApp.

1. Na **zdroje UIMap - Tvůrce programového testu uživatelského rozhraní** dialogovém okně, vyberte **generovat kód**.

1. V **název metody** zadejte **SimpleAppTest** a zvolte **přidat a generovat**. Během pár sekund programového testu uživatelského rozhraní se zobrazí a přidají se do řešení.

1. Zavřít **zdroje UIMap - programového Tvůrce testu uživatelského rozhraní**.

     *CodedUITest1.cs* souboru se zobrazí v editoru kódu.

1. Uložte projekt.

### <a name="run-the-test"></a>Spuštění testu

1. Z **Test** nabídce zvolte **Windows** a potom zvolte **Průzkumníka testů**.

2. Z **sestavení** nabídce zvolte **sestavit řešení**.

3. V *CodedUITest1.cs* souboru, vyhledejte **CodedUITestMethod** metodu, klikněte pravým tlačítkem a vyberte **spuštění testů**, nebo spuštění testu z **testování Explorer**.

   V průběhu programového testu uživatelského rozhraní je zobrazena aplikace SimpleWPFApp. Provádí kroky, které jste učinili v předchozí proceduře. Ale když test se pokusí o zaškrtněte políčko pro ovládací prvek zaškrtávací políčko, **výsledky testu** ukazuje, že test se nezdařil. To je proto test pokusí zaškrtněte políčko ale neví o tom, že ovládací prvek zaškrtávací políčko je zakázána, dokud indikátor průběhu je 100 % dokončení. Můžete to vyřešit a podobné problémy s použitím různých `UITestControl.WaitForControlXXX()` metody, které jsou k dispozici pro programové testování uživatelského rozhraní. Následující postup popisuje, pomocí `WaitForControlEnabled()` metoda opravit problém, který tento test selhání. Další informace najdete v tématu [provedení programového uživatelského rozhraní testy počkejte pro konkrétní události při přehrávání](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).

## <a name="edit-and-rerun-the-coded-ui-test"></a>Upravit a znovu spusťte programového testu uživatelského rozhraní

1.  V **testování Explorer** okně vyberte neúspěšných testů a v **trasování zásobníku** zvolte první odkaz na **UIMap.SimpleAppTest()**.

2.  *UIMap.Designer.cs* soubor se otevře s bodem zvýrazněných v kód chyby:

    ```csharp
    // Select 'CheckBox' check box
    uICheckBoxCheckBox.Checked = this.SimpleAppTestParams.UICheckBoxCheckBoxChecked;
    ```

3.  Chcete-li tento problém, můžete provést programového testu UI čekat na ovládací prvek zaškrtávací políčko Povolit než budete pokračovat na tento řádek pomocí `WaitForControlEnabled()` metoda.

    > [!WARNING]
    > Nelze změnit *UIMap.Designer.cs* souboru. Všechny změny budou přepsány pokaždé, když generování kódu pomocí kódu **zdroje UIMap - Tvůrce programového testu uživatelského rozhraní**. Pokud máte zaznamenaná metodu, zkopírujte ho do *UIMap.cs* souborů a přejmenujte ji. *UIMap.cs* soubor lze použít k přepsání metody a vlastnosti v *UIMapDesigner.cs* souboru. Je nutné odebrat odkaz na původní metody v *CodedUITest.cs* a nahraďte název přejmenované metody.

4.  V **Průzkumníku řešení**, vyhledejte *UIMap.uitest* v projektu programových testů uživatelského rozhraní.

5.  Otevřete místní nabídku pro *UIMap.uitest* a zvolte **otevřete**.

     Programový test uživatelského rozhraní se zobrazí v Editoru programového testu uživatelského rozhraní. Nyní můžete zobrazit a upravit programový test uživatelského rozhraní.

6.  V **akci uživatelského rozhraní** podokně, vyberte metodu testu (SimpleAppTest), který chcete přesunout do *UIMap.cs* nebo *UIMap.vb* souboru. Přesunutí metody do jiného souboru umožňuje přidat vlastní kód, který nebude při znovu zkompiluje testovacího kódu přepsány.

7.  Vyberte **přesunout kódu** tlačítko **editoru programových testů UI** panelu nástrojů.

8.  Zobrazí se dialogové okno aplikace Microsoft Visual Studio. Ho vás varuje, že metoda budou přesunuty z *UIMap.uitest* do souboru *UIMap.cs* souboru a že již budete moci upravit metodu pomocí editoru programových testů uživatelského rozhraní. Zvolte **Ano**.

     Metoda test je odebrán z *UIMap.uitest* souboru a už se zobrazí v podokně akcí uživatelského rozhraní. Chcete-li přesunutý testovací soubor upravit, otevřete *UIMap.cs* souboru z **Průzkumníku řešení**.

9. Na panelu nástrojů Visual Studio zvolte **Uložit**.

     Aktualizace zkušební metody jsou uloženy ve *UIMap.Designer* souboru.

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

13. V *CodedUITest1.cs* souboru, vyhledejte **CodedUITestMethod** metoda a buď komentář nebo přejmenujte odkaz na původní metodou SimpleAppTest() a nahraďte ji metodou nové ModifiedSimpleAppTest():

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

16. Tentokrát programového testu UI úspěšně dokončí všechny kroky v testu a **předané** se zobrazí v **testování Explorer** okno.

## <a name="refactor-a-control-in-simplewpfapp"></a>Refaktorovat ovládacího prvku v SimpleWPFApp

1.  V *MainWindow.xaml* souboru v návrháři, vyberte ovládací prvek tlačítko.

2.  V horní části **vlastnosti** změňte **název** hodnota vlastnosti z **button1** k **buttonA**.

3.  Na **sestavení** nabídce zvolte **sestavit řešení**.

4.  V **Průzkumníka testů**spusťte **CodedUITestMethod1**.

     Test se nezdaří, protože programový test uživatelského rozhraní nemůže najít ovládací prvek Tlačítko, který byl původně namapován ve třídě UIMap jako Tlačítko1. Refaktoring může tímto způsobem ovlivnit programové testy uživatelského rozhraní.

5.  V **Průzkumníka testů**v **trasování zásobníku** zvolte první odkaz vedle položky **(UIMpa.ModifiedSimpleAppTest)**.

     *UIMap.cs* soubor otevře. Místo chyby bude v kódu zvýrazněno:

    ```csharp
    // Click 'Start' button
    Mouse.Click(uIStartButton, new Point(27, 10));
    ```

     Všimněte si, že používá řádek kódu dříve v tomto postupu `UiStartButton`, což je název zdroje UIMap předtím, než byla rozdělili.

     Chcete-li tento problém, můžete přidat refactored ovládací prvek do zdroje UIMap pomocí **Tvůrce programového testu uživatelského rozhraní**. Testu kódu pro použití kódu, můžete aktualizovat, jak je předvedeno v dalším postupu.

## <a name="map-refactored-control-rerun-the-test"></a>Mapování rozdělili řízení opětovné spuštění testu

1.  V *CodedUITest1.cs* v souboru **CodedUITestMethod1()** metoda, klikněte pravým tlačítkem, vyberte **generovat kód pro programového testu uživatelského rozhraní** a potom zvolte **použití Programový Tvůrce testu uživatelského rozhraní**.

     **Zdroje UIMap - Tvůrce programového testu uživatelského rozhraní** se zobrazí.

2.  Pomocí zástupce na ploše, které jste vytvořili dříve, spusťte aplikaci SimpleWPFApp, kterou jste vytvořili dříve.

3.  Na **zdroje UIMap - Tvůrce programového testu uživatelského rozhraní** dialogu přetažením záměrný kříž nástroje **spustit** na SimpleWPFApp tlačítko.

     **Spustit** tlačítko ohraničeno blue pole. **Programový Tvůrce testu uživatelského rozhraní** trvá několik sekund a zpracování dat pro vybraný ovládací prvek zobrazení vlastností ovládacího prvku. Všimněte si, že hodnota **AutomationUId** je **buttonA**.

4.  Ve vlastnostech ovládacího prvku vyberte šipku v levém horním rohu a rozbalte mapování ovládacího prvku uživatelského rozhraní. Všimněte si, že **UIStartButton1** je vybrána.

5.  Na panelu nástrojů vyberte **přidání ovládacího prvku na ovládací prvek mapy uživatelského rozhraní**.

     Stav v dolní části okna ověřuje akce zobrazením **vybrané řízení se přidal do mapy ovládacího prvku uživatelského rozhraní**.

6.  Na **zdroje UIMap - Tvůrce programového testu uživatelského rozhraní** dialogovém okně, vyberte **generovat kód**.

     **Programového Tvůrce testu uživatelského rozhraní – generovat kód** otevře se dialogové okno s poznámku označující, že se nevyžadují žádné nové metody, a tento kód se vygeneruje pouze změny se mapy ovládacího prvku uživatelského rozhraní.

7.  Zvolte **generovat**.

8.  Ukončete aplikaci SimpleWPFApp.

9. Zavřít **zdroje UIMap - programového Tvůrce testu uživatelského rozhraní**.

10. V **Průzkumníku řešení**, otevřete *UIMap.Designer.cs* souboru.

11. V souboru UIMap.Designer.cs vyhledejte **UIStartButton1** vlastnost. Upozornění `SearchProperties` je nastaven na `"buttonA"`:

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

12. V *UIMap.cs* soubor, přidejte konstruktor a zadat `SearchProperties` vlastnost `UIStartButton` vlastnost na používání `AutomationID` vlastnosti s hodnotou `"buttonA":`

    ```csharp
    public UIMap()
            {
                this.UIMainWindowWindow.UIStartButton.SearchProperties[WpfButton.PropertyNames.AutomationId] = "buttonA";
            }
    ```

13. Na **sestavení** nabídce zvolte **sestavit řešení**.

14. V **Průzkumníka testů**spusťte **CodedUITestMethod1**.

     Tentokrát programový test uživatelského rozhraní úspěšně dokončí všechny kroky v testu. V **výsledky testů** okně uvidíte stav **předané**.

## <a name="videos"></a>Videa

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Začínáme s testy programového uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230573)

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [údržbu a ladění programové testy uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230574)

![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [ruční kódování programové testy uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230575)

## <a name="faq"></a>Nejčastější dotazy

[Programové testy uživatelského rozhraní – nejčastější dotazy](https://social.msdn.microsoft.com/Forums/en-US/3a74dd2c-cef8-4923-abbf-7a91f489e6c4/faqs?forum=vsautotest)

## <a name="see-also"></a>Viz také:

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
- [Úpravy programových testů uživatelského rozhraní pomocí Editoru programových testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)
