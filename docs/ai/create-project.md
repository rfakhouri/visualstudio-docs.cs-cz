---
ms.technology: vs-ai-tools
ms.openlocfilehash: 999e57f9b9b873f44f5a1ef0edac94c7e2b53ac4
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2018
ms.locfileid: "29709359"
---
# <a name="create-an-ai-project-from-a-template-in-visual-studio"></a>Vytvoření projektu AI ze šablony v sadě Visual Studio

Jakmile jste [nainstalované Visual Studio Tools pro AI](installation.md), je snadné vytvořit nový projekt AI pomocí různých šablon.

1. Spusťte sadu Visual Studio.

1. Vyberte **soubor > Nový > projekt** (Ctrl + Shift + N). V **nový projekt** dialogové okno, vyhledejte "**AI nástroje**" a vyberte požadované šablony. Všimněte si, že výběrem šablony zobrazuje krátký popis co Šablona nabízí.

    ![Dialogové okno Nový projekt VS2017 pomocí šablony Python](media\create-project\new-ai-project.png)

1. Tento rychlý start, vyberte "**TensorFlow aplikace**" šablony, přiřaďte projektu umístění a název (například "MNIST") a vyberte **OK**.

1. Visual Studio vytvoří soubor projektu ( `.pyproj` soubor na disku) společně s dalšími soubory podle šablony. Projekt se šablonou "TensorFlow aplikace", obsahuje jeden soubor se stejným názvem jako projektu. Soubor je otevřen v editoru Visual Studio ve výchozím nastavení.

    ![Výsledný projektu při použití šablony aplikace Python](media\create-project\new-tensorflowapp.png)

1. Všimněte si, že kód importuje již několik knihoven, včetně TensorFlow, numpy, sys a operačního systému. Kromě začíná vaší aplikace připravené některé vstupní argumenty snadno povolit přepínání umístění vstupní Cvičná data, výstup modely a soubory protokolu. Tyto parametry jsou užitečné při odesílání vašeho úloh do více výpočetní kontexty (ie jiný adresář na místním dev pole, než ve sdílené složce Azure).

1. Projekt má také některé vlastnosti k vytvoření, která usnadňují ladění aplikace pomocí automaticky předání argumentů příkazového řádku tyto vstupní parametry. **Klikněte pravým tlačítkem na** projektu zvolte **vlastnosti**

    ![Vlastnosti](media\create-project\project-properties.png)

1. Klikněte **ladění** automaticky zjistit argumenty skriptu přidat. můžete je změnit podle potřeby a kde se vstupní data nachází kam chcete výstupu uložené.

    ![Vlastnosti](media\create-project\/project-properties_1.png)

1. Spusťte program stisknutím Ctrl + F5 nebo výběrem **ladění > Spustit bez ladění** v nabídce. Výsledky jsou zobrazeny v okně konzoly.
