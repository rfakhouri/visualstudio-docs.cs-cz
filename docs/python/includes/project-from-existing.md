---
ms.topic: include
ms.openlocfilehash: 37079cfaa1204cd8ce7a77e1e2f5aa91ea844ea5
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38809415"
---
1. Spusťte sadu Visual Studio a vyberte **soubor > Nový > projekt**.

1. V **nový projekt** dialogové okno, vyhledejte "Python", vyberte šablonu "Z kódu Pythonu existující", dejte projektu název a umístění a vyberte **OK**.

1. V průvodci, který se zobrazí nastavení cesty k váš stávající kód, nastavte filtr pro typy souborů a zadejte všechny cesty pro hledání, které vyžaduje váš projekt a pak vyberte **Další**. Pokud si nejste jisti, jaké vyhledávací cesty, ponechte toto pole prázdné.

    ![Nový projekt z existujícího kódu, krok 1](../media/projects-from-existing-1.png)

1. V dalším dialogovém okně vyberte spouštěcí soubor projektu a vyberte **Další**. (V případě potřeby vyberte některé prostředí; v opačném případě přijměte výchozí hodnoty.) Všimněte si, že dialogové okno zobrazuje pouze soubory v kořenové složce; Pokud je soubor, který chcete v podsložce, nechte prázdné spouštěcí soubor a nastavte ho později v Průzkumníku řešení (popsaných níže).

    ![Nový projekt z existujícího kódu, krok 2](../media/projects-from-existing-2.png)

1. Vyberte umístění, do kterého chcete uložit soubor projektu (což je `.pyproj` souboru na disku). Pokud je k dispozici, můžete také zahrnout automatické zjišťování virtuálních prostředí a přizpůsobit projekt pro jiné webové rozhraní. Pokud si nejste jisti z těchto možností, nechte je nastavena na výchozí hodnoty.

    ![Nový projekt z existujícího kódu, krok 3](../media/projects-from-existing-3.png)

1. Vyberte **Dokončit** a sady Visual Studio vytvoří projekt a otevře jej v Průzkumníku řešení. Pokud chcete přesunout `.pyproj` souboru jinde, vyberte ho v Průzkumníku řešení a zvolte **soubor > Uložit jako**. Tato akce aktualizuje odkazy na soubory v projektu, ale nepřesouvá soubory kódu.

1. Pokud chcete nastavit různé spouštěcí soubor, vyhledejte soubor v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **nastavit jako spouštěcí soubor**.