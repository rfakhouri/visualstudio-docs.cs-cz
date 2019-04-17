---
title: Options, Text Editor, C#, Advanced | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Advanced
- VS.ToolsOptionsPages.Text_Editor.Visual_JSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- outlining options [J#]
- XML documentation, creating
ms.assetid: 947f9d9a-b0f3-408d-9866-d82895bcee31
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ed1260d414c21d40bd0dc57f885cf5996594b7d6
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59664544"
---
# <a name="options-text-editor-c-advanced"></a>Možnosti, textový editor, C#, upřesnit
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Použijte toto dialogové okno Upravit nastavení editoru formátování, refaktoring kódu a dokumentační komentáře XML pro jazyk Visual C#. Toto dialogové okno, klikněte na tlačítko **možnosti** na **nástroje** nabídky, rozbalte **textový Editor** složky, rozbalte **jazyka C#** a potom klikněte na tlačítko  **Pokročilé**.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="outlining"></a>Sbalování  
 Po otevření souborů vstoupit do režimu sbalování  
 Pokud je vybráno, automaticky popisuje, jak soubor kódu, který vytvoří sbalitelnou bloky kódu. Při prvním otevření souboru #regions bloky a bloky neaktivního kódu sbalte.  
  
## <a name="editor-help"></a>Nápověda k editoru  
 Underline chyby v editoru  
 Identifikuje chyby sestavení v kódu. Pokud je vybraná tato možnost, zobrazí se podtržení vlnovkou barvy, které mají zvláštní význam:  
  
- Chyby analýzy jsou červené.  
  
- Chyby sestavení jsou modrá.  
  
- Upozornění sestavení jsou zelená.  
  
- Neplatný [upravit a pokračovat](../../debugger/edit-and-continue.md) úpravy jsou fialový.  
  
  Přesuňte ukazatel nad segmentu podtržené kódu zobrazíte popisek s informacemi o chybě.  
  
  Zobrazit živé sémantické chyby  
  Identifikuje určité chyby při kompilaci bez explicitní kompilace, například, deklarace a používání neznámého typu nebo odkazuje na neznámou vlastnost.  
  
  Zvýrazňovat odkazy na _symbol pod kurzorem  
  Když se kurzor uvnitř symbol, nebo když kliknete na symbol, jsou zvýrazněny všechny instance tohoto symbolu v souboru kódu.  
  
## <a name="refactoring"></a>Refaktoring  
 Zkontrolujte výsledky refaktoring  
 Zobrazí **výsledky ověření** dialogové okno při pokusu o Refaktorovat kód, který obsahuje chyby sestavení, nebo když refaktoring by způsobilo odkaz kód k vytvoření vazby na něco jiného než jeho původní vazby.  
  
 Upozornit na členy s odkazy na generovaný kompilátorem  
 Zobrazí dialogové okno upozornění při pokusu o Refaktorovat člena, který má stejný název jako odkaz na generovaný kompilátorem.  
  
## <a name="xml-documentation-comments"></a>Dokumentační komentáře XML  
 Generování komentářů k dokumentaci XML pro / / / / /  
 Pokud je vybráno, vloží \<summary > počáteční a koncové značky pro dokumentační komentáře XML automaticky po zadání Úvod / / / / / komentář. Další informace o dokumentaci XML, naleznete v tématu [dokumentační komentáře XML](http://msdn.microsoft.com/library/803b7f7b-7428-4725-b5db-9a6cff273199).  
  
## <a name="implement-interface"></a>Implementovat rozhraní  
 Obklopit s #region generovaného kódu  
 Vloží #region \< *název rozhraní*> člen kolem metody, když se implementovat rozhraní nebo implementovat rozhraní explicitně se používá.  
  
## <a name="organize-usings"></a>Uspořádat direktivy using  
 Umístit nejdřív direktivy "System", při řazení direktiv Using  
 Pokud je vybráno, `System` pomocí direktivy zobrazí před dalšími direktiv using. Další informace najdete v tématu [řazení direktiv Using](../../misc/sort-usings.md).  
  
## <a name="see-also"></a>Viz také  
 [Dokumentační komentáře XML](http://msdn.microsoft.com/library/803b7f7b-7428-4725-b5db-9a6cff273199)   
 [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)   
 [Visual C# IntelliSense](../../ide/visual-csharp-intellisense.md)
