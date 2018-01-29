---
title: "Možnosti, textový Editor, C#, Upřesnit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Advanced
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- XML documentation, creating
ms.assetid: 947f9d9a-b0f3-408d-9866-d82895bcee31
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 193b61ab95daa84c5815c251c7d52103c88977e1
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/29/2018
---
# <a name="options-text-editor-c-advanced"></a>Možnosti, textový editor, C#, upřesnit
Tento dialog můžete upravit nastavení pro dokumentační komentáře XML, editor formátování a refaktoring kódu pro jazyk C#. Pro přístup k tohoto dialogového okna, klikněte na tlačítko **možnosti** na **nástroje** nabídky, rozbalte **textového editoru** složky, rozbalte položku **C#**a pak klikněte na tlačítko  **Rozšířené**.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="outlining"></a>Sbalování  
 Zadejte popisující režimu při otevírání souborů  
 Při výběru automaticky přehled souboru kódu, který vytvoří sbalitelné bloky kódu. Při prvním otevření souboru #regions bloky a bloky kódu neaktivní sbalte.  
  
## <a name="editor-help"></a>Nápovědy k editoru  
 Underline chyby v editoru  
 Identifikuje chyby sestavení v kódu. Když je vybraná tato možnost, zobrazí se podtržení vlnovkami v barev, které mají zvláštní význam:  
  
-   Chyby analýzy jsou red.  
  
-   Chyby sestavení jsou modrá.  
  
-   Upozornění sestavení jsou zelená.  
  
-   Neplatný [upravit a pokračovat](../../debugger/edit-and-continue.md) úpravy jsou fialové.  
  
Přesuňte ukazatel přes segment podtržené kódu zobrazíte popisek s informace o této chybě.  
  
Zobrazit živé sémantické chyby  
Identifikuje určitým chybám kompilace bez explicitní kompilace, například deklarování a použití Neznámý typ nebo odkazující na Neznámá vlastnost.  
  
Zvýrazněte odkazy na symbolů v místě kurzoru  
Když kurzor je nastavený uvnitř symbol, nebo když klikněte na symbol, jsou vyznačené všechny instance tohoto symbolu v souboru kódu.  
  
## <a name="refactoring"></a>Refaktoring  
 Zkontrolujte výsledky refaktoring  
 Zobrazí **výsledky ověření** dialogové okno při pokusu o refactor kód, který obsahuje chyby sestavení, nebo když refaktoring by způsobilo kód odkaz na vytvořit vazbu na něco jiného než jeho původní vazby.  
  
 Upozornit na členy s kompilátoru generuje odkazy  
 Při pokusu o Refaktorovat člena, který má stejný název jako odkaz kompilátoru generované, zobrazí se dialog s upozorněním.  
  
## <a name="xml-documentation-comments"></a>Dokumentační komentáře XML  
 Generovat dokumentační komentáře XML pro / / /  
 Pokud vybraná, vloží \<souhrnné > začínat a končit značky pro dokumentační komentáře XML automaticky po zadání Úvod / / / komentář. Další informace o dokumentace XML, najdete v části [dokumentační komentáře XML](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments).  
  
## <a name="implement-interface"></a>Implementovat rozhraní  
 Obklopit s #region generovaného kódu  
 Vloží #region \< *název rozhraní*> člen kolem metody, pokud se použije implementovat rozhraní nebo explicitní implementace rozhraní.  
  
## <a name="organize-usings"></a>Uspořádat Using  
 Nejprve umístit direktivy "Systém", pokud řazení direktiv Using  
 Při výběru `System` pomocí direktivy zobrazí před ostatními pomocí direktivy. Další informace najdete v tématu direktiv Using uspořádat v [C# IntelliSense](../../ide/visual-csharp-intellisense.md#automatic-code-generation).  
  
## <a name="see-also"></a>Viz také  
 [Dokumentační komentáře XML](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)   
 [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)   
 [C# IntelliSense](../../ide/visual-csharp-intellisense.md)