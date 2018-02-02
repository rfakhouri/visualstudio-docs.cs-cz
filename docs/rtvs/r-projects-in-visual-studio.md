---
title: Projekty v R Tools pro Visual Studio | Microsoft Docs
description: "Postup vytvoření správce R projekty v sadě Visual Studio, včetně vlastnosti, příkazy projektu a šablony."
ms.custom: 
ms.date: 06/29/2017
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
ms.openlocfilehash: f201eb31f907e8cacf6453651927e5639462e1c3
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/01/2018
---
# <a name="creating-r-projects-in-visual-studio"></a>Vytváření projektů R v sadě Visual Studio

Projekt R ( `.rxproj` souboru) identifikuje všechny zdroje a soubory obsahu přidružené k projektu. Také obsahuje informace o sestavení pro každý soubor, udržuje informace o integraci se systémy správy zdrojového kódu a umožňuje uspořádat do logických součástí vaší aplikace. Informace týkající se pracovní prostor např. seznam nainstalovaných balíčků, ale je zachován odděleně, v pracovním prostoru sám sebe.

Projekty jsou vždy spravované v rámci sady Visual Studio *řešení*, která může obsahovat libovolný počet projekty, které může odkazovat navzájem. V tématu [použít více typů projektu v sadě Visual Studio](#use-multiple-project-types-in-visual-studio).

## <a name="creating-a-new-r-project"></a>Vytvoření nového projektu R

1. Spuštění sady Visual Studio.
1. Zvolte **soubor > Nový > projekt...** (Ctrl+Shift+N)
1. Vyberte z v části "R projekt" **šablony > R**, název a umístění poskytnout projekt a vyberte **OK**:

    ![Dialogové okno Nový projekt pro R v sadě Visual Studio (RTVS v VS2017)](media/getting-started-01-new-project.png)

Tento příkaz vytvoří projekt s prázdnou `script.R` soubor otevřete v editoru. Všimněte si také v **Průzkumníku řešení** existují dva další soubory v projektu:

![Obsah projektu R vytvořené ze šablony](media/projects-template-results.png)

`.Rhistory` Zaznamenává ať příkazy, které zadáte do [R interaktivní](interactive-repl-for-r-in-visual-studio.md) okno. Můžete otevřít okno vyhrazené historie s **R nástroje > Windows > Historie** příkaz. Toto okno obsahuje položky panelu nástrojů tlačítko a kontext nabídky vymazat obsah historie.

`rproject.rproj` Souboru udržuje určitá nastavení projektu specifické R, které jinak nejsou spravovány nástrojem Visual Studio:

| Vlastnost | Výchozí | Popis |
| --- | --- | --- |
| Version | 1.0 | Použít verze R nástrojů pro Visual Studio a vytvořte tak projekt. |
| RestoreWorkspace | Výchozí | Automaticky načíst předchozí proměnné pracovního prostoru z `.RData` soubor v adresáři projektu. |
| SaveWorkspace | Výchozí | Aktuální pracovní prostor proměnné, které chcete uložit `.RData` soubor v adresáři projektu při zavření projektu. |
| AlwaysSaveHistory | Výchozí | Uložit aktuální historie interaktivních okna `.RHistory` soubor v adresáři projektu při zavření projektu. |
| EnableCodeIndexing | Ano | Určuje, jestli se má spouštět indexování úlohy pro rychlejší hledání kódu na pozadí. |
| UseSpacesForTab | Ano | Určuje, zda se mají vkládat mezery (Ano) nebo znaku tabulátoru (ne) při stisknutí klávesy Tab v editoru. |
| NumSpacesForTab | 2 | Počet mezer vkládaných Pokud UseSpacesForTab kladná. |
| Kódování | UTF-8 | Výchozí kódování pro `.R` soubory. |
| RnwWeave | Sweave | Balíček pro použití při tkaní Rnw souboru. |
| LaTeX | pdfLaTeX | Knihovnu, která má použít při převodu RMarkdwon do PDF. |

### <a name="converting-a-folder-of-files-to-an-r-project"></a>Převádění složku souborů do projektu R

Pokud máte existující složky `.R` soubory, které chcete spravovat v projektu, proveďte následující kroky:

1. Vytvořte nový projekt v sadě Visual Studio jako v předchozí části.
1. Zkopírujte soubory do složky projektu.
1. V Průzkumníku řešení Visual Studio klikněte pravým tlačítkem na projekt, vyberte **Přidat > ukončení položky**a přejděte k souborům, které chcete přidat. Tyto soubory se zobrazí ve vašem projektu stromu po výběru **OK**.
1. Chcete-li uspořádat kódu do podsložky, klikněte pravým tlačítkem na projekt, vyberte možnost **Přidat > novou složku** nejdřív poté zkopírujte soubory do této složky a přidat tyto existujících položek v kroku 3.

## <a name="project-properties"></a>Vlastnosti projektu

K otevření stránek vlastností projektu, klikněte pravým tlačítkem na projekt v **Průzkumníku řešení** a vyberte **vlastnosti**, nebo vyberte **Projekt > vlastnosti (název projektu)...*  položku nabídky. Otevřeném okně se zobrazí vlastnosti projektu:

| Tabulátor | Vlastnost | Popis |
| --- | --- | --- |
| Spustit | Spuštění souboru | Název souboru, který se spouští s **zdrojový soubor spouštěcí** příkazu, F5, **ladění > Spustit ladění**, nebo **ladění > Spustit bez ladění**. Pravým tlačítkem myši na soubor v projektu a výběrem **nastavit jako spouštěcí R skript** také nastaví jej jako spouštěcí soubor. |
| | Resetování R interaktivní při spuštění | Vymaže všechny proměnné z pracovního prostoru interaktivních okna při spuštění projektu. Učinit Ano záruky existuje není žádný obsah zbytkové prostoru z zkontrolují spustí. |
| | Cesta vzdálené projektu | Cesta k vzdáleného pracovního prostoru. |
| | Přenos souborů při spuštění | Určuje, zda soubory projektu, podstoupí filtru v **souborů k přenosu**, jsou zkopírovány do vzdálené pracovní prostor se každé spuštění. |
| | Soubory pro přenos | Názvy souborů a zástupné znaky označující konkrétní soubory zkopírovat do vzdáleného pracovního prostoru, pokud **přenos souborů při spuštění** je vybrána. |
| Nastavení | (Soubor Settings.R) | Nastavení projektu R pocházet z `Settings.R` nebo `*.Settings.R` soubory, které se nacházejí v projektu. Pokud není dostupný žádný soubor nastavení, můžete přidat proměnné, uložte na stránce a výchozí `Settings.R` soubor se vytvoří pro vás. Můžete také přidat soubor nastavení projektu prostřednictvím **soubor > Přidat novou položku...*  příkazu nabídky. <br/> Nastavení se ukládají jako kód R a souboru můžete použít jako zdroj před spuštěním z ostatních modulů, proto předem vyplní prostředí s předdefinovanými nastaveními. |

## <a name="r-specific-project-commands"></a>Příkazy specifické pro R projektu

Projekty Visual Studio podporují počet obecné příkazů pomocí místní nabídky a **projektu** nabídky. Podrobnosti na tyto obecné možnosti najdete v tématu [řešení a projektů v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md). Mějte na paměti, ale který 

R nástrojů pro Visual Studio (RTVS) přidá počet vlastní příkazy v nabídce klikněte pravým tlačítkem na projekt R a také soubory nebo složky v projektu.

| Příkaz | Popis |
| --- | --- |
| Sada zde pracovní adresář | Nastaví R interaktivních okna pracovní adresář ke složce projektu, který můžete také použít na všechny podsložky v rámci projektu. |
| Otevřít složku | Otevře Průzkumníka Windows v umístění vybraného souboru. | 
| Přidat skript jazyka R | Vytvoří a otevře se nové `.R` soubor s názvem výchozí. Můžete také **Přidat > novou položku...**  příkaz pro vytvoření `.R` soubory a také řadu dalších typů souborů. V tématu [šablon položek specifické R](#r-specific-item-templates). |
| Přidat R Markdownu | Vytvoří a otevře se nové `.rmd` dokument s výchozím názvem. Můžete také **Přidat > novou položku...**  příkaz pro vytvoření `.rmd` soubory a také řadu dalších typů souborů. V tématu [šablon položek specifické R](#r-specific-item-templates).  | 
| Publikování uložené procedury | Spustí se proces publikování všechny uložené procedury obsažené v skripty R. V tématu [práci s SQL serverem uložené procedury](integrating-sql-server-with-r.md#working-with-sql-server-stored-procedures). | 

## <a name="r-specific-item-templates"></a>Šablony položek specifické R

RTVS obsahuje několik šablon pro konkrétní typy souborů. Přístup k šablony kliknete pravým tlačítkem na projekt R a výběrem **Přidat > novou položku...** , výběrem **Projekt > Přidat novou položku...** , nebo pomocí **soubor > Nový > soubor...**  a výběrem **R** kartě. Je nejlepší způsob, jak prozkoumat šablonu pro vytvoření nového projektu a vkládání souborů každého typu.

> [!Note]
> **Přidat > novou položku...**  příkazy také zobrazit typy obecné souborů, které nejsou uvedené v tabulce; s **soubor > Nový > soubor...**  tyto typy jsou obsaženy místo toho na **Obecné** kartě.

| Typ souboru | Popis |
| --- | --- |
| Skript jazyka R | Textový soubor obsahující stejné příkazy, které lze zadat na příkazovém řádku R. |
| R Markdownu | Soubor obsahující [Markdownu R](rmarkdown-with-r-in-visual-studio.md) dokumentu. |
| Nastavení R | Soubor, který obsahuje nastavení aplikace R. | 
| Dokumentace R | Obecný soubor dokumentace R obsahující pouze název, alias a názvu pole. |
| R dokumentace (Function) | Soubor dokumentace R obsahující mnoho polí s komentáři k popisu funkce. |
| R dokumentace (datové sady) | Soubor dokumentace R obsahující mnoho polí s komentáři k popisu datové sady. |
| Dotaz SQL | A prázdný `.sql` souboru. V tématu [systému SQL Server integration](integrating-sql-server-with-r.md). |
| Uložená procedura s R | Souboru R podřízené dotazu SQL a podřízené uložené procedury souboru šablony. V tématu [systému SQL Server integration](integrating-sql-server-with-r.md). |

## <a name="use-multiple-project-types-in-visual-studio"></a>Použití více typy projektů v sadě Visual Studio

Řešení sady Visual Studio poskytují vhodné místo k shromáždění a spravovat související projekty v jednom místě logické. Řešení pomoct chránit váš kód uspořádány a umožňuje spolupráci v rámci týmů.

V následujícím příkladu obsahuje řešení projektu R se model sestavuje pomocí R a Azure Machine Learning, projekt Python, scikit další, obsahující moduly pro náročné výpočetní pracovní projektu jazyka C++, projektu SQL pro správu dat a Python nebo Bottle projekt pro web, který publikuje výsledek:

![Visual Studio Průzkumník řešení zobrazující více souvisejících projekty v řešení](media/projects-polyglot.png)

Projekt zvýrazněná s tučné písmo je "počáteční" projekt pro řešení; Chcete-li ji změnit, klikněte pravým tlačítkem myši na jiný projekt a vyberte **nastavit jako spouštěný projekt**.

> [!Note]
> V současné době není k dispozici žádné explicitní R C# nebo integrace jazyka C++ na místě (protože je pro Python, najdete v části [vytváření rozšíření pro C++ pro jazyk Python](../python/working-with-c-cpp-python-in-visual-studio.md)).  Ale nejsou k dispozici, které poskytují c a C++ mostů pro R. knihovny

Další informace o obecně řízení projektů a řešení najdete v tématu [řešení a projektů v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md).
