---
title: "Možnosti, textový Editor, C#, IntelliSense | Microsoft Docs"
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense
helpviewer_keywords:
- underlines, wavy
- IntelliSense [C#], options
- IntelliSense [C#], wavy underlines
- wavy underlines
- Text Editor Options dialog box, IntelliSense
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 78763e0257334065b1fdbcbcab5f106face20dee
ms.sourcegitcommit: 238cd48787391aa0ed1eb684f3f04e80f7958705
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/12/2018
---
# <a name="options-text-editor-c-intellisense"></a>Možnosti, textový editor, C#, IntelliSense

Použití **IntelliSense** stránka možnosti změnit nastavení, které ovlivňují chování IntelliSense pro jazyk C#. Chcete-li získat přístup k této stránce Možnosti, zvolte **nástroje** > **možnosti**a potom vyberte **textového editoru** > **C#**  >  **IntelliSense**.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

**IntelliSense** možnosti stránka obsahuje následující možnosti:

## <a name="completion-lists"></a>Seznamy dokončení

- Zobrazit seznam dokončení po je zadán znak *

   Pokud je vybraná tato možnost, IntelliSense zobrazí seznam dokončení automaticky při zadávání. Pokud není vybraná tato možnost, je stále k dispozici v doplňování IntelliSense **IntelliSense** nabídky nebo stisknutím kombinace kláves **Ctrl**+**místo**.

- Po odstranění znak zobrazí seznam dokončení

- Zvýraznění odpovídající částí položky seznamu dokončení

- Zobrazit seznam filtrů dokončení

- Zobrazit název návrhy

### <a name="snippets-behavior"></a>Chování fragmenty kódu

- Nikdy nezahrne fragmenty kódu

   Pokud je vybraná tato možnost, IntelliSense nikdy přidá do seznamu dokončení aliasy pro fragmenty kódu v C#.

- Vždy zahrnovat fragmenty kódu

   Pokud je vybraná tato možnost, IntelliSense přidá do seznamu dokončení aliasy pro fragmenty kódu v C#. V případě alias fragmentu kódu je stejný jako klíčové slovo, například [třída](/dotnet/csharp/language-reference/keywords/class), klíčové slovo je nahrazena zástupce. Další informace najdete v tématu [fragmenty kódu v C#](../../ide/visual-csharp-code-snippets.md).

- Zahrnout fragmenty při?-karta je zadán po identifikátor

   Pokud je vybraná tato možnost, IntelliSense Přidá aliasy pro jazyk C# code fragmenty pro dokončení seznamu při **?** + **Kartě** stisknutí po identifikátor

### <a name="enter-key-behavior"></a>Zadejte chování klávesy

- Nikdy přidejte nový řádek na zadejte

   Určuje, že nový řádek nikdy přidán automaticky po výběru položky v seznamu dokončení a stisknutím klávesy **Enter**.

- Přidat nový řádek pouze na zadání po konci plně typové slova

   Určuje, že pokud zadejte všechny znaky pro položku v seznamu dokončení a potom stiskněte klávesu **Enter**, je automaticky přidán nový řádek a kurzor přesune na nový řádek.

   Pokud zadáte například `else` a potom stiskněte klávesu **Enter**, v editoru se zobrazí následující:

   `else`

   `|`(kurzor umístění)

   Ale pokud zadáte pouze `el` a potom stiskněte klávesu **Enter**, v editoru se zobrazí následující:

   `else|`(kurzor umístění)

- Vždy přidejte nový řádek na zadejte

   Určuje, že pokud zadáte *žádné* znaků pro položku v seznamu dokončení a poté stiskněte klávesu **Enter**, je automaticky přidán nový řádek a kurzor přesune na nový řádek.

## <a name="see-also"></a>Viz také

[Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)  
[Používání atributu IntelliSense](../../ide/using-intellisense.md)