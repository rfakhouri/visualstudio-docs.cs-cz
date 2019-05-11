---
title: Sada barevný motiv a písem
ms.date: 11/20/2017
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eccbc834f4038ec18c2f84244488b81a59ecbfbf
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531563"
---
# <a name="personalize-the-visual-studio-ide-and-editor"></a>Přizpůsobení integrovaného vývojového prostředí sady Visual Studio a Editor

V tomto kurzu 5 až 10 minut přizpůsobíme barevný motiv sady Visual Studio tak, že vyberete tmavý motiv. Přizpůsobíme také barvy pro dva různé typy textu v textovém editoru.

::: moniker range="vs-2017"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) stránku a nainstalovat zdarma.

::: moniker-end

::: moniker range=">=vs-2019"

Pokud jste ještě nenainstalovali aplikaci Visual Studio, přejděte [soubory ke stažení Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) stránku a nainstalovat zdarma.

::: moniker-end

## <a name="set-the-color-theme"></a>Nastavit barevný motiv

Výchozí barevný motiv uživatelského rozhraní sady Visual Studio se nazývá **modré**. Změňme ji na **tmavě**.

1. Na panelu nabídek, které, jako je na řádku nabídek **souboru** a **upravit**, zvolte **nástroje** > **možnosti**.

1. Na **prostředí** > **Obecné** stránka Možnosti, změna **barevný motiv** výběru **tmavě**a klikněte na tlačítko **OK**.

   Barva motivu pro celý vývojové prostředí (IDE) sady Visual Studio se změní na **tmavě**.

   ::: moniker range="vs-2017"

   ![Visual Studio 2017 v tmavém motivu](media/quickstart-personalize-dark-theme.png)

   ::: moniker-end

   ::: moniker range="vs-2019"

   ![Visual Studio 2019 v tmavém motivu](media/vs-2019/dark-theme.png)

   ::: moniker-end

> [!TIP]
> Můžete nainstalovat další předdefinované motivy nainstalováním **Editor motivů sady Visual Studio** z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor). Po instalaci tohoto nástroje, další barevné motivy joinkind **barevný motiv** rozevíracího seznamu.

## <a name="change-text-color"></a>Změna barvy textu

Nyní přizpůsobíme některé barvy textového editoru. Nejprve vytvoříme nový soubor XML, chcete-li zobrazit výchozí barvy.

1. Na panelu nabídek zvolte **souboru** > **nový** > **souboru**.

1. V **nový soubor** dialogovém okně **Obecné** kategorie, zvolte **soubor XML**a klikněte na tlačítko **otevřít**.

1. Vložte následující kód XML pod řádkem, který obsahuje `<?xml version="1.0" encoding="utf-8"?>`.

   ```xml
   <Catalog>
     <Book id="bk101">
     <Author>Garghentini, Davide</Author>
     <Title>XML Developer's Guide</Title>
     <Genre>Computer</Genre>
     <Price>44.95</Price>
     <PublishDate>2000-10-01</PublishDate>
     <Description>
       An in-depth look at creating applications with XML.
     </Description>
   </Book>
   <Book id="bk102">
     <Author>Garcia, Debra</Author>
     <Title>Midnight Rain</Title>
     <Genre>Fantasy</Genre>
     <Price>5.95</Price>
     <PublishDate>2000-12-16</PublishDate>
     <Description>
       A former architect battles corporate zombies, an evil
       sorceress, and her own childhood to become queen of the world.
     </Description>
   </Book>
   </Catalog>
   ```

   Všimněte si, že jsou čísla řádku tyrkysová modrou barvu a atributy XML (například `id="bk101"`) jsou světle modrou barvou. Chceme změnit barvu textu pro tyto položky.

   ![Barvy písma souboru XML](media/quickstart-personalize-xml-file.png)

1. Chcete-li otevřít **možnosti** dialogového okna zvolte **nástroje** > **možnosti** z řádku nabídek.

1. V části **prostředí**, zvolte **písma a barvy** kategorie.

   Všimněte si, že text pod **zobrazit nastavení pro** říká **textový Editor**&mdash;Toto je chceme. Rozbalte rozevíracího seznamu právě zobrazíte rozsáhlý seznam míst, kde můžete přizpůsobovat písma a barvy textu.

1. Chcete-li změnit barvu textu čísla řádku, v **zobrazení položek** klikněte na položku **číslo řádku**. V **popředí položky** zvolte **Olivově**.

   ![Dialogové okno Možnosti, písma a barvy kategorie](media/quickstart-personalize-line-number-color.png)

   Některé jazyky mají své vlastní zvláštní nastavení písma a barvy. Pokud jste vývojář C++ a chcete změnit barvu použitou pro funkce, například můžete vyhledat **funkcí jazyka C++** v **zobrazení položek** seznamu.

1. Předtím, než jsme ukončit dialogové okno, můžeme také změnit barvu atributy ve formátu XML. V **zobrazení položek** seznamu, přejděte dolů k položce **atribut XML** a vyberte ji. V **popředí položky** zvolte **Limetkově**. Zvolte **OK** naše výběr uložte a zavřete dialogové okno.

   Čísla řádků jsou nyní oliv barvu a atributy XML jsou jasně, Limetkově zelená. Pokud otevřete jiný typ souboru, například soubor kódu jazyka C++ nebo C#, uvidíte, že čísla řádků se zobrazí také v oliv barvu.

   ![Soubor XML s novou barvy písma](media/quickstart-personalize-xml-file-new-colors.png)

Prozkoumali jsme pár způsoby přizpůsobení barev v sadě Visual Studio. Doufáme, že vám ukážeme si některé další možnosti vlastního nastavení v **možnosti** dialogové okno, aby skutečně sada Visual Studio vlastní.

## <a name="see-also"></a>Viz také:

- [Přizpůsobení editoru](../ide/how-to-change-text-case-in-the-editor.md)
- [Integrované vývojové prostředí sady Visual Studio – přehled](../get-started/visual-studio-ide.md)