---
title: Klonování úložiště
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: 73f1595e0e6c8f182f0bedcece51011390964ed2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62539616"
---
# <a name="clone-a-repository-of-python-code-in-visual-studio"></a>Naklonujte úložiště kódu v Pythonu v sadě Visual Studio

Jakmile [nainstalované Visual Studio Tools pro AI](installation.md), můžete snadno naklonujte úložiště kódu v Pythonu a vytvoření projektu z něj.

1. Pro připojení k úložištím GitHub, spusťte instalační program sady Visual Studio, vyberte **změnit**a vyberte **jednotlivé komponenty** kartu. Přejděte dolů k položce **kódu nástroje** vyberte **rozšíření GitHub pro Visual Studio**a vyberte **změnit**.

    ![Výběr GitHub extension v instalačním programu sady Visual Studio](media/create-project-repo/installation-github-extension.png)

2. Spusťte sadu Visual Studio.

3. Vyberte **zobrazení > Průzkumník týmových projektů** otevřít **Team Exploreru** okno, ve kterém můžete připojit ke Githubu nebo Azure DevOps nebo klonování úložiště.

    ![Okno Průzkumníka týmu zobrazující Azure DevOps, Githubu a klonování úložiště](media/create-project-repo/team-explorer-devops.png)

4. Do pole Adresa URL v části **místní úložiště Git**, zadejte `https://github.com/Microsoft/samples-for-ai`zadejte složky pro klonované soubory a vyberte **klonování**.

    > [!Tip]
    > Složka, kterou zadáte v Průzkumníku týmových projektů je konkrétní složky pro klonované soubory příjem. Na rozdíl od `git clone` příkazu, vytváření v Team Exploreru klonu neprovádí automatické vytváření podsložku s názvem úložiště.

5. Při klonování je hotové, klikněte dvakrát na složku úložiště v dolní části Průzkumníku týmových projektů přejděte na řídicí panel úložiště. V části **řešení**vyberte **nový**.

    ![Okno Průzkumníka týmu, vytvoření nového projektu z klonu](media/create-project-repo/team-explorer-new-project.png)

6. V **nový projekt** dialogové okno, které se zobrazí, vyberte "**z existujícího kódu Pythonu**", zadejte název projektu, nastavte **umístění** do stejné složky jako úložiště, a Vyberte **OK**. V průvodci, který se zobrazí, vyberte **Dokončit**.

7. Vyberte **zobrazení > Průzkumník řešení** z nabídky.

8. V Průzkumníku řešení rozbalte `TensorFlow Examples> MNIST` uzel, klikněte pravým tlačítkem na `convolutional.py`a vyberte **nastavit jako spouštěcí soubor**. Tento krok informuje soubor, který by měl použít při spuštění projektu sady Visual Studio.

9. Stisknutím klávesy **Ctrl**+**F5** nebo vyberte **ladit > Spustit bez ladění** ke spuštění programu. Pokud se zobrazí chyba, zkontrolujte nastavení pracovního adresáře v předchozím kroku.

10. Když se program spustí úspěšně, uvidíte ho spustit ke stažení trénování a testování datovou sadu, pak trénování modelu a vaše míra výstupních chyb. Chcete, míra chyb snížení v čase

    ![První výstup z programu mnist ručně Pythonu](media/create-project-repo/tensorflow-mnist-running.png)

   > [!NOTE]
   > Pokud používáte Anaconda a dojde k chybě o chybějící numpy, budete muset [změnit prostředí Pythonu používat Anaconda](../python/selecting-a-python-environment-for-a-project.md).

11. Můžete sledovat průběh pomocí TensorBoard. Klikněte pravým tlačítkem na projekt a klikněte na tlačítko **TensorBoard spouštět** vyberte adresář výstupu TensorBoard protokoly.

   ![Spustit tensorboard](media/create-project-repo/run-tensorboard.png)

12. Všimněte si, že chyba snížení přesčas, což znamená, že zlepšení kvality.

   ![Spustit tensorboard](media/create-project-repo/tensorboard.png)
