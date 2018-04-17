---
title: 'Rychlý úvod: Vytvoření první aplikace pro univerzální platformu Windows v sadě Visual Studio s XAML a C# | Microsoft Docs'
ms.custom: ''
ms.date: 04/04/2018
ms.technology:
- vs-acquisition
ms.topic: quickstart
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: d1263b752a27522b9a551d8015689f60422984ad
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-create-your-first-universal-windows-platform-application-in-visual-studio-with-xaml-and-c35"></a>Rychlý úvod: Vytvoření první aplikace pro univerzální platformu Windows v sadě Visual Studio s XAML a C&#35;

V tento úvod 5 až 10 minut v sadě Visual Studio integrované vývojové prostředí (IDE) vytvoříte aplikaci "Hello World", který běží na jakékoli zařízení s Windows 10. K tomu budete používat šablona projektu univerzální platformu Windows (UWP), Extensible aplikace Markup Language (XAML) a programovací jazyk C#.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="create-a-project"></a>Vytvoření projektu

Nejprve vytvořte projekt univerzální platformu Windows. Typ projektu se dodává s všechny soubory šablony, které budete potřebovat, než jste přidali i nic!

1. Otevřete Visual Studio 2017.

2. V horní nabídce vyberte příkaz **soubor** > **nový** > **projektu...** .

3. V levém podokně **nový projekt** dialogové okno, rozbalte seznam **Visual C#**a potom zvolte **univerzální pro Windows**. V prostředním podokně vyberte **prázdná aplikace (univerzální pro Windows)**. Pojmenujte projekt *HelloWorld* a zvolte **OK**.

   ![Univerzální pro Windows šablona projektu v dialogovém okně Nový projekt v prostředí Visual Studio IDE](../ide/media/new-project-csharp-uwp-helloworld.png)

   > [!NOTE]
   > Pokud nevidíte **prázdná aplikace (univerzální pro Windows)** projektu šablony, klikněte na tlačítko **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno.<br><br>![Klikněte na odkaz otevřete instalační program Visual Studio z dialogového okna Nový projekt](../ide/media/vb-open-visual-studio-installer-hello-world.png)<br><br>Spustí instalační program Visual Studio. Vyberte **vývoj pro univerzální platformu Windows** zatížení a potom zvolte **upravit**.<br><br>![Univerzální platforma Windows vývoj zatížení v instalačním programu Visual Studio](../ide/media/uwp-dev-workload.png)

4. Když **nový projekt univerzální platformu Windows** se zobrazí dialogové okno, zvolte **OK**.

   ![Přijměte výchozí cílová verze a minimální verze nastavení v dialogu Nový projekt univerzální platforma Windows](../ide/media/new-uwp-project-target-minver-dialog.png)

  > [!NOTE]
  > Pokud je to poprvé používáte Visual Studio k vytvoření aplikace pro UPW, **nastavení** dialogové okno se může objevit. Zvolte **režim vývojáře**a potom zvolte **Ano**.<br><br>
 ![Povolit režim vývojáře v dialogovém okně Nastavení UWP](../ide/media/enable-developer-mode.png)<br><br>Visual Studio nainstaluje balíček další režim vývojáře. Po dokončení instalace balíčku zavřete **nastavení** dialogové okno.

## <a name="create-the-application"></a>Vytvoření aplikace

Je čas spuštění vývoj. Budete přidání ovládacího prvku tlačítko, na tlačítko Přidat akci a pak spusťte aplikaci "Hello World" v tématu bude vypadat takto.

### <a name="add-a-button-to-the-design-canvas"></a>Přidání tlačítka na plátno návrhu

1. V **Průzkumníku řešení**, dvakrát klikněte na **MainPage.xaml** otevření zobrazení rozdělení.

  ![Otevřete MainPage.xaml v Průzkumníku řešení ](../ide/media/uwp-solution-explorer-MainPage-xaml.png)

  Existují dvě podokna: **návrháře XAML**, což zahrnuje na plátno návrhu a **editoru XAML**, kde můžete přidat nebo změnit kód.    

  ![V podokně Návrhář XAML v editoru XAML](../ide/media/uwp-xaml-editor.png)

2. Zvolte **sada nástrojů** a otevřete okno rozevírací sady nástrojů.

  ![Klikněte na panel nástrojů a otevřete okno rozevírací sada nástrojů](../ide/media/uwp-toolbox.png)

  (Pokud nevidíte možnost sada nástrojů, můžete otevřít ho v řádku nabídek. Chcete-li tak učinit, zvolte **zobrazení** > **nástrojů**. Také můžete stisknout klávesu **Ctrl**+**Alt**+**X**.)

