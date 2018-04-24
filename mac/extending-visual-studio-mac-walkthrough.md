---
title: Rozšíření sady Visual Studio pro Mac návod
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.technology: vs-ide-sdk
ms.assetid: 7D00512B-9688-4D8D-87A7-F04F207E3D02
ms.openlocfilehash: fdfbc5c10c3b49165960938f7f8832f61a37a805
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="extending-visual-studio-for-mac-walkthrough"></a>Rozšíření sady Visual Studio pro Mac návod

Toto téma vás provede vytváření [balíčku jednoduché rozšíření](https://github.com/mjh4/AddIns/tree/master/DateInserter). Balíček rozšíření bude v sadě Visual Studio vytvořte nový příkaz nabídky upravit pro Mac, která umožňuje uživatelům vložit aktuální datum a čas do otevřete textový dokument.

Tento příklad používá Maker Add-in. Add-In Maker vytvoří novou šablonu projektu a naplní s požadovaných souborů pro balíček naše vlastní rozšíření.

1.   Začněte tím, že spuštění sady Visual Studio pro Mac, pokud ještě není otevřené:

  ![Visual Studio pro Mac – snímek obrazovky](media/extending-visual-studio-mac-addin3.png)

2.   Nainstalujte _Add-in Maker v balíčku rozšíření_ pomocí Správce rozšíření. V sadě Visual Studio nabídce zvolte **rozšíření...** :

  ![Karta doplněk Manager](media/extending-visual-studio-mac-addin4.png)

3.   Přejděte na kartu galerie a typ `Addin Maker` do panelu Hledat v pravém horním. Vyberte doplněk Maker kategorie vývoj Add-in a klikněte na <kbd>nainstalovat</kbd>. Pokud se objeví nic dosáhl aktualizace a hledat znovu:

  ![Doplněk Manager](media/extending-visual-studio-mac-addin5.png)

4.   Teď, když je nainstalován doplněk Maker, můžete začít vytvářet balíček rozšíření. Začněte vytvořením nové řešení.

5.  Z **dialogové okno nové řešení**, zvolte **jiných > Různé > Obecné > Xamarin Studio doplněk > C#** šablony a na následující obrazovce název nové řešení `DateInserter`:

  ![Vytvoření nové řešení](media/extending-visual-studio-mac-addin7New.png)

6.   Visual Studio pro Mac naplní nové řešení:

  ![Vyplněná řešení](media/extending-visual-studio-mac-addin8.png)

7.   Odebrat šablonu kód v `Manifest.addin.xml` a nahraďte ji následujícím kódem:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
        <ExtensionModel>
            <Extension path = "/MonoDevelop/Ide/Commands/Edit">
                <Command id = "DateInserter.DateInserterCommands.InsertDate"
                    _label = "Insert Date"
                    defaultHandler = "DateInserter.InsertDateHandler" />
            </Extension>

            <Extension path = "/MonoDevelop/Ide/MainMenu/Edit">
                <CommandItem id="DateInserter.DateInserterCommands.InsertDate" />
            </Extension>
        </ExtensionModel>
    ```

8.   Teď je potřeba nastavit soubory, které bude nakonec zpracovávat vkládání datum a čas do textového editoru. Klikněte pravým tlačítkem na uzel projektu a přidejte nový soubor. Vyberte **Obecné > prázdná třída** a pojmenujte nový soubor *InsertDateHandler*:

  ![Vložit datum obslužné rutiny](media/extending-visual-studio-mac-addin9.png)

9.   Umožňuje odebrat kód šablony z `InsertDateHandler.cs` a nahraďte ji následujícím kódem:

    ```cs
    using MonoDevelop.Components.Commands;
    using MonoDevelop.Ide;
    using MonoDevelop.Ide.Gui;
    using System;

    namespace DateInserter
    {
        class InsertDateHandler : CommandHandler
        {
            protected override void Run()
            {

            }

            protected override void Update(CommandInfo info)
            {

            }
        }
    }
    ```

  Tyto dvě metody zástupný symbol jsme budete rozbalte později.

10.   Klikněte pravým tlačítkem na **DateInserter** projekt a vyberte **Přidat > Nový soubor**. Vyberte **Obecné > prázdný výčet**a zadejte název nového souboru *DateInserterCommands*:

  ![DateInserterCommands](media/extending-visual-studio-mac-addin10.png)

11.   Přidat `InsertDate` příkaz jako nový výčet ve `DateInserterCommands.cs` souboru:

    ``` cs
    using System;

    namespace DateInserter
    {
        public enum DateInserterCommands
        {
            InsertDate,
        }
    }
    ```

12.   V tomto okamžiku byste měli mít balíček rozšíření práci. Uložení práce a spustíte aplikaci můžete otestovat ho. Prostředí IDE spustí novou instanci sady Visual Studio pro Mac pomocí nového balíčku rozšíření nainstalované. Pokud přejdete do **nabídky Upravit**, uvidíte, že Visual Studio pro Mac má nový parametr s názvem **vložit datum**, které jsou popsány v následující snímek obrazovky:

  ![Vložte příkaz datum](media/extending-visual-studio-mac-addin11.png)

  Všimněte si, že vyberete vložit data z místní nabídky nemá žádný vliv, jako aktuální implementace má jenom metody zástupný symbol.

13.   Rozhraní je na místě pro balíček rozšíření, a je na čase napsat kód, který zajišťuje vkládání datum. Nejdřív zkontrolujte, zda **vložte příkaz datum** je povoleno pouze pokud má uživatel textový soubor otevřete tak, že nahradíte `Update` metoda v `InsertDateHandler.cs` následujícím kódem:

    ```cs
    protected override void Update(CommandInfo info)
    {
        info.Enabled = IdeApp.Workbench.ActiveDocument?.Editor != null;
    }
    ```

14.   Aktualizace příkaz `Run` metoda vložit datum a čas následujícím kódem:

    ``` cs
    protected override void Run () {
        var editor = IdeApp.Workbench.ActiveDocument.Editor;
        var date = DateTime.Now.ToString ();
        editor.InsertAtCaret (date);

    }
    ```

15.   Nakonec spuštěním umožňuje naše balíčku rozšíření otestovat. V nové instanci sady Visual Studio pro Mac, vyberte **Upravit > Vložit datum**. Aktuální datum a čas je vložen v našem pomocí kurzoru, které jsou popsány v následující snímek obrazovky:

  ![Vložit snímek datum](media/extending-visual-studio-mac-addin12.png)
