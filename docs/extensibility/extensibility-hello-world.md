---
title: Hello World | Microsoft Docs
ms.custom: ''
ms.date: 07/10/2017
ms.topic: conceptual
ms.assetid: f74e1ad1-1ee5-4360-9bd5-d82467b884ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7c531d8acddfebcd2656d6dca05b95244f54ec01
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31134805"
---
# <a name="creating-your-first-extension-hello-world"></a>Vytváření rozšíření pro první: Hello World

Tento příklad Hello, World vás provede procesem vytvoření vaší první rozšíření pro Visual Studio. Tento kurz vám ukáže, jak přidat nový příkaz pro Visual Studio.

V procesu, se dozvíte, jak:

* **[Vytvoření projektu rozšíření](#create-an-extensibility-project)**
* **[Přidání vlastního příkazu](#add-a-custom-command)**
* **[Upravit zdrojový kód](#modify-the-source-code)**
* **[Spustit](#run-it)**

V tomto příkladu budete používat Visual C# Chcete-li přidat že vlastní nabídky tlačítka s názvem "Vyslovení Hello, World!" který vypadá takto:

![příkaz Hello world](media/hello-world-say-hello-world.png)

## <a name="prerequisites"></a>Požadavky

Než začnete, ujistěte se, že máte nainstalovanou **vývoj rozšíření pro Visual Studio** zatížení, která zahrnuje VSIX šablonu, kterou budete potřebovat a ukázkový kód.

Poznámka: Můžete použít všechny verze sady Visual Studio (Community, Professional nebo Enterprise) vytvořit projekt sady Visual Studio rozšíření.

## <a name="create-an-extensibility-project"></a>Vytvoření projektu rozšíření

Krok 1. Z **soubor** nabídky, klikněte na tlačítko **nový projekt**. V dolní části obrazovky můžete zadat název projektu.

Krok 2. Z **šablony** nabídky, klikněte na tlačítko **Visual C#**, klikněte na tlačítko **rozšiřitelnost**a potom klikněte na **projektu VSIX**.

![Nový projekt](media/hello-world-new-project.png)

Teď byste měli vidět na stránce Začínáme a některé ukázkové prostředky.

Pokud potřebujete nechte tohoto kurzu a vraťte se do ní nový projekt HelloWorld můžete najít na **– úvodní stránka** v **poslední** části.

## <a name="add-a-custom-command"></a>Přidání vlastního příkazu

Krok 1. Pokud vyberete manifest, uvidíte, jaké možnosti jsou změnit instance, metadata, popis a verze.

Krok 2. Klikněte pravým tlačítkem na projekt (ne řešení). V místní nabídce klikněte na tlačítko **přidat**a potom klikněte na **uživatelský ovládací prvek**.

Krok 3. Přejděte zpět na **rozšiřitelnost** části a potom klikněte na **vlastní příkaz**.

Krok 4. V **název** pole v dolní části, zadejte jeho název, například Command.cs.

![vlastního příkazu](media/hello-world-custom-command.png)

Nový příkaz budou zobrazeny v **Průzkumníku řešení** pod **prostředky** firemní pobočky. Toto je také kde najdete další soubory vztahující se k příkazu, jako jsou soubory PNG a ICO, pokud chcete změnit obrázek.

## <a name="modify-the-source-code"></a>Upravit zdrojový kód

V tomto okamžiku je tlačítko přidáváte poměrně Obecné. Budete muset upravit VSCT soubor a soubor CS, pokud chcete změnit.

* Soubor VSCT je, kde je můžete přejmenovat příkazech, a také definovat kde přejde v sadě Visual Studio příkaz systému. Jak můžete prozkoumat soubor VSCT, si všimnete spoustu komentáři kód, který vysvětluje, co každá část ovládací prvky kódu.

* Soubor CS je, kde můžete definovat akce, jako je obslužná rutina kliknutí na.

Krok 1. V **Průzkumníku**, najít soubor VSCT pro nový příkaz. V takovém případě bude zavolána CommandPackage.vsct.

![příkaz balíček vsct](media/hello-world-command-package-vsct.png)

Krok 2. Změna `ButtonText` parametr "Říct Hello, World!"

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

Krok 3. Přejděte zpět na **Průzkumníku řešení** a najít soubor Command.cs. Změňte řetězec `message` pro příkaz `string.Format(..)` na "Hello, World!"

```csharp
  ...
  private void MenuItemCallback(object sender, EventArgs e)
  {
    string message = "Hello World!";
    string title = "Command1";

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

Zajistěte, aby se uložit změny do každého souboru.

## <a name="run-it"></a>Spustit

Nyní můžete spustit ve zdrojovém kódu ve Visual Studio experimentální Instance.

Krok 1. Klikněte na tlačítko **spustit** na panelu nástrojů. Tato akce sestavení projektu a spuštění ladicího programu, spouští novou instanci sady Visual Studio volat **experimentální instanci**.

Zobrazí se slova "Experimentální Instance" v sadě Visual Studio záhlaví.

![experimentální instanci záhlaví](media/hello-world-exp-instance.png)

Krok 2. Na **nástroje** nabídky **experimentální instanci**, klikněte na tlačítko **indikované Hello World!**.

![Konečný výsledek](media/hello-world-final-result.png)

Měli byste vidět výstup z nové vlastní příkazu v tomto případě dialogu v centru obrazovky, který vám poskytne "Hello World!" Zpráva.

## <a name="next-steps"></a>Další kroky

Teď, když znáte základní informace o práci s rozšiřitelnosti Visual Studio, tady je, kde můžete další informace:

* [Zahajuje se vyvíjet rozšíření Visual Studia](starting-to-develop-visual-studio-extensions.md) – ukázky, kurzy. a publikování rozšíření.
* [Co je nového ve Visual Studio 2017 SDK](what-s-new-in-the-visual-studio-2017-sdk.md) – nové funkce rozšíření v Visual Studio 2017
* [V sadě Visual Studio SDK](internals/inside-the-visual-studio-sdk.md) -další podrobnosti o rozšiřitelnosti Visual Studio