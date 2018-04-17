---
title: Fragmenty kódu pro R
description: Fragmenty kódu pro R v sadě Visual Studio poskytují zástupce rychle vložit bloky kódu o libovolné délce, pomoci vyhnout se opakovaně přepisování podobný kód.
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- devlang-r
dev_langs:
- R
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 43227c0d8181202f0bb7a8794397271aa293aa89
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu v sadě Visual Studio poskytují zástupce rychle vložit bloky kódu o libovolné délce, pomoci vyhnout se opakovaně přepisování podobný kód. Kolekce Visual Studio přidat desítek užitečné fragmenty R R nástrojů pro Visual Studio (RTVS).

Pokud chcete vložit fragment, typ zkrácený název fragmentu kódu (IntelliSense je zadáno), pak stiskněte klávesu Tab, vložit.

Příklady jednoduchých:

- typ `=` pak kartě a RTVS rozšíří jeho `<-` operátor přiřazení.
- typ `>` pak kartě a RTVS rozšíří ji `%>%` operátor kanálu.

Fragmenty kódu může být mnohem víc než jenom znak dokončení znaků. Fragment kódu pro čtení souboru CSV se `read.csv` funkce, například zbavit můžete z si museli pamatovat názvy nebo parametry:

![Animace vložit volání read.csv pomocí fragmentu kódu](media/code-snippet-expansion.gif)

V takovém případě při psaní `readc`, IntelliSense zobrazí seznam dokončení. Výběrem tohoto dokončení v rozevíracím seznamu a stisknutím klávesy Tab vybere `readc`, a stisknutím klávesy Tab rozšíří fragmentu. (Z tohoto důvodu rozšíření fragmentu kódu je často představit jako "typ fragmentu a dvakrát stiskněte klávesu TAB"). Ve většině případů první kartě dokončí výběr IntelliSense a druhé kartě aktivuje rozšíření.

Chcete-li zobrazit všechny dostupné fragmenty kódu, otevřete **nástroje > Správce fragmentů kódu...**  dialogové okno (Ctrl + K, B) a vyberte **R** pro **jazyk**. Skupiny rozbalte a vyberte jednotlivé fragmenty zobrazíte popis a text klávesové:

![Dialogové okno fragmenty kódu pro R](media/code-snippet-dialog.png)

Chcete-li vytvořit vlastní kód fragmenty, postupujte podle pokynů na [návod: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md). Nakonec fragmentu kódu je právě soubor XML. Například následující kód je fragment kódu pro operaci kanálu (zástupce `>`):

```xml
<?xml version="1.0" encoding="utf-8" ?>
<CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>Dplyr pipe</Title>
      <Shortcut>&gt;</Shortcut>
      <Description>Code snippet for '%&gt;%' operator</Description>
      <Author>Microsoft Corporation</Author>
      <SnippetTypes>
        <SnippetType>Expansion</SnippetType>
       </SnippetTypes>
    </Header>
    <Snippet>
      <Code Language="R">
        <![CDATA[ %>% $end$]]>
      </Code>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```

Soubory XML pro všechny fragmenty kódu jsou nainstalovány s RTVS; **umístění** pole **Správce fragmentů kódu** poskytuje cestu. Můžete také najít ve zdrojovém kódu RTVS na Githubu v části [src/balíček/Impl/fragmenty](https://github.com/Microsoft/RTVS/tree/master/src/Package/Impl/Snippets).
