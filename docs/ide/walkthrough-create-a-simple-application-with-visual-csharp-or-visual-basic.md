---
title: "Návod: Vytvoření jednoduché aplikace s C# nebo Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 10/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
- CSharp
ms.assetid: f84339c7-d617-4f56-bfcd-af2215c347ba
caps.latest.revision: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: b33816e074cf63826c931bcda0978ebdb5bb8bbe
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="walkthrough-create-a-simple-application-with-c-or-visual-basic"></a>Návod: Vytvoření jednoduché aplikace s C# nebo Visual Basic
Provedením tohoto návodu budete seznámit se s řadu nástrojů, dialogová okna a návrhářů, které můžete použít při vývoji aplikací pomocí sady Visual Studio. Budete vytvořit jednoduchou aplikaci "Hello, World", návrh uživatelského rozhraní, přidejte kód a ladění chyb, zatímco informace o práci v integrované vývojové prostředí (IDE).
  
##  <a name="BKMK_ConfigureIDE"></a>Konfigurace prostředí IDE  
Při prvním spuštění sady Visual Studio, budete vyzváni k přihlášení. Tento krok je volitelný pro účely tohoto postupu. Dále se může zobrazit dialogové okno s dotazem, zvolte nastavení pro vývoj a barvu motivu. Ponechejte výchozí hodnoty a zvolte **spuštění sady Visual Studio**.  

![Zvolte dialogové okno nastavení](../ide/media/exploreide-settings.png "exploreide – nastavení")
  
Po spuštění sady Visual Studio se zobrazí okna nástrojů, v nabídkách a panely nástrojů a místo na hlavní okno. Nástroje systému windows jsou ukotveno na levé a pravé straně okna aplikace s **Snadné spuštění**, panelu nabídek a standardním panelu nástrojů v horní části. V centru okna aplikace **– úvodní stránka**. Při načítání řešení nebo projekt, zobrazit v prostoru editory a návrhářů, kde **– úvodní stránka** je. Při vývoji aplikace, budete tráví většinu doby v této oblasti centrální.  
  
![IDE s použitými nastaveními Obecné](../ide/media/exploreide-idewithgeneralsettings.png "ExploreIDE IDEwithgeneralsettings")  
  
##  <a name="BKMK_CreateApp"></a>Vytvoření jednoduché aplikace  
  
### <a name="create-the-project"></a>Vytvoření projektu  
Při vytváření aplikace v systému Visual Studio je třeba nejprve vytvořit projekt a řešení. V tomto příkladu vytvoříte projekt Windows Presentation Foundation (WPF).  
  
#### <a name="to-create-the-wpf-project"></a>Vytvoření projektu WPF  
  
1.  Vytvořte nový projekt. Na řádku nabídek zvolte **soubor**, **nový**, **projektu...** .  
  
     ![V řádku nabídek zvolte soubor, nový, projektu](../ide/media/exploreide-filenewproject.png "ExploreIDE FileNewProject")  
  
