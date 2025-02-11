---
title: Vytvoření projektu aplikace AI ze šablony
author: lisawong19
ms.author: liwong
manager: routlaw
ms.date: 11/13/2017
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: 0b537d80b8db9150c6804aff2ee3de0e6c879bb9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62546723"
---
# <a name="create-an-ai-project-from-a-template-in-visual-studio"></a>Vytvoření projektu aplikace AI ze šablony v sadě Visual Studio

Jakmile [nainstalované Visual Studio Tools pro AI](installation.md), je snadné vytvořit nový projekt AI pomocí různých šablon.

1. Spusťte sadu Visual Studio.

2. Vyberte **soubor > Nový > projekt** (Ctrl + Shift + N). V **nový projekt** dialogové okno, vyhledejte "**nástroje AI**" a vyberte požadované šablony. Všimněte si, že vyberete šablonu zobrazuje krátký popis co Šablona nabízí.

    ![Dialogové okno Nový projekt VS2017 šablonou Pythonu](media/create-project/new-ai-project.png)

3. Pro účely tohoto rychlého startu vyberte "**TensorFlow aplikace**" šablony, dejte projektu název (například "mnist ručně") a umístění a vyberte **OK**.

4. Visual Studio vytvoří soubor projektu ( `.pyproj` souboru na disku) společně s další soubory, jak je popsáno v šabloně. Projekt se šablonou "TensorFlow aplikace", obsahuje jeden soubor se stejným názvem jako váš projekt. Soubor je otevřen v editoru sady Visual Studio ve výchozím nastavení.

    ![Výsledný projekt při použití šablony aplikace v Pythonu](media/create-project/new-tensorflowapp.png)

5. Všimněte si, že kód již importuje několik knihoven, včetně TensorFlow, numpy, sys a operačního systému. Kromě toho začíná vaše aplikace připravená některé vstupní argumenty snadno povolit přepínání umístění vstupní trénovacích dat, výstupní modely a soubory protokolů. Tyto parametry jsou užitečné, když odešlete své úlohy do více výpočetní kontext (tedy jiný adresář na místním vývojovém pole, než na sdílené složky Azure).

6. Váš projekt má také některé vlastnosti vytvořen k tomu, aby dál ladit vaši aplikaci automaticky předáním argumentů příkazového řádku pro tyto vstupní parametry. **Klikněte pravým tlačítkem myši** projektu vyberte **vlastnosti**

    ![Vlastnosti](media/create-project/project-properties.png)

7. Klikněte na tlačítko **ladění** přidána karta zobrazíte argumenty skriptu. můžete je změnit podle potřeby, kde se vstupní data nachází a kde chcete výstup uložen.

    ![Vlastnosti](media/create-project//project-properties_1.png)

8. Spusťte program stisknutím kombinace kláves Ctrl + F5 nebo výběrem **ladit > Spustit bez ladění** v nabídce. Výsledky se zobrazí v okně konzoly.
