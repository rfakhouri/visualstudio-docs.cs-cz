# <a name="clone-a-repository-of-python-code-in-visual-studio"></a>Klonování úložiště Python kódu v sadě Visual Studio

Jakmile jste [nainstalované Visual Studio Tools pro AI](installation.md), můžete snadno klonovat úložiště v kódu jazyka Python a vytvořte projekt z něj.

1. Pro připojení k úložišť GitHub, spusťte instalační program sady Visual Studio, vyberte **upravit**a vyberte **jednotlivých součástí** kartě. Přejděte dolů k položce **Code nástroje** vyberte **Githubu rozšíření pro Visual Studio**a vyberte **upravit**.
    
    ![Když Githubu rozšíření vyberete v instalačním programu sady Visual Studio](media\create-project-repo\installation-github-extension.png)
    
2. Spusťte sadu Visual Studio.

3. Vyberte **zobrazení > Team Explorer...**  otevřete **Team Explorer** okno, ve kterém můžete připojit k webu GitHub nebo Visual Studio Team Services, nebo klonovat úložiště.

    ![Team explorer okno zobrazující Visual Studio Team Services, GitHub a klonování úložiště](media\create-project-repo\team-explorer.png)

4. Do pole Adresa URL v části **místní úložiště Git**, zadejte `https://github.com/Microsoft/samples-for-ai`, zadejte složku pro klonovaný soubory a vyberte **klon**.

    > [!Tip]
    > Složky, kterou zadáte v Team Explorer je konkrétní složky přijímat klonovaný soubory. Na rozdíl od `git clone` příkazu vytvoříte klon v Team Exploreru nevytvoří automaticky podsložku s názvem úložiště.

5. Po dokončení klonování dvakrát klikněte na složku úložiště v dolní části Team Explorer a přejděte na řídicí panel úložiště. V části **řešení**, vyberte **nový...** .

    ![Okno Průzkumníka týmu, vytvoření nového projektu z klonu](media\create-project-repo\team-explorer-new-project.png)

6. V **nový projekt** dialog, který se zobrazí, vyberte možnost "**z existujícího kódu Python**", zadejte název projektu, nastavte **umístění** do stejné složky jako úložiště, a Vyberte **OK**. V průvodci, který se zobrazí, vyberte **Dokončit**.

7. Vyberte **zobrazení > Průzkumníku řešení** z nabídky.

8. V Průzkumníku řešení rozbalte `TensorFlow Examples> MNIST` uzel, klikněte pravým tlačítkem na `convolutional.py`a vyberte **nastavit jako spouštěcí soubor**. Tento krok informuje soubor, který se má používat při spuštění projektu sady Visual Studio.

10. Stiskněte klávesy Ctrl + F5 nebo vyberte **ladění > Spustit bez ladění** ke spuštění programu. Pokud se zobrazí ', znovu zkontrolujte pracovní adresář nastavení v předchozím kroku.


11. Po úspěšném spuštění program uvidíte ho stáhnout vaše školení a testovací datové sady, pak trénování modelu a vaše míra výstupních chyb. Chcete-li míra chyb snížení v čase

    ![První výstup z programu Python MNIST](media\create-project-repo\tensorflow-mnist-running.png)

> Pokud používáte Anaconda a dojde k chybě o chybějící numpy, budete muset změnit prostředí python, budete muset [změnit prostředí python používat Anaconda](https://docs.microsoft.com/visualstudio/python/python-environments) 

11. Můžete vizualizovat průběh s TensorBoard. Klikněte pravým tlačítkem na projekt a klikněte na tlačítko **spustit TensorBoard** poté vyberte adresář výstupu TensorBoard protokoly.

    ![Spustit tensorboard](media\create-project-repo\run-tensorboard.png)

11. Všimněte si, chyba snížení přesčas, což znamená, že je zlepšení kvality

    ![Spustit tensorboard](media\create-project-repo\tensorboard.png)