2.  Vyberte šablonu aplikace WPF Visual C# nebo Visual Basicu výběrem v levém podokně **nainstalovaná**, **Visual C#**, **Windows Classic Desktop**, třeba, a pak vyberete **Aplikace WPF (rozhraní .NET Framework)** v prostředním podokně.  Název projektu HelloWPFApp v dolní části dialogového okna Nový projekt.  
  
     ![Vytvoření projektu jazyka C# WPF, HelloWPFApp](../ide/media/exploreide-newprojectcsharp.png "ExploreIDE NewProjectcsharp")  
  
Visual Studio vytvoří projekt HelloWPFApp a řešení, a **Průzkumníku řešení** ukazuje různé soubory. Návrhář WPF ukazuje v rozděleném zobrazení návrhové a XAML zobrazení souboru MainWindow.xaml. Můžete Vysuňte rozdělovače a zobrazit více nebo méně buď zobrazení.  Můžete zobrazit jenom vizuální zobrazení nebo pouze zobrazení XAML. (Další informace najdete v tématu [WPF Designer pro Windows Forms vývojáři](http://msdn.microsoft.com/47ad0909-e89b-4996-b4ac-874d929f94ca).) Následující položky se zobrazí v **Průzkumníku řešení**:  
  
![Průzkumník řešení se soubory HelloWPFApp načíst](../ide/media/exploreide-hellowpfappfiles.png "ExploreIDE HelloWPFAppFiles")  
  
Poté, co jste projekt vytvořili, jej můžete upravit. Pomocí **vlastnosti** okno (v nalezen **zobrazení** nabídky), můžete zobrazit a změnit možnosti pro položky projektu, ovládací prvky a další položky v aplikaci.  
  
#### <a name="to-change-the-name-of-mainwindowxaml"></a>Změna názvu souboru MainWindow.xaml  
Můžeme poskytnout MainWindow více určitý název.  

1. V **Průzkumníku**, vyberte MainWindow.xaml. Měli byste vidět **vlastnosti** okno, ale pokud nemáte, vyberte **zobrazení** nabídky a potom **vlastnosti – okno** položky.  
2. Změna **název souboru** vlastnost `Greetings.xaml`.  
  
     ![Vlastnosti – okno s názvem souboru zvýrazněná](../ide/media/exploreide-filenameinpropertieswindow.png "ExploreIDE FilenameinPropertiesWindow")  
  
     **Průzkumník řešení** ukazuje, že název souboru je nyní Greetings.xaml a Greetings.xaml.vb nebo Greetings.xaml.cs má teď název souboru vnořené kódu. Tento soubor kód je vnořený pod uzlem souboru XAML zobrazit, že jsou úzce související se vzájemně k sobě.  
  
### <a name="design-the-user-interface-ui"></a>Návrh uživatelského rozhraní (UI)  
Nyní do této aplikace přidáme tři typy ovládacích prvků: ovládací prvek TextBlock, dva ovládací prvky RadioButton a ovládací prvek Button.  
  
#### <a name="to-add-a-textblock-control"></a>Přidání ovládacího prvku TextBlock  
  
1.  Otevřete **sada nástrojů** okno a vybrat **zobrazení** nabídky a **sada nástrojů** položky.  
  
2.  V **sada nástrojů**, rozbalte **běžných ovládacích prvků WPF** uzlu zobrazíte TextBlock ovládacího prvku.  
  
     ![Sada nástrojů pomocí ovládacího prvku TextBlock zvýrazněná](../ide/media/exploreide-textblocktoolbox.png "ExploreIDE TextBlockToolbox")  
  
3.  Přidání ovládacího prvku TextBlock na návrhovou plochu výběrem **TextBlock** položku a přetáhněte ji do okna na návrhovou plochu. Center ovládacího prvku v horní části okna.  
  
Okno aplikace by mělo vypadat jako na následujícím obrázku:  
  
![TextBlock ovládacího prvku formuláře pozdrav](../ide/media/exploreide-greetingswithtextblockonly.png "ExploreIDE GreetingswithTextblockonly")  
  
Značka XAML by měla vypadat následovně:  
  
```xaml  
<TextBlock HorizontalAlignment="Center" TextWrapping="Wrap" VerticalAlignment="Center" RenderTransformOrigin="4.08,2.312" Margin="237,57,221,238"><Run Text="TextBlock"/><InlineUIContainer><TextBlock TextWrapping="Wrap" Text="TextBlock"/>  
```  

#### <a name="to-customize-the-text-in-the-text-block"></a>Úprava textu v textovém bloku  
  
1.  V zobrazení jazyka XAML vyhledejte kód pro TextBlock a změnit atribut Text:  

   ```xaml
   Text="Select a message option and then choose the Display button."
   ```  
  
2.  Znovu center TextBlock v případě potřeby a uložte změny stisknutím **Ctrl-s** nebo pomocí **souboru** položku nabídky.  
  
V dalším kroku přidáte dva [RadioButton](/dotnet/framework/wpf/controls/radiobutton) ovládacích prvků formuláře.  
  
#### <a name="to-add-radio-buttons"></a>Přidání přepínačů  
  
1.  V **sada nástrojů**, Najít **RadioButton** ovládacího prvku.  
  
     ![Sada nástrojů okno s RadioButton – ovládací prvek vybrán](../ide/media/exploreide-radiobuttontoolbox.png "ExploreIDE RadioButtonToolbox")  
  
2.  Přidání dvou ovládacích prvků RadioButton na návrh surface výběrem **RadioButton** položku a přetáhněte ji do okna na návrhovou plochu. Přesunout tlačítka (tak, že je vyberete a pomocí klávesy se šipkami) tak, aby se zobrazí tlačítka vedle sebe v ovládacím prvku TextBlock.  
  
     Okno aplikace by mělo vypadat takto:  
  
     ![Pozdrav formuláři s textblock a dvě přepínací tlačítka](../ide/media/exploreide-greetingswithradiobuttons.png "ExploreIDE Greetingswithradiobuttons")  
  
3.  V **vlastnosti** okně levém RadioButton – ovládací prvek, změny **název** vlastnost (vlastnost v horní části **vlastnosti** okno) k  **HelloButton**.  

     ![RadioButton vlastnosti – okno](../ide/media/exploreide-buttonproperties.png "exploreide buttonproperties")  
  
4.  V **vlastnosti** okna pro správné ovládací prvek přepínač, změny **název** vlastnost **GoodbyeButton**a potom uložte změny.  
  
Nyní můžete zadat text k zobrazení u obou ovládacích prvků RadioButton. Následující postup aktualizace **obsahu** vlastnost pro ovládací prvek přepínač.  
  
#### <a name="to-add-display-text-for-each-radio-button"></a>Přidání textu k zobrazení u obou přepínačů  
  
1.  Návrhové ploše otevřete místní nabídky pro HelloButton stisknutím kombinace kláves pravým tlačítkem myši na HelloButton, zvolte **upravit Text**a pak zadejte text "Hello".  
  
2.  Otevřete místní nabídku pro GoodbyeButton stisknutím kombinace kláves pravým tlačítkem myši na GoodbyeButton, zvolte **upravit Text**a pak zadejte "Goodbye".  

### <a name="to-set-a-radio-button-to-be-checked-by-default"></a>Chcete-li nastavit přepínací tlačítko, které se ve výchozím nastavení zaškrtnuto.  
V tomto kroku vytvoříme HelloButton ke kontrole ve výchozím nastavení tak, aby mezi dvěma přepínačů je vždycky vybraná.  

V zobrazení jazyka XAML, vyhledejte kód pro HelloButton a přidat **IsChecked** atribut:

```xaml
IsChecked="True"
```  

Je posledním elementu uživatelského rozhraní, který přidáte [tlačítko](/dotnet/framework/wpf/controls/button) ovládacího prvku.  
  
#### <a name="to-add-the-button-control"></a>Přidání ovládacího prvku tlačítka  
  
1.  V **sada nástrojů**, Najít **tlačítko** řízení a poté jej přidejte do návrhové plochy v rámci kontrol RadioButton přetažením do formuláře v zobrazení návrhu.  
  
2.  V zobrazení jazyka XAML, změňte hodnotu **obsahu** pro ovládací prvek tlačítko z `Content="Button"` k `Content="Display"`a potom uložte změny.  
  
     Kód by měl podobat následujícímu příkladu:  
     `<Button Content="Display" HorizontalAlignment="Left" VerticalAlignment="Top" Width="75" Margin="215,204,0,0"/>`  
  
     Okno aplikace by mělo vypadat jako na následujícím obrázku.  
  
     ![Pozdrav formuláři s popisky ovládacího prvku](../ide/media/exploreide-greetingswithconrollabels.png "ExploreIDE Greetingswithconrollabels")  
  
### <a name="add-code-to-the-display-button"></a>Přidání kódu k tlačítku Zobrazit  
Při spuštění této aplikace, zobrazí se okno se zprávou po uživatel vybere přepínače a potom vybere **zobrazení** tlačítko. Objeví se jedno okno se zprávou pro Hello a druhé se zprávou pro Goodbye. Pokud chcete vytvořit toto chování, přidáte kód pro událost Button_Click v Greetings.xaml.vb nebo Greetings.xaml.cs.  
  
#### <a name="add-code-to-display-message-boxes"></a>Přidání kódu pro zobrazení oken se zprávami    
1.  Na návrhové ploše, poklikejte **zobrazení** tlačítko.  
  
     Otevře se okno s obsahem souboru Greetings.xaml.vb, případně Greetings.xaml.cs, s kurzorem umístěným v události Button_Click. 
  
    ```vb  
    Private Sub Button_Click_1(sender As Object, e As RoutedEventArgs)  
  
    End Sub  
    ```    
    ```csharp  
    private void Button_Click_1(object sender, RoutedEventArgs e)  
    {  
  
    }  
    ```  
  
2.  Zadejte následující kód:  
  
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
  
3.  Uložte aplikaci.  
  
##  <a name="BKMK_DebugTest"></a>Ladění a testování aplikace  
Dále budete ladění aplikace vyhledejte chyby a otestovat obou polí zprávu zobrazovat správně. Následující pokyny vám pomohou s sestavení a spuštění ladicího programu, ale později můžou číst [vytváření grafického subsystému WPF aplikace (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf) a [ladění WPF](../debugger/debugging-wpf.md) Další informace.  
  
### <a name="find-and-fix-errors"></a>Vyhledání a oprava chyb  
V tomto kroku budete Najít chybu, která jsme způsobené dříve změnou názvu souboru MainWindow.xaml.  
  
#### <a name="to-start-debugging-and-find-the-error"></a>Spuštění ladění a vyhledání chyby  
  
1.  Spuštění ladicího programu výběrem **ladění**, pak **spustit ladění**.  
  
     ![Spuštění ladění příkazu v nabídce ladění](../ide/media/exploreide-startdebugging.png "ExploreIDE StartDebugging")  
  
     A **rozdělit režimu** se zobrazí v okně a **výstup** okno znamená, že došlo k výjimce IOException: Nelze najít prostředek 'mainwindow.xaml'.  
  
2.  Zastavení ladicího programu výběrem **ladění**, **Zastavte ladění**.  
  
     ![Zastavte ladění příkazu v nabídce ladění](../ide/media/exploreide-stopdebugging.png "ExploreIDE StopDebugging")  
  
Jsme MainWindow.xaml přejmenován na Greetings.xaml na začátku tohoto návodu, ale kód stále odkazuje na mainwindow.xaml jako počáteční identifikátor URI pro aplikace, takže nelze spustit projekt.  
  
#### <a name="to-specify-greetingsxaml-as-the-startup-uri"></a>Určení souboru Greetings.xaml jako spouštěcího identifikátoru URI  
  
1.  V **Průzkumníku**, otevřete soubor App.xaml (v projektu C#) nebo soubor Application.xaml (v projektu jazyka Visual Basic).  
  
2.  Změna `StartupUri="MainWindow.xaml"` k `StartupUri="Greetings.xaml"`a potom uložte změny.  
  
Ladicí program spustit znovu (stiskněte **F5**). Měli byste vidět okno Greetings aplikace. Nyní zavřete okno aplikace a zastavte ladění.  
  
### <a name="to-debug-with-breakpoints"></a>Ladění se zarážkami  
Kód můžete testovat během ladění tak, že přidáte některé zarážky. Můžete přidat zarážky výběrem **ladění**, **Přepnout zarážku**, kliknutím na levém okraji editoru vedle řádek kódu, kde chcete zalomení nebo stisknutím **F9**.  
  
#### <a name="to-add-breakpoints"></a>Přidání zarážek  
  
1.  Otevřete Greetings.xaml.vb nebo Greetings.xaml.cs a vyberte následující řádek:`MessageBox.Show("Hello.")`  
  
2.  Přidejte zarážku z nabídky výběrem **ladění**, pak **Přepnout zarážku**.  
  
     ![Přepnout zarážku – příkaz v nabídce ladění](../ide/media/exploreide-togglebreakpoint.png "togglebreakpoint ExploreIDE –")  
  
     Na levém okraji okna editoru se vedle řádku kódu zobrazí červený kruh.  
  
3.  Vyberte následující řádek: `MessageBox.Show("Goodbye.")`.  
  
4.  Stiskněte **F9** klíče přidat zarážky a potom stiskněte klávesu **F5** spustit ladění.  
  
5.  V **Přivítání** okně zvolte **Hello** přepínač a potom vyberte **zobrazení** tlačítko.  
  
     Na řádku `MessageBox.Show("Hello.")` zvýrazněn žlutě. V dolní části rozhraní IDE, automobily, lokální a sledovat windows jsou ukotveny na levé straně a windows zásobníkem volání, zarážky, příkazu, Immediate a výstup se ukotven společně na pravé straně.  
  
6.  Na řádku nabídek zvolte **ladění**, **Krokovat s Vystoupením**.  
  
     Obnoví spuštění aplikace a zobrazí se okno se zprávou slovem "Hello".  
  
7.  Vyberte **OK** tlačítka v okně se zprávou a tím ho zavřete.  
  
8.  V **pozdrav** okně zvolte **Shledanou** přepínač a potom vyberte **zobrazení** tlačítko.  
  
     Na řádku `MessageBox.Show("Goodbye.")` zvýrazněn žlutě.  
  
9. Vyberte **F5** klíče a pokračujte ladění. Jakmile se zobrazí okno se zprávou, vyberte **OK** tlačítka v okně se zprávou a tím ho zavřete.  
  
10. Zavřete okno aplikace a zastavte ladění.  
  
11. Na řádku nabídek zvolte **ladění**, **zakažte všechny zarážky**.  
  
### <a name="build-a-release-version-of-the-application"></a>Sestavení verze pro vydání aplikace  
 Teď, když ověříte, že vše funguje, můžete připravit sestavení pro vydání aplikace.  
  
#### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>Vyčištění souborů řešení a sestavení verze pro vydání  
  
1.  V hlavní nabídce vyberte **sestavení**, **Vyčistit řešení** odstranit zprostředkující soubory a výstupní soubory, které byly vytvořeny během předchozí sestavení. Není to nutné, ale ho vyčistí výstupy ladění sestavení.  
  
     ![Příkaz Vyčistit řešení v nabídce sestavení](../ide/media/exploreide-cleansolution.png "ExploreIDE CleanSolution")  
  
2.  Změnit konfiguraci sestavení HelloWPFApp z **ladění** k **verze** pomocí ovládacího prvku rozevíracího seznamu na panelu nástrojů (zobrazuje "Debug" aktuálně).  
  
     ![Standardním panelu nástrojů verze vybrané](../ide/media/exploreide-releaseversion.png "ExploreIDE ReleaseVersion")  
  
3.  Sestavte řešení tak, že zvolíte **sestavení**, pak **sestavit řešení**.  
  
     ![Sestavit řešení – příkaz v nabídce sestavení](../ide/media/exploreide-buildsolution.png "ExploreIDE BuildSolution")  
  
Blahopřejeme k dokončení tohoto návodu! Můžete najít .exe jste vytvořili v části adresáře řešení a projektu (...\HelloWPFApp\HelloWPFApp\bin\Release\\). Pokud chcete prozkoumat další příklady, přečtěte si téma [Visual Studio – ukázky](../ide/visual-studio-samples.md).  
  
## <a name="see-also"></a>Viz také
[Co je nového ve Visual Studio 2017](../ide/whats-new-in-visual-studio.md)   
[Začít s vývojem pomocí sady Visual Studio](../ide/get-started-developing-with-visual-studio.md)   
[Tipy pro vyšší produktivitu](../ide/productivity-tips-for-visual-studio.md)