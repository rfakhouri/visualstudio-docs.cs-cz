---
title: R Markdownu s R Tools pro sadu Visual Studio | Microsoft Docs
description: "Postup vytvoření R Markdownu dokumenty v sadě Visual Studio k vytvoření vysoce kvalitní sestav, prezentací a řídicí panely."
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: d81d6e8e21631062b7e66bc7f2437819d3488dd3
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="creating-r-markdown-documents"></a>Vytváření dokumentů R Markdownu

[R Markdownu](https://rmarkdown.rstudio.com/) je dokument formátu, který se zobrazí analýzy v R vysoce kvalitní dokumentů, sestav, prezentací a řídicí panely.

R Tools pro Visual Studio (RTVS) poskytuje šablony položky R Markdownu, editor podporují (včetně IntelliSense pro R kódu v editoru), možnosti generování souboru a live preview.

## <a name="using-r-markdown"></a>Pomocí Markdownu R

1. Zavřete Visual Studio.
1. (Pouze jednou) Nainstalujte `pandoc` z [pandoc.org](http://pandoc.org/installing.html).
1. Restartujte Visual Studio, který by měl vyzvednutí pandoc instalace.
1. Nainstalujte `knitr` a `rmarkdown` balíčků, které můžete provést z [interaktivních okna](interactive-repl-for-r-in-visual-studio.md):

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. Vytvoření nového souboru Markdownu R pomocí **soubor > Nový > soubor** příkazu v nabídce a výběrem **R > R Markdownu** ze seznamu. V kontextu projektu, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a vyberte **přidat Markdownu R** (nebo **Přidat > novou položku...**  a výběrem **R Markdownu** ze seznamu).

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

## <a name="previews"></a>Preview verze

Visual Studio 2017 verze 15,5 a novější automaticky získávat živém náhledu pro R Markdownu. Chcete-li zapnout automatickou synchronizaci mezi editoru a ve verzi preview, vyberte **R nástroje > Markdown > automatické synchronizace** (Ctrl + Shift + Y). Pokud nepoužíváte automatické synchronizace, můžete obnovit pomocí preview **R nástroje > Markdown > Náhled Markdownu R opětovného načtení**.

Můžete také zobrazit náhled souboru ve formátu HTML, PDF, a aplikace Microsoft Word formátuje v editoru pravým tlačítkem myši a výběrem jedné z **Preview** příkazy. Stejné příkazy jsou také k dispozici na **R nástroje > Markdown** nabídky. (V dřívějších verzích sady Visual Studio tyto příkazy se nacházejí na **R nástroje > Publikovat** nabídky.)

![RMarkdown živém náhledu a další příkazy nabídky preview](media/rmarkdown-live-preview.png)
