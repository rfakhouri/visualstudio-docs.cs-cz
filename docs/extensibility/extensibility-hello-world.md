---
title: Kurz Hello World rozšíření | Dokumentace Microsoftu
ms.date: 03/14/2019
ms.topic: conceptual
ms.assetid: f74e1ad1-1ee5-4360-9bd5-d82467b884ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 910e1890fd07c0888c47735451cba29aa08ec916
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160703"
---
# <a name="create-your-first-extension-hello-world"></a>Vytvořte své první rozšíření: Hello World

V tomto příkladu Hello World vás provede vytvořením své první rozšíření pro Visual Studio. V tomto kurzu se dozvíte, jak přidat nový příkaz do sady Visual Studio.

V procesu, se dozvíte, jak:

* **[Vytvořit projekt rozšíření](#create-an-extensibility-project)**
* **[Přidat vlastní příkaz.](#add-a-custom-command)**
* **[Změnit zdrojový kód](#modify-the-source-code)**
* **[Infrastruktura.](#run-it)**

V tomto příkladu použijete Visual C# můžete přidat že vlastní tlačítko s názvem "Řekněme, že Hello World!" který vypadá takto:

![Příkaz Hello World](media/hello-world-say-hello-world.png)

> [!NOTE]
> Tento článek se týká k sadě Visual Studio ve Windows. Visual Studio pro Mac, najdete v části [návod rozšíření v sadě Visual Studio pro Mac](/visualstudio/mac/extending-visual-studio-mac-walkthrough).

## <a name="prerequisites"></a>Požadavky

Než začnete, ujistěte se, že jste nainstalovali **vývoj rozšíření sady Visual Studio** úlohu, která zahrnuje VSIX šablony budete potřebovat a ukázkový kód.

> [!NOTE]
> Můžete použít všechny edice sady Visual Studio (Community, Professional nebo Enterprise) Chcete-li vytvořit projekt rozšíření sady Visual Studio.

## <a name="create-an-extensibility-project"></a>Vytvořit projekt rozšíření

::: moniker range="vs-2017"

Krok 1. Z **souboru** nabídce vyberte možnost **nový projekt**.

Krok 2. Do vyhledávacího pole v pravém horním rohu, zadejte "vsix" a vyberte vizuál C# **projekt VSIX**. Zadejte "HelloWorld" **název** v dolní části dialogového okna a vyberte **OK**.

![Nový projekt](media/hello-world-new-project.png)

Teď byste měli vidět stránku Začínáme a některé ukázkové prostředky.

Pokud potřebujete ponechat v tomto kurzu, vraťte se do něj, můžete najít váš nový projekt Hello World na **úvodní stránka** v **poslední** oddílu.

::: moniker-end

::: moniker range=">=vs-2019"

Krok 1. Z **souboru** nabídce vyberte možnost **nový projekt**. Vyhledejte "vsix" a vyberte vizuál C# **projekt VSIX** a potom **Další**.

Krok 2. Zadejte "HelloWorld" **název projektu** a vyberte **vytvořit**.

![Nový projekt](media/hello-world-new-project-2019.png)

Teď byste měli vidět projekt Hello World v **Průzkumníka řešení**.

::: moniker-end

## <a name="add-a-custom-command"></a>Přidat vlastní příkaz.

Krok 1. Pokud vyberete *.vsixmanifest* soubor manifestu, uvidíte, jaké možnosti jsou změnit, jako je verze, popis a Autor.

Krok 2. Klikněte pravým tlačítkem na projekt (nikoli řešení). V místní nabídce vyberte **přidat**a potom **nová položka**.

Krok 3. Vyberte **rozšiřitelnost** části a klikněte na tlačítko **vlastního příkazu**.

Krok 4. V **název** pole v dolní části, zadejte název souboru, třeba *Command.cs*.

![vlastní příkaz.](media/hello-world-custom-command.png)

Váš nový příkaz Soubor je viditelný v **Průzkumníka řešení**. V části **prostředky** uzlu, najdete tu souborů souvisejících s svých rukou. Například pokud chcete změnit obrázek, soubor PNG je tady.

## <a name="modify-the-source-code"></a>Změnit zdrojový kód

Na tento bod, příkaz a tlačítko je text automaticky generované a velmi zajímavé. Pokud chcete provést změny, můžete upravit VSCT soubor a soubor CS.

* Soubor VSCT je, kde je můžete přejmenovat příkazům, jakož i definují, kam obrátit příkaz systému Visual Studio. Při prohlížení souboru VSCT si povšimněte komentáře, které popisují, co každý oddíl VSCT ovládacích prvků kódu.

* Soubor CS je, ve kterém můžete definovat akce, jako je například obslužné rutiny kliknutí.

::: moniker range="vs-2017"

Krok 1. V **Průzkumníka řešení**, najít soubor VSCT pro nový příkaz. V takovém případě bude volána *CommandPackage.vsct*.

![příkaz balíčku vsct](media/hello-world-command-package-vsct.png)

::: moniker-end

::: moniker range=">=vs-2019"

Krok 1. V **Průzkumníka řešení**, najít soubor VSCT pro váš balíček rozšíření VS. V takovém případě bude volána *HelloWorldPackage.vsct*.

::: moniker-end

Krok 2. Změnit `ButtonText` parametr `Say Hello World!`.

```xml
  ...
  <Button guid="guidCommandPackageCmdSet" id="CommandId" priority="0x0100" type="Button">
     <Parent guid="guidCommandPackageCmdSet" id="MyMenuGroup" />
     <Icon guid="guidImages" id="bmpPic1" />
     <Strings>
        <ButtonText>Say Hello World!</ButtonText>
     </Strings>
  </Button>
  ...
```

Krok 3. Přejděte zpět na **Průzkumníka řešení** a najít *Command.cs* souboru. V `Execute` metodu, změňte řetězec `message` z `string.Format(..)` k `Hello World!`.

```csharp
  ...
  private void Execute(object sender, EventArgs e)
  {
    ThreadHelper.ThrowIfNotOnUIThread();
    string message = "Hello World!";
    string title = "Command";

    // Show a message box to prove we were here
    VsShellUtilities.ShowMessageBox(
        this.ServiceProvider,
        message,
        title,
        OLEMSGICON.OLEMSGICON_INFO,
        OLEMSGBUTTON.OLEMSGBUTTON_OK,
        OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST);
  }
  ...
```

Nezapomeňte si uložit změny do každého souboru.

## <a name="run-it"></a>Infrastruktura.

Nyní můžete spustit zdrojový kód v experimentální instanci aplikace Visual Studio.

Krok 1. Stisknutím klávesy **F5** ke spuštění **spustit ladění** příkazu. Tento příkaz sestaví váš projekt a spustí ladicí program spouští novou instanci sady Visual Studio, volá se, **experimentální instanci**.

::: moniker range="vs-2017"

Zobrazí se slova **experimentální instanci** v záhlaví programu sady Visual Studio.

![experimentální instanci záhlaví](media/hello-world-exp-instance.png)

::: moniker-end

Krok 2. Na **nástroje** nabídku **experimentální instanci**, klikněte na tlačítko **Say Hello World!**.

![Konečný výsledek](media/hello-world-final-result.png)

Byste měli vidět výstup z vlastního příkazu, v tomto případě dialogové okno do středu obrazovky, který poskytuje **Hello World!** zpráva.

## <a name="next-steps"></a>Další kroky

Teď, když znáte základy práce se rozšíření produktu Visual Studio, zde je, kde můžete další informace:

* [Začněte vyvíjet rozšíření aplikace Visual Studio](starting-to-develop-visual-studio-extensions.md) – ukázky, kurzy. a publikování rozšíření
* [Co je nového ve Visual Studio 2017 SDK](what-s-new-in-the-visual-studio-2017-sdk.md) – nové funkce rozšíření v sadě Visual Studio 2017
* [Co je nového ve Visual Studio SDK. 2019](whats-new-visual-studio-2019-sdk.md) – nové funkce rozšíření v aplikaci Visual Studio 2019
* [V sadě Visual Studio SDK](internals/inside-the-visual-studio-sdk.md) – další podrobnosti o rozšíření produktu Visual Studio