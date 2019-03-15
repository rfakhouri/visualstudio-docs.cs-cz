---
title: Rychlý Start – otevřete složku kódu Pythonu
description: V tomto rychlém startu otevření a spuštění kódu Pythonu ze složky bez použití projektu sady Visual Studio (Visual Studio. 2019 pouze).
ms.date: 03/12/2019
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
monikerRange: '>= vs-2019'
ms.openlocfilehash: 6cf4e15ec464b1d438245cd7bfe254d9464ad2a6
ms.sourcegitcommit: 4c7a0c2d712eb24609216577a793e912a6083eaf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "57986940"
---
# <a name="quickstart-open-and-run-python-code-in-a-folder"></a>Rychlý start: Otevření a spuštění kódu Pythonu ve složce

Jakmile [nainstalována podpora Pythonu v aplikaci Visual Studio 2019](installing-python-support-in-visual-studio.md), je snadné spuštění existujícího kódu Pythonu ve Visual Studio 2019 bez vytvoření projektu sady Visual Studio.

> [!Note]
> Visual Studio 2017 a starší je nutné vytvořit projekt sady Visual Studio ke spuštění kódu Pythonu, které můžete snadno proveďte pomocí předdefinovaných projektových šablon. Zobrazit [rychlý start: Vytvoření projektu Pythonu z existujícího kódu](quickstart-01-python-in-visual-studio-project-from-existing-code.md)

1. V tomto návodu můžete použít libovolnou složku s kódu v Pythonu, který vás zajímá. Pokud chcete postupovat z příkladu, naklonujte úložiště GitHub gregmalcolm/python_koans k počítači pomocí příkazu `git clone https://github.com/gregmalcolm/python_koans` v příslušné složce.

1. Spusťte Visual Studio 2019 a na úvodní obrazovce vyberte **otevřít** v dolní části **Začínáme** sloupce. Případně, pokud již máte Visual Studio běží, vyberte **souboru** > **otevřít** > **složky** místo příkazu.

    ![Úvodní obrazovka aplikace Visual Studio](media/quickstart-open-folder/01-open-local-folder.png)

1. Přejděte do složky, která obsahuje kód Pythonu, a pak zvolte **vybrat složku**. Pokud používáte python_koans kódu, je nutné vybrat `python3` složku ve složce klonování.

    ![Dialogové okno Vybrat složku z příkazu Otevřít složku](media/quickstart-open-folder/02-select-folder.png)

1. Visual Studio zobrazí ve složce **Průzkumníka řešení** v co se nazývá **zobrazení složky**. Můžete rozbalit nebo sbalit složek pomocí šipky na levém okraji názvy složek:

    ![Ovládací prvky rozbalíte nebo sbalíte složek v Průzkumníku řešení](media/quickstart-open-folder/03-expand-collapse-folders.png)

1. Při otevírání složky Pythonu, sada Visual Studio vytvoří několik skrytých složek ke správě nastavení související s projektem. Zobrazíte tyto složky (a jakékoli jiné skryté soubory a složky, například *.Git, na který* složky), vyberte **zobrazit všechny soubory** tlačítka panelu nástrojů:

    ![Zobrazení skrytých složek v Průzkumníku řešení](media/quickstart-open-folder/05-view-hidden-folders.png)

