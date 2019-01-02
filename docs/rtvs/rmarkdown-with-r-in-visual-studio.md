---
title: R Markdown
description: Jak vytvořit R Markdown dokumenty v sadě Visual Studio k vytvoření vysoce kvalitní sestavy, prezentace a řídicí panely.
ms.date: 11/16/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 6394dcedc8c29f517d502d1a4e5475667f9b1f9f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938469"
---
# <a name="create-r-markdown-documents"></a>Vytváření dokumentů R Markdown

[R Markdown](https://rmarkdown.rstudio.com/) je formát dokumentu, který převede analýzy v jazyce R na vysoce kvalitní dokumenty, sestavy, prezentace a řídicí panely.

Nástroje R pro Visual Studio (RTVS) obsahuje šablonu položky R Markdown, editor podporují (včetně technologie IntelliSense pro kód jazyka R v editoru), možnosti generování souboru a živá ve verzi preview.

## <a name="using-r-markdown"></a>Použití R Markdown

1. Zavřete Visual Studio.
1. (Pouze jednou) Nainstalujte `pandoc` z [pandoc.org](http://pandoc.org/installing.html).
1. Restartujte sadu Visual Studio, který by měl instalace pandocu vyzvednutí.
1. Nainstalujte `knitr` a `rmarkdown` balíčky, které lze provádět z [interaktivní okno](interactive-repl-for-r-in-visual-studio.md):

    ```R
    install.packages("knitr")
    install.packages("rmarkdown")

    ```
1. Vytvořit nový soubor R Markdown pomocí **souboru** > **nový** > **souboru** příkaz nabídky a vyberete **R**  >  **R Markdown** ze seznamu. V kontextu projektu, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a vyberte **přidat R Markdown** (nebo **přidat** > **nová položka** a vyberete **R Markdown** ze seznamu).

1. Výchozí obsah nového souboru jsou následující:

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

Visual Studio 2017 verze 15.5 nebo novější automaticky poskytují dynamický náhled R Markdown. Chcete-li zapnout automatickou synchronizaci mezi editoru a náhled, vyberte **nástroje R** > **Markdownu** > **Automatická synchronizace** ( **CTRL**+**Shift**+**Y**). Pokud nepoužíváte automatické synchronizace, můžete aktualizovat pomocí verze preview **nástroje R** > **Markdownu** > **znovu načíst náhled Markdownu R**.

Můžete také zobrazit náhled souboru ve formátu HTML, PDF, Microsoft Word a formáty a v editoru pravým tlačítkem a výběrem jedné z **ve verzi Preview** příkazy. Stejné příkazy jsou také k dispozici na **nástroje R** > **Markdownu** nabídky. (V dřívějších verzích sady Visual Studio se našly tyto příkazy na **nástroje R** > **publikovat** nabídky.)

![Dynamický náhled RMarkdown a dalších příkazů nabídky ve verzi preview](media/rmarkdown-live-preview.png)
