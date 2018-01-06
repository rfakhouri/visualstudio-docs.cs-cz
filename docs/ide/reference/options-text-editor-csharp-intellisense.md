---
title: "Možnosti, textový Editor, C#, IntelliSense | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Intellisense
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Intellisense
helpviewer_keywords:
- underlines, wavy
- IntelliSense [C#], options
- IntelliSense [C#], wavy underlines
- wavy underlines
- Text Editor Options dialog box, IntelliSense
ms.assetid: 3466dedb-e5f4-424c-8dd8-e4941b2f4fc2
caps.latest.revision: "25"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: b0b69b7eafbfbb1b5c2c582fd0c734a183ea0a78
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="options-text-editor-c-intellisense"></a>Možnosti, textový editor, C#, IntelliSense
Použití **IntelliSense** stránka vlastností můžete upravit nastavení, které ovlivňují chování IntelliSense pro Visual C#. Dostanete **IntelliSense** stránka vlastností kliknutím **možnosti** na **nástroje** nabídky, pak levým na **C#** v **Textového editoru** složku a potom kliknutím na tlačítko **IntelliSense.**  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
 **IntelliSense** vlastnost stránka obsahuje následující vlastnosti:  
  
## <a name="completion-lists"></a>Seznamy dokončení  
 **Zobrazit seznam dokončení po znak je zadán.**  
 Pokud je vybraná tato možnost, IntelliSense zobrazí seznam dokončení automaticky při zadávání. Pokud není vybraná tato možnost, je stále k dispozici v doplňování IntelliSense **IntelliSense** nabídky nebo stisknutím kombinace kláves CTRL + MEZERNÍK.  
  
 **Seznamy dokončení umístit klíčová slova**  
 Pokud je vybraná tato možnost, IntelliSense přidá klíčová slova jazyka C#, například [třída](/dotnet/csharp/language-reference/keywords/class), do seznamu dokončení.  
  
 **Seznamy dokončení umístit fragmenty kódu**  
 Pokud je vybraná tato možnost, IntelliSense přidá do seznamu dokončení aliasy pro fragmenty kódu v C#. V případě alias fragmentu kódu je stejný jako klíčové slovo, například [třída](/dotnet/csharp/language-reference/keywords/class), klíčové slovo je nahrazena zástupce. Další informace najdete v tématu [fragmenty kódu Visual C#](../../ide/visual-csharp-code-snippets.md).  
  
## <a name="selection-in-completion-lists"></a>Výběr v seznamy dokončení  
 **Potvrzené zadáním následujících znaků:**  
 Určuje všechny znaky, které provést automatické doplňování IntelliSense pro vybranou položku v seznamu dokončení po jejich zadali.  
  
 **Potvrzené stisknutím panelu místa**  
 Určuje zahrnout akce stisknutím panelu místo spuštění automatického dokončování IntelliSense pro vybranou položku v seznamu dokončení.  
  
 **Přidejte nový řádek na zadejte na konci plně typu aplikace word**  
 Určuje, že pokud zadejte všechny znaky pro položku v seznamu dokončení a potom stiskněte klávesu ENTER, se automaticky vytvoří nový řádek, a kurzor přesune na nový řádek.  
  
 Pokud zadáte například `else` a stiskněte klávesu ENTER, zobrazí se následující v editoru:  
  
 `else`  
  
 `|`(kurzor umístění)  
  
 Ale pokud zadáte pouze `el` a stiskněte klávesu ENTER, zobrazí se následující v editoru:  
  
 `else|`(kurzor umístění)  
  
## <a name="intellisense-member-selection"></a>Výběr členů IntelliSense  
 **Předběžné vybere naposledy použité člena**  
 Pokud je vybraná tato možnost, IntelliSense předem vybere členy, kteří nedávno jste vybrali v poli automaticky otevírané okno vypsat členy pro automatické objekt název dokončení během aktuální relace v integrované vývojové prostředí (IDE). Historii naposledy použité členy není zaškrtnuté mezi každou relaci v prostředí IDE. Další informace najdete v tématu [IntelliSense pro naposledy použit členy](../../ide/visual-csharp-intellisense.md#most-recently-used-members).  
  
## <a name="see-also"></a>Viz také  
 [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)   
 [Dokumentační komentáře XML](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)   
 [Používání atributu IntelliSense](../../ide/using-intellisense.md)