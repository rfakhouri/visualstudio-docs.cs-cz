---
title: Nastavit motiv barev a písem v sadě Visual Studio
ms.date: 11/20/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 56d40211b7d69d46bfbb24f6c1e0de8855809cda
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-personalize-the-visual-studio-ide-and-editor"></a>Rychlý úvod: Přizpůsobení Editor a Visual Studio – sada IDE

V tento rychlý start 5 až 10 minut jsme budete přizpůsobit barvu motivu sady Visual Studio a barvy textu v **textového editoru**.

Pokud jste ještě nenainstalovali Visual Studio, přejděte k [Visual Studio stáhne](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs) stránky instalaci zdarma.

## <a name="set-the-color-theme"></a>Nastavit Barva motivu

Výchozí motiv barvu pro Visual Studio 2017 nazývá **Blue**. Nyní změníme jeho **tmavý**.

1. Na řádku nabídek zvolte **nástroje** > **možnosti**.

1. Na **prostředí** > **Obecné** stránka Možnosti, změny **barevný motiv** výběr **tmavý**a potom vyberte **OK**.

   Barva motivu pro celý IDE se změní na **tmavý**.

   ![VS v tmavý motiv](media/quickstart-personalize-dark-theme.png)

> [!TIP]
> Můžete nainstalovat další předdefinované motivy nainstalováním **Visual Studio barvu motivu editoru** z [Visual Studio marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor). Po instalaci tohoto nástroje se zobrazí další barevné motivy v **barevný motiv** rozevíracího seznamu.

## <a name="change-text-color"></a>Změna barvy textu

Nyní jsme budete přizpůsobit některé barvy textu pro Editor. První otevřete soubor XML a zobrazí se výchozí barvy.

1. V řádku nabídek zvolte **soubor** > **nový** > **soubor**.

1. V **nový soubor** dialogovém **Obecné** kategorie, zvolte **souboru XML**a potom zvolte **otevřete**.

1. Vložte následující kód pod řádek, který obsahuje XML `<?xml version="1.0" encoding="utf-8"?>`.

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

   Všimněte si, že čísla řádků jsou tyrkysová modrou barvu a atributy XML světle modré barvy. Přidáme změnit barvu textu pro tyto položky.

   ![Barvy písma souboru XML](media/quickstart-personalize-xml-file.png)

1. Chcete-li otevřít **možnosti** dialogové okno Vyberte **nástroje** > **možnosti** z řádku nabídek.

1. V části **prostředí**, vyberte **písma a barev** kategorie.

   Všimněte si, že text v rámci **zobrazit nastavení pro** uvádí **textového editoru**&mdash;je to, co chceme. Může rozbalte rozbalovací seznam právě pro rozsáhlé seznamu míst, kde můžete přizpůsobit písma a barvy.

1. Chcete-li změnit barvu textu čísla řádku, v **zobrazení položek** vyberte **číslo řádku**. V **popředí položky** vyberte **olivového**.

   ![Dialogové okno Možnosti, kategorie písma a barev](media/quickstart-personalize-line-number-color.png)

   Některé jazyky mají své vlastní konkrétní nastavení písma a barev. Pokud jste vývojář C++ a chcete změnit barvu použitou pro funkce, například můžete vyhledat **funkcí jazyka C++** v **zobrazení položek** seznamu.

1. Před jsme ukončit dialogové okno, můžeme také změnit barvu atributy XML. V **zobrazení položek** seznamu, přejděte dolů k položce **atribut XML** a vyberte ho. V **popředí položky** vyberte **vápna**. Zvolte **OK** naše výběr uložte a zavřete dialogové okno.

   Čísla řádků jsou nyní oliv barvy a atributy XML jasné, vápna zeleně. Pokud otevřete jiný typ souboru, např. soubor kódu C++ nebo C# uvidíte, že čísla řádků se zobrazí také v oliv barvu.

   ![Soubor XML s novou barvy písma](media/quickstart-personalize-xml-file-new-colors.png)

Jsme prozkoumali jenom několik způsobů přizpůsobení barev v sadě Visual Studio. Doufáme, že budete prozkoumat další možnosti přizpůsobení v **možnosti** dialogové okno, a vytvořit tak Visual Studio vlastní.

## <a name="see-also"></a>Viz také

- [Rychlý úvod: První pohled na Visual Studio IDE](../ide/quickstart-ide-orientation.md)
- [Rychlý úvod: Kódování v editoru](../ide/quickstart-editor.md)
- [Rychlý úvod: Projekty a řešení](../ide/quickstart-projects-solutions.md)
- [Přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)
- [Přizpůsobení editoru](../ide/customizing-the-editor.md)
- [Integrované vývojové prostředí sady Visual Studio – přehled](../ide/visual-studio-ide.md)
