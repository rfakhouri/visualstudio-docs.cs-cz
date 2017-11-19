---
title: R Markdownu s R Tools pro sadu Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3ac955b2-b6e1-4d32-b1a4-2882c93311fc
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: e3d9ee899c9ed82cacfd9466412bacfea6b8c5e8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="creating-r-markdown-documents"></a>Vytváření dokumentů R Markdownu

[R Markdownu](https://rmarkdown.rstudio.com/) je dokument formátu, který se zobrazí analýzy v R vysoce kvalitní dokumentů, sestav, prezentací a řídicí panely.

R nástrojů pro Visual Studio (RTVS) poskytuje šablony položky R Markdownu, editor podpory (včetně IntelliSense pro R kódu v editoru) a možnosti generování souboru.

Využití formátu R Markdown:

1. Zavřete Visual Studio.
1. (Pouze jednou) Nainstalujte `pandoc` z [pandoc.org](http://pandoc.org/installing.html).
1. Restartujte Visual Studio, který by měl vyzvednutí pandoc instalace.
1. Nainstalujte `knitr` a `rmarkdown` balíčků, které můžete provést z [interaktivních okna](interactive-repl.md):

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. Vytvoření nového souboru Markdownu R buď pomocí **soubor > Nový** příkazu v nabídce a výběrem **R Markdownu** ze seznamu, nebo kliknutím pravým tlačítkem myši na projekt v Průzkumníku řešení a výběrem **přidat R Markdown** (nebo **Přidat > novou položku...**  a výběrem **R Markdownu** ze seznamu).

1. Výchozí hodnotou tohoto nového souboru jsou následující:

    ~~~markdown
    ---
    title: "Untitled"
    output: html_document
    ---
    
    This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and Microsoft Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.
    
    When you click the **R Tools | Publish | Preview** button a document will be generated that includes both content as well as the output of any embedded R code chunks within the document. You can embed an R code chunk like this:
    
    ```{r}
    summary(cars)
    ```
    
    You can also embed plots, for example:
    
    ```{r, echo=FALSE}
    plot(cars)
    ```
    
    Note that the `echo = FALSE` parameter was added to the code chunk to prevent printing of the R code that generated the plot.
    
    ~~~

1. V průběhu úprav, klikněte pravým tlačítkem v editoru a vyberte **Preview**, který má možnosti jazyka HTML, PDF a Microsoft Word. Z této verze preview můžete uložit soubor jako vhodný pro formát, který jste zvolili.
