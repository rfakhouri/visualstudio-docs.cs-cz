# <a name="create-an-ai-project-from-existing-code"></a>Vytvoření projektu AI z existujícího kódu

Jakmile jste [nainstalované Visual Studio Tools pro AI](installation.md), je snadné tím existující kód Python, do projektu sady Visual Studio.

> [!Important]
>
> Proces popsaný tady není přesuňte nebo zkopírujte původním zdrojovým souborům. Pokud chcete pracovat s kopií, duplicitní nejprve složce.

1. Spusťte sadu Visual Studio a vyberte **soubor > Nový > projekt**.

1. V **nový projekt** dialogové okno, vyhledejte "**AI nástroje**", vyberte "**kód z existující Python**" šablony, název a umístění poskytnout projekt a vyberte **OK**.

    ![Nový projekt z existujícího kódu, krok 1](media\create-project-existing\new-ai-project.png)

1. V průvodci, který se zobrazí, nastavení cesty pro váš stávající kód, nastavte filtr pro typy souborů a zadejte všechny cesty hledání, které projekt vyžaduje, a potom vyberte **OK**. Pokud si nejste jisti, jaké vyhledávání cest, nechte toto pole prázdné.

![Nový projekt z existujícího kódu, krok 2](media\create-project-existing\azurebatch-newproject.png)

> Pokud váš stávající kód je součástí projektu Azure Machine Learning, podívejte se "**složky je Azure Machine Learning**" k zajištění úspěšné převod důležité podrobnosti konfigurace Azure Machine Learning, třeba které experimentování účet, který pracovního prostoru, výpočetní kontexty používat a další.

1. Pokud chcete nastavit spuštění souboru, vyhledejte soubor v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **nastavit jako spouštěcí soubor**.

1. V případě potřeby spustit program stisknutím Ctrl + F5 nebo výběrem **ladění > Spustit bez ladění**.

> [!div class="nextstepaction"]
> [Kurz: Práce s Python v sadě Visual Studio](../python/tutorial-working-with-python-in-visual-studio-step-00-installation.md)

## <a name="see-also"></a>Viz také

- [Vytvoření prostředí pro existující překladač Pythonu](../python/managing-python-environments-in-visual-studio.md#creating-an-environment-for-an-existing-interpreter)