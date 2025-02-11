---
title: Jak textové šablony | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: d1ac2509-0479-47eb-809c-1f171245d0b6
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9c31e1d17137fd0e801bb506c280a83285c311b4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68181576"
---
# <a name="how-to--with-text-templates"></a>Postupy pro textové šablony
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Textové šablony v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nabízejí praktický způsob generování textu jakéhokoli druhu. Textové šablony můžete použít ke generování textu za běhu v rámci vaší aplikace a v době návrhu k vygenerování nějakých kód projektu. Toto téma obsahuje souhrn nejčastěji dotaz "Jak na to...?" dotazy.  
  
 V tomto tématu jsou více odpovědí, které předchází odrážky alternativní návrhy.  
  
 Obecný úvod do textové šablony, najdete v článku [generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md).  
  
## <a name="how-to-"></a>Jak...  
  
### <a name="generate-part-of-my-application-code"></a>Generovat část kódu své aplikace sám  
 Mám konfiguraci nebo *modelu* v souboru nebo v databázi. Jeden nebo více částí kódu závisí na modelu.  
  
- Generovat některé soubory kódu z textových šablon. Další informace najdete v tématu [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md) a [co je nejlepší způsob, jak začít psát šablonu?](#starting).  
  
### <a name="generate-files-at-run-time-passing-data-into-the-template"></a>Generování souborů za běhu, předávání dat do šablony  
 Moje aplikace v době běhu generuje textové soubory, jako je například sestavy, které obsahují kombinaci standardního textu a data. Chcete se vyhnout psaní stovky `write` příkazy.  
  
- Přidejte textové šabloně běhu do projektu. Tato šablona vytvoří třídu ve vašem kódu, který můžete vytvořit instanci a použít k vygenerování textu. Data můžete předat do ní parametry konstruktoru. Další informace najdete v tématu [generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
- Pokud chcete generovat z šablon, které jsou k dispozici pouze v době běhu, můžete použít standardní textových šablon. Pokud píšete [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] rozšíření, můžete vyvolat službu šablonování textu. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md). V jiných kontextech můžete použít modul šablon textu. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>.  
  
     Použití \<#@parameter#> směrnice pro předání parametrů do těchto šablon. Další informace najdete v tématu [T4 – direktiva Parameter](../modeling/t4-parameter-directive.md).  
  
### <a name="read-another-project-file-from-a-template"></a>Přečtěte si jiný soubor projektu ze šablony  
 Ke čtení souboru z dané [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projektu jako šablony:  
  
- Vložit `hostSpecific="true"` do `<#@template#>` směrnice.  
  
     Ve vašem kódu, použijte `this.Host.ResolvePath(filename)` získat úplnou cestu k souboru.  
  
### <a name="invoke-methods-from-a-template"></a>Vyvolání metody ze šablony  
 Pokud metody ještě neexistuje, například ve standardním [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] třídy:  
  
- Použít \<#@assembly#> direktiva načíst sestavení a používání \<#@import#> Chcete-li nastavit obor názvů kontextu. Další informace najdete v tématu [T4 – Direktiva Import](../modeling/t4-import-directive.md).  
  
   Často používají stejnou sadu sestavení, direktivy import, zvažte vytvoření procesor direktiv. V každé šabloně můžete vyvolat procesor direktiv, který lze načíst sestavení a soubory modelu a nastavte kontext oboru názvů. Další informace najdete v tématu [vytváření vlastních procesorů textových šablon T4 – direktiva](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
  Pokud píšete metody sami:  
  
- Při psaní textové šabloně běhu zapište definice částečné třídy, který má stejný název jako textové šabloně běhu. Přidejte další metody této třídy.  
  
- Zápis řídicí blok funkce třídy `<#+ ... #>` ve které je možné deklarovat soukromé třídy, vlastnosti a metody. Při kompilaci textové šablony se transformuje na třídu. Standardní řídicí bloky `<#...#>` textu se transformují do jedné metody a bloky s funkcí třídy jsou vloženy jako samostatné členy. Další informace najdete v tématu [řídicí bloky textových šablon](../modeling/text-template-control-blocks.md).  
  
   Metody definované funkce třídy mohou také obsahovat vložený textové bloky.  
  
   Zvažte umístění funkce třídy v samostatném souboru, který můžete `<#@include#>` do jednoho nebo více souborů šablon.  
  
- Zápis metod v samostatném sestavení (knihovna tříd) a je volat z vaší šablony. Použití `<#@assembly#>` směrnice pro načtení sestavení, a `<#@import#>` nastavit kontext oboru názvů. Všimněte si, že pokud chcete při ladění ji, sestavte znovu sestavení, budete muset zastavit a restartovat [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Další informace najdete v tématu [direktivy textové šablony T4](../modeling/t4-text-template-directives.md).  
  
### <a name="generate-many-files-from-one-model-schema"></a>Generovat ze schématu jeden model mnoho souborů  
 Pokud často generování souborů z modelů, které mají stejné schéma XML nebo databáze:  
  
- Zvažte vytvoření procesor direktiv. To umožňuje nahradit více příkazů sestavení a příkazy v každé šabloně s jeden vlastní direktivy importu. Procesoru direktiv můžete také načíst a analyzovat soubor modelu. Další informace najdete v tématu [vytváření vlastních procesorů textových šablon T4 – direktiva](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
### <a name="generate-files-from-a-complex-model"></a>Generování souborů z komplexní model  
  
- Zvažte vytvoření jazyka specifického pro doménu (DSL) k vyjádření modelu. To usnadňuje mnohem zápisu šablon, protože používají typy a vlastnosti, které obsahují názvy elementů v modelu. Nemáte k analýze souboru či přejděte z uzlů XML. Příklad:  
  
     `foreach (Book book in this.Library) { ... }`  
  
     Další informace najdete v tématu [Začínáme s jazyky specifickými pro doménu](../modeling/getting-started-with-domain-specific-languages.md) a [generování kódu z jazyka specifického pro doménu](../modeling/generating-code-from-a-domain-specific-language.md).  
  
- Vezměte v úvahu generování kódu z modelu UML. Kód nemusí přímo odráží UML. Například nemáte generování třídy pro každou třídu modelu UML. Místo toho může pomocí diagramu tříd UML představující webovou stránku a generovat webovou stránku z každou třídu modelu UML. Zvolte typ diagramu, který je nejblíž k vašim potřebám. Například zvolte diagramy činnosti k reprezentaci libovolného typu pracovní postup. Můžete definovat Stereotypy se přidat informace, které jsou vhodné pro vaši aplikaci pro každý typ elementu.  
  
     Generování z modelu UML umožňuje nakreslit a upravit model ve formě graficky, ale bez nutnosti návrhu vlastní typ diagramu, stejně jako s DSL.  
  
     Další informace najdete v tématu [vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md) a [generování souborů z modelu UML](../modeling/generate-files-from-a-uml-model.md).  
  
### <a name="get-data-from-includevsprvsincludesvsprvs-mdmd"></a>Získání dat z [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]  
 Použití služby poskytované v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], sada `hostSpecific` atribut a zatížení `EnvDTE` sestavení. Příklad:  
  
```csharp  
<#@ template hostspecific="true" language="C#" #>  
<#@ output extension=".txt" #>  
<#@ assembly name="EnvDTE" #>  
<#  
  IServiceProvider serviceProvider = (IServiceProvider)this.Host;  
  EnvDTE.DTE dte = (EnvDTE.DTE) serviceProvider.GetService(typeof(EnvDTE.DTE));  
#>  
  
Number of projects in this VS solution:  <#= dte.Solution.Projects.Count #>  
  
```  
  
### <a name="execute-text-templates-in-the-build-process"></a>Spuštění textové šablony v procesu sestavení  
  
- Další informace najdete v tématu [generování kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md).  
  
## <a name="more-general-questions"></a>Další obecné otázky  
  
### <a name="starting"></a> Co je nejlepší způsob, jak zahájit zápis textové šablony?  
  
1. Zápis konkrétní příklad generovaného souboru.  
  
2. Vložíte-li ho Změníme na textové šablony `<#@template #>` směrnice a direktivy a kódu, které jsou nutné k načtení vstupní soubor nebo model.  
  
3. Postupně nahraďte část souboru výraz a bloky kódu.  
  
### <a name="what-is-a-model"></a>Co je "model"?  
  
- Vstup přečtený ve vaší šabloně. To může být v souboru nebo v databázi. Může být XML, nebo výkresu Visia nebo jazyka specifického pro doménu (DSL) nebo modelu UML a může to být prostý text. Může být rozděleny mezi několik souborů. Obvykle více než jedna šablona načte jeden model.  
  
     Nepřímo "model" je, že představuje určitý aspekt vaši firmu víc přímo do kódu generovaného programu nebo jiné soubory. Například to může představovat plánu komunikace sítě, která dohlíží generované softwaru.  
  
### <a name="what-is-the-benefit-of-using-text-templates"></a>Co je výhodou použití textových šablon?  
 Obvykle generovat více kódu nebo jiných souborů z jednoho modelu. Model představuje požadavky přímo než generovaného kódu. Vynechá podrobnosti implementace a je napsán z hlediska požadavků, nikoli kódu. Při změně požadavků – stejně jako obvykle – můžete aktualizovat modelu jednodušší a spolehlivější než jiné části programového kódu.  
  
 Generování kódu je proto cenným nástrojem z hlediska metod agilního vývoje.  
  
### <a name="what-best-practices-are-there-for-text-templates"></a>Co "doporučené" jsou pro textové šablony?  
  
- Další informace najdete v tématu [pokyny pro textové šablony T4 zápis](../modeling/guidelines-for-writing-t4-text-templates.md).  
  
### <a name="what-is-t4"></a>Co je "T4"?  
  
- Jiný název [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] zde popsané funkce šablony textu. Předchozí verze, která nebyla publikována, je zkratkou pro "Transformace textové šablony".
