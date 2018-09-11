---
ms.technology: vs-ai-tools
ms.openlocfilehash: 5abaf2aafe2ff265123e9d4ed12f0ee350b22879
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283519"
---
# <a name="clone-a-repository-of-python-code-in-visual-studio"></a>Naklonujte úložiště kódu v Pythonu v sadě Visual Studio

Jakmile [nainstalované Visual Studio Tools pro AI](installation.md), můžete snadno naklonujte úložiště kódu v Pythonu a vytvoření projektu z něj.

1. Pro připojení k úložištím GitHub, spusťte instalační program sady Visual Studio, vyberte **změnit**a vyberte **jednotlivé komponenty** kartu. Přejděte dolů k položce **kódu nástroje** vyberte **rozšíření GitHub pro Visual Studio**a vyberte **změnit**.

    ![Výběr GitHub extension v instalačním programu sady Visual Studio](media\create-project-repo\installation-github-extension.png)

2. Spusťte sadu Visual Studio.

3. Vyberte **zobrazení > Průzkumník týmových projektů...**  otevřít **Team Exploreru** okno, ve kterém můžete připojit ke Githubu nebo Azure DevOps nebo klonování úložiště.

    ![Okno Průzkumníka týmu zobrazující Azure DevOps, Githubu a klonování úložiště](media\create-project-repo\team-explorer.png)

4. Do pole Adresa URL v části **místní úložiště Git**, zadejte `https://github.com/Microsoft/samples-for-ai`zadejte složky pro klonované soubory a vyberte **klonování**.

    > [!Tip]
    > Složka, kterou zadáte v Průzkumníku týmových projektů je konkrétní složky pro klonované soubory příjem. Na rozdíl od `git clone` příkazu, vytváření v Team Exploreru klonu neprovádí automatické vytváření podsložku s názvem úložiště.

5. Při klonování je hotové, klikněte dvakrát na složku úložiště v dolní části Průzkumníku týmových projektů přejděte na řídicí panel úložiště. V části **řešení**vyberte **nový...** .

    ![Okno Průzkumníka týmu, vytvoření nového projektu z klonu](media\create-project-repo\team-explorer-new-project.png)

6. V **nový projekt** dialogové okno, které se zobrazí, vyberte "**z existujícího kódu Pythonu**", zadejte název projektu, nastavte **umístění** do stejné složky jako úložiště, a Vyberte **OK**. V průvodci, který se zobrazí, vyberte **Dokončit**.

7. Vyberte **zobrazení > Průzkumník řešení** z nabídky.

8. V Průzkumníku řešení rozbalte `TensorFlow Examples> MNIST` uzel, klikněte pravým tlačítkem na `convolutional.py`a vyberte **nastavit jako spouštěcí soubor**. Tento krok informuje soubor, který by měl použít při spuštění projektu sady Visual Studio.

10. Stisknutím kláves Ctrl + F5 nebo vyberte **ladit > Spustit bez ladění** ke spuštění programu. Pokud se zobrazí ", znovu zkontrolujte pracovní adresář nastavení v předchozím kroku.


11. Když se program spustí úspěšně, uvidíte ho spustit ke stažení trénování a testování datovou sadu, pak trénování modelu a vaše míra výstupních chyb. Chcete, míra chyb snížení v čase

    ![První výstup z programu mnist ručně Pythonu](media\create-project-repo\tensorflow-mnist-running.png)

> Pokud používáte Anaconda a dojde k chybě o chybějící numpy, budete muset [změnit prostředí Pythonu používat Anaconda](../python/selecting-a-python-environment-for-a-project.md).

11. Můžete sledovat průběh pomocí TensorBoard. Klikněte pravým tlačítkem na projekt a klikněte na tlačítko **TensorBoard spouštět** vyberte adresář výstupu TensorBoard protokoly.

    ![Spustit tensorboard](media\create-project-repo\run-tensorboard.png)

11. Všimněte si, že chyba snížení přesčas, což znamená, že je zlepšit kvalitu

    ![Spustit tensorboard](media\create-project-repo\tensorboard.png)