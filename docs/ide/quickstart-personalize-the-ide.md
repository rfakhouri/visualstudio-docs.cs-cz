---
title: "Nastavit motiv barev a písem v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 369407c70ba15c720af3c92a5fabc56497eeedb6
ms.sourcegitcommit: 1aa9282b1f0bc2795df3264cbd1e331cc44c23f3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/08/2017
---
# <a name="quickstart-personalize-the-visual-studio-ide-and-editor"></a>Rychlý úvod: přizpůsobení Visual Studio IDE a Editor

V tento rychlý start 5 až 10 minut jsme budete přizpůsobit barvu motivu sady Visual Studio a dvě barvy textu v textovém editoru.

## <a name="set-the-color-theme"></a>Nastavit Barva motivu

Výchozí motiv barvu pro Visual Studio 2017 nazývá **Blue**. Nyní změníme jeho **tmavý**.

1. Na řádku nabídek zvolte **nástroje**, **možnosti**.

1. Na **prostředí**, **Obecné** stránka Možnosti, změny **barevný motiv** výběr **tmavý**a potom zvolte **OK** .

   Barva motivu pro celý IDE se změní na **tmavý**.

   ![VS v tmavý motiv](media/quickstart-personalize-dark-theme.png)

> [!TIP]
> Můžete nainstalovat další předdefinované motivy nainstalováním **Visual Studio barvu motivu editoru** z [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.VisualStudio2017ColorThemeEditor). Po instalaci tohoto nástroje se zobrazí další barevné motivy v rozevíracím seznamu Barva motivu.

## <a name="change-text-color"></a>Změna barvy textu

Nyní jsme budete přizpůsobit některé barvy textu pro Editor. První otevřete soubor XML a zobrazí se výchozí barvy.

1. V řádku nabídek zvolte **soubor**, **nový**, **souboru...** .

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

   Všimněte si, že čísla řádků jsou tyrkysová modrou barvu a atributy xml světle modré barvy. Přidáme změnit barvu textu pro tyto položky.

   ![Barvy písma souboru XML](media/quickstart-personalize-xml-file.png)

1. Chcete-li otevřít **možnosti** dialogové okno, z řádku nabídek zvolte **nástroje**, **možnosti**.

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

[Rychlý úvod: první pohled na Visual Studio IDE](../ide/quickstart-ide-orientation.md)  
[Přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md)  
[Vlastní nastavení editoru](../ide/customizing-the-editor.md)  
[Integrované vývojové prostředí sady Visual Studio – přehled](../ide/visual-studio-ide.md)