1. Kód spustit, musíte nejprve k identifikaci při spuštění nebo primární programový soubor. V tomto příkladu, spouštěcí soubor *tento koans.py*. Klikněte pravým tlačítkem na soubor a vyberte **nastavit jako položku při spuštění**.

    ![Nastavení položku při spuštění v Průzkumníku řešení](media/quickstart-open-folder/06-set-as-startup-item-command.png)

    > [!Important]
    > Pokud spouštěcí položka není umístěný v kořenovém adresáři složky můžete otevřít, musíte také přidat řádek do konfiguračního souboru JSON spuštění podle popisu v části [nastavit pracovní adresář](#set-a-working-directory).

1. Spuštění kódu stisknutím klávesy **Ctrl**+**F5** nebo jeho výběru **ladění** > **spustit bez ladění**. Můžete také vybrat tlačítko na panelu nástrojů, který zobrazuje položku při spuštění s tlačítko Přehrát, která spustí kód v ladicím programu sady Visual Studio. Ve všech případech se Visual Studio zjistí, že spouštěcí položka soubor Pythonu, proto se automaticky spustí kód ve výchozím prostředí Pythonu. (Toto prostředí se zobrazí napravo od položku při spuštění na panelu nástrojů).

    ![Spustit ladicí program tlačítka panelu nástrojů](media/quickstart-open-folder/07-start-debug-toolbar.png)

1. Výstup programu se zobrazí v samostatném příkazovém okně:

    ![Okno výstup pro spuštění kódu Pythonu](media/quickstart-open-folder/08-result-window.png)

1. Chcete-li spustit kód v jiném prostředí, vyberte ho z rozevíracího seznamu ovládacího prvku na panelu nástrojů a pak znovu spusťte položku při spuštění.

1. Zavřít složku v sadě Visual Studio, vyberte **souboru** > **Zavřít složku** příkazu nabídky.

## <a name="set-a-working-directory"></a>Nastavte pracovní adresář

Visual Studio ve výchozím nastavení, spustí projektu Pythonu otevřít složku v kořenovém adresáři stejné složce. Kód ve vašem projektu, ale předpokládat, že se Pythonu běží v podsložce. Předpokládejme například, otevřete v kořenové složce úložiště python_koans a potom nastavte *pythonu3/zamýšlené koans.py* soubor jako položku při spuštění. Je-li spustit kód se zobrazí chyba, která *koans.txt* soubor nebyl nalezen. K této chybě dochází, protože *tento koans.py* předpokládá, že se Pythonu běží v *pythonu3* složku spíše než kořenovém adresáři úložiště.

V takových případech musíte taky přidá řádek do souboru JSON konfigurace spuštění zadat pracovní adresář:

1. Klikněte pravým tlačítkem na Pythonu (*.py*) spouštěcí soubor v **Průzkumníka řešení** a vyberte **nastavení ladění a spouštění**.

    ![Nastavení ladění a spouštění příkazu pro soubor Pythonu](media/quickstart-open-folder/09-debug-launch-settings-menu-command.png)

1. V **vyberte ladicí program** dialogové okno, které se zobrazí, vyberte **výchozí** a klikněte na tlačítko **vyberte**.

    ![Nastavení ladění a spouštění příkazu pro soubor Pythonu](media/quickstart-open-folder/10-select-debugger.png)

    > [!Note]
    > Pokud nevidíte **výchozí** jako volba, ujistěte se, že jste klikli pravým tlačítkem myši Python *.py* souboru při výběru **nastavení ladění a spouštění** příkazu. Visual Studio používá typ souboru k určení při možnosti ladicího programu k zobrazení.

1. Visual Studio otevře soubor s názvem *souboru launch.vs.json*, která je umístěná v skrytého *.vs* složky. Tento soubor popisuje kontext ladění pro projekt. Pokud chcete zadat pracovní adresář, přidejte hodnotu `"workingDirectory"`, například `"workingDirectory": "python3"` například python koans:

    ```json
    {
      "version": "0.2.1",
      "defaults": {},
      "configurations": [
        {
          "type": "python",
          "interpreter": "(default)",
          "interpreterArguments": "",
          "scriptArguments": "",
          "env": {},
          "nativeDebug": false,
          "webBrowserUrl": "",
          "project": "python3\\contemplate_koans.py",
          "name": "contemplate_koans.py",
          "workingDirectory": "python3"
        }
      ]
    }
    ```

1. Soubor uložte a spusťte program znovu, který teď bude spouštět v zadané složce.

## <a name="next-steps"></a>Další kroky

> [!div class="nextstepaction"]
> [Kurz: Práce s využitím Pythonu v sadě Visual Studio](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Viz také:

- [Rychlý start: Vytvoření projektu Pythonu z existujícího kódu](quickstart-01-python-in-visual-studio-project-from-existing-code.md)
- [Rychlý start: Vytvoření projektu Pythonu z úložiště](quickstart-03-python-in-visual-studio-project-from-repository.md)
- [Ručně identifikovat existující interpret Pythonu](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment)