3. Klikněte **Pin** ikonu ukotvení panelu nástrojů okna.

  ![Kliknutím na ikonu Připnutí na ukotvení panelu nástrojů okna](../ide/media/uwp-toolbox-autohide.png)

4. Klikněte **tlačítko** řízení a poté ji přetáhněte na plátno návrhu.

   ![Klikněte na ovládací prvek tlačítko a přetáhněte ji na plátno návrhu](../ide/media/uwp-toolbox-add-button-control.png)

  Pokud si prohlédnete kód v editoru XAML, uvidíte, že tlačítko byl přidán zde příliš:

  ![Klikněte na ovládací prvek tlačítko a přetáhněte ji na plátno návrhu](../ide/media/uwp-xaml-control-code-window.png)

### <a name="add-a-label-to-the-button"></a>Přidání štítku pro tlačítko

1. V editoru XAML, změňte tlačítko obsahu hodnotu z "Button" na "Hello, World!"

   ![Změňte hodnotu obsahu tlačítka na Hello World](../ide/media/uwp-change-button-text-in-xaml-code-window.png)

2. Všimněte si, že se změní na tlačítko v Návrháři XAML, příliš.

   ![Tlačítko změny Hello, World na plátně návrhu](../ide/media/uwp-button-text-change-in-design-canvas.png)

### <a name="add-an-event-handler"></a>Přidání obslužné rutiny události

Komplikovanější, zvuků "obslužné rutiny události", ale je stejně jiný název pro kód, který je volána, když se stane událost. V takovém případě přidá akci "Hello World!" tlačítko.

1. Dvakrát klikněte tlačítko – ovládací prvek na plátně návrhu.

2.  Upravit kód obslužné rutiny událostí v *MainPage.xaml.cs*, kódu stránky.

 Toto je, kde získat zajímavé věcí. Výchozí obslužnou rutinu události vypadá takto:

   ![Obslužné rutiny události Button_Click výchozí ](../ide/media/uwp-button-click-code.png)

 Nyní změníme, takže vypadá takto:

    ![Novou obslužnou rutinu události Button_Click asynchronní ](../ide/media/uwp-add-hello-world-async-code.png)

  Tady je kód pro kopírování a vkládání:

  ```C#
  private async void Button_Click(object sender, RoutedEventArgs e)
         {
             MediaElement mediaElement = new MediaElement();
             var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();
             Windows.Media.SpeechSynthesis.SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello, World!");
             mediaElement.SetSource(stream, stream.ContentType);
             mediaElement.Play();
         }
  ```

#### <a name="what-did-we-just-do"></a>Co jsme právě?

Kód některé rozhraní API systému Windows používá k vytvoření objektu souhrnnou řeči a poté nastaví nějaký text. Tím vyjádříte. (Další informace o používání SpeechSynthesis najdete v tématu <xref:System.Speech.Synthesis>.)

## <a name="run-the-application"></a>Spuštění aplikace

Je čas vytvořit, nasadit a spustit aplikaci UWP "Hello World" v tématu vypadá a vyznívá jako. Tady je způsob.

1. Zvolte **místního počítače** a spusťte aplikaci.

   ![Klikněte na místním počítači a spuštění ladění aplikace UWP](../ide/media/uwp-start-or-debug.png "klikněte na místním počítači spustit a ladění aplikace UWP")

   (Alternativně můžete **ladění** > **spustit ladění** z řádku nabídek nebo klikněte na tlačítko **F5** spuštění vaší aplikace.)

2. Zobrazte aplikaci, která se zobrazí úvodní obrazovka zmizí, jakmile. Aplikace by měl vypadat podobně jako tento:

   ![UWP "Hello World" aplikace](../ide/media/uwp-hello-world-app.png)

3. Klikněte **Hello, World** tlačítko.

 Zařízení se dozvíte oznámena Windows 10, "Hello, World!"

4. Chcete-li zavřít aplikaci, klikněte na tlačítko **Zastavte ladění** tlačítka na panelu nástrojů. (Případně vyberte **ladění** > **Zastavte ladění** z řádku nabídek nebo stiskněte klávesu **Shift**+**F5**.)

## <a name="next-steps"></a>Další kroky

Blahopřejeme k dokončení tento rychlý start! Věříme, že jste se naučili základy o UWP a Visual Studio IDE. Další informace, pokračujte následujícím kurzu:

> [!div class="nextstepaction"]
> [Vytvoření uživatelského rozhraní](/windows/uwp/design/basics/xaml-basics-ui)
