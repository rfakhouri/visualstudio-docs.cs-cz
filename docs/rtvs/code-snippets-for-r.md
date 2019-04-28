---
title: Fragmenty kódu pro R
description: Fragmenty kódu pro R v sadě Visual Studio poskytují zástupce pro rychlé vkládání bloky kódu libovolné délky, což pomáhá vyhnout se pořád dokola přepisování podobný kód.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: 05a21da94dd643b04cea94b7840ca26d9379cb5a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62969441"
---
# <a name="code-snippets"></a>Fragmenty kódu

Fragmenty kódu v sadě Visual Studio poskytují zástupce pro rychlé vkládání bloky kódu libovolné délky, což pomáhá vyhnout se pořád dokola přepisování podobný kód. Nástroje R pro Visual Studio (RTVS) přidejte desítky užitečné fragmenty kódu R do kolekce Visual Studio.

Chcete-li vložit fragment kódu, typ zkrácený název fragmentu kódu (je k dispozici technologie IntelliSense), stiskněte klávesu **kartu** pro vložení.

Několik jednoduchých příkladů:

- typ `=` Tab a RTVS rozbalí `<-` operátor přiřazení.
- typ `>` Tab a RTVS rozbalí `%>%` operátor kanálu.

Fragmenty kódu může být mnohem víc než jenom znak konce znaků. Fragment kódu pro čtení souboru CSV s `read.csv` funkce, například můžete snížit vás nebudou muset pamatovat názvy nebo parametry:

![Animace dvojice použitím fragment kódu pro vložení volání read.csv](media/code-snippet-expansion.gif)

V takovém případě při psaní `readc`, IntelliSense zobrazí seznam pro doplňování. Výběrem tohoto dokončení v rozevíracím seznamu a stisknutím klávesy **kartu** vybere `readc`a stisknutím klávesy **kartu** znovu rozbalí fragmentu kódu. (Z tohoto důvodu rozšíření fragment kódu je často představit jako "zadejte fragment kódu a dvakrát stiskněte klávesu TAB"). Ve většině případů na první kartě dokončí výběr IntelliSense a druhá karta se rozšíření aktivuje.

Chcete-li zobrazit všechny dostupné fragmenty kódu, otevřete **nástroje** > **Správce fragmentů kódů** dialogové okno (**Ctrl**+**K**,**B**) a vyberte **R** pro **jazyka**. Rozbalte skupinu a vyberte jednotlivé fragmenty kódu popis a zástupce textu:

![Dialogové okno fragmenty kódu pro R](media/code-snippet-dialog.png)

K vytvoření vlastních fragmentech kódu, postupujte podle pokynů na [názorný postup: Vytvoření fragmentu kódu](../ide/walkthrough-creating-a-code-snippet.md). Nakonec fragment kódu je právě soubor XML. Například následující kód je fragment kódu pro operace kanálu byla (místní `>`):

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

Soubory XML pro všechny fragmenty kódu se instalují s RTVS; **umístění** pole **Správce fragmentů kódů** poskytuje cestu. Můžete také najít ve zdrojovém kódu na Githubu v rámci RTVS [src/balíček/Impl/fragmentů](https://github.com/Microsoft/RTVS/tree/master/src/Package/Impl/Snippets).
