---
title: Postup... with textové šablony | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 95ef3440e9b330860c8438b997c9c0e8b3c4fe0c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to--with-text-templates"></a>Postupy pro textové šablony
Textové šablony v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nabízejí praktický způsob generování textu jakéhokoli druhu. Textové šablony můžete použít pro generování textu za běhu v rámci vaší aplikace a v době návrhu k vygenerování některých kódu projektu. Toto téma shrnuje nejčastěji výzva "Jak se dá...?" otázky.  
  
 V tomto tématu jsou více odpovědi, které jsou označeny odrážek alternativní návrhy.  
  
 Obecný úvod do textové šablony, najdete v tématu [generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md).  
  
## <a name="how-to-"></a>Jak...  
  
### <a name="generate-part-of-my-application-code"></a>Generovat součástí kódu aplikace  
 Je nutné konfiguraci nebo *modelu* v souboru nebo v databázi. Jeden nebo více součástí vlastního kódu závisí na tomto modelu.  
  
-   Některé soubory s kódem vygenerujte z textové šablony. Další informace najdete v tématu [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md) a [co je nejlepší způsob, jak zahájit zápis šablonu?](#starting).  
  
### <a name="generate-files-at-run-time-passing-data-into-the-template"></a>Generování souborů za běhu, předávání dat do šablony  
 Moje aplikace za běhu, generuje textových souborů, jako je například sestavy, které obsahují směs standardního textu a data. Chcete se vyhnout psaní stovky `write` příkazy.  
  
-   Textové šablony runtime přidejte do projektu. Tato šablona vytvoří třídu ve vašem kódu, který můžete vytvořit instanci a použít pro vygenerování textu. V parametrech konstruktor můžete předat data do ní. Další informace najdete v tématu [generování textu běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md).  
  
-   Pokud chcete vygenerovat z šablon, které jsou k dispozici pouze v době běhu, můžete použít standardní textové šablony. Pokud píšete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozšíření, můžete vyvolat službu ukázka textu. Další informace najdete v tématu [volání transformací textu v rozšíření VS](../modeling/invoking-text-transformation-in-a-vs-extension.md). V jiných kontextech můžete použít modul ukázka textu. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.TextTemplating.Engine?displayProperty=fullName>.  
  
     Použití \<#@parameter#> direktiva předat parametry do těchto šablon. Další informace najdete v tématu [T4 – direktiva Parameter](../modeling/t4-parameter-directive.md).  
  
### <a name="read-another-project-file-from-a-template"></a>Přečtěte si další soubor projektu ze šablony  
 Načíst soubor ze stejné [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu jako šablonu:  
  
-   Vložit `hostSpecific="true"` do `<#@template#>` – direktiva.  
  
     V kódu, použijte `this.Host.ResolvePath(filename)` získat úplnou cestu k souboru.  
  
### <a name="invoke-methods-from-a-template"></a>Vyvolání metody ze šablony  
 Pokud metody již existují, například ve verzi standard [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] třídy:  
  
-   Použít \<#@assembly#> direktiva k načtení sestavení a použít \<#@import#> nastavit kontext oboru názvů. Další informace najdete v tématu [T4 – Direktiva Import](../modeling/t4-import-directive.md).  
  
     Pokud často používáte stejnou sadu sestavení a importovat direktivy, vezměte v úvahu zápis procesoru direktiv. V každé šabloně můžete vyvolat procesoru direktiv, které lze načíst sestavení a souborů modelu a nastavit kontext oboru názvů. Další informace najdete v tématu [vytváření vlastní T4 Text šablony direktiva procesorů](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
 Pokud píšete metody sami:  
  
-   Pokud píšete textové šablony runtime, zapište definici třídu, která má stejný název jako vaše runtime textové šablony. Přidejte další metody do této třídy.  
  
-   Zápis řídicí blok třída funkce `<#+ ... #>` ve které je možné deklarovat privátní třídy, vlastnosti a metody. Při kompilaci textové šablony je převede na třídu. Bloky standardního ovládacího prvku `<#...#>` text jsou transformovány do jedné metody a třída funkce bloky jsou vloženy jako samostatné členy. Další informace najdete v tématu [řídicí bloky textových šablon](../modeling/text-template-control-blocks.md).  
  
     Metody definované jako třída funkce vytvořit vložený text bloky.  
  
     Zvažte umístění třída funkce do samostatného souboru, který můžete `<#@include#>` do jednoho nebo více souborů šablony.  
  
-   Zápis metod v samostatném sestavení (knihovna tříd) a volat je z šablony. Použití `<#@assembly#>` direktiva k načtení sestavení a `<#@import#>` nastavit kontext oboru názvů. Všimněte si, že chcete-li znovu sestavit sestavení při ladění ho, možná budete muset zastavit a restartovat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [direktivy textových šablon T4](../modeling/t4-text-template-directives.md).  
  
### <a name="generate-many-files-from-one-model-schema"></a>Generovat mnoho souborů ze schématu jeden model.  
 Pokud často generování souborů z modelů, které mají stejné schéma XML nebo databáze:  
  
-   Vezměte v úvahu zápis procesoru direktiv. To umožňuje nahradit více příkazů sestavení a příkazy v každé šabloně s jeden vlastní – direktiva import. Procesoru direktiv můžete také načíst a analyzovat soubor modelu. Další informace najdete v tématu [vytváření vlastní T4 Text šablony direktiva procesorů](../modeling/creating-custom-t4-text-template-directive-processors.md).  
  
### <a name="generate-files-from-a-complex-model"></a>Generování souborů z komplexní model  
  
-   Zvažte vytvoření jazyk specifické pro doménu (DSL) představující model. To usnadňuje mnohem zápisu šablony, protože používáte typy a vlastnosti, které odpovídají názvy elementů v modelu. Nemáte analyzovat soubor nebo přejděte z uzlů XML. Příklad:  
  
     `foreach (Book book in this.Library) { ... }`  
  
     Další informace najdete v tématu [Začínáme s jazyky specifické pro doménu](../modeling/getting-started-with-domain-specific-languages.md) a [generování kódu z jazyka domény](../modeling/generating-code-from-a-domain-specific-language.md).  
  
### <a name="get-data-from-includevsprvscode-qualityincludesvsprvsmdmd"></a>Získání dat z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]  
 Použití služeb, které jsou součástí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], sada `hostSpecific` atribut a zatížení `EnvDTE` sestavení. Příklad:  
  
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
  
-   Další informace najdete v tématu [generování kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md).  
  
## <a name="more-general-questions"></a>Další obecné otázky  
  
###  <a name="starting"></a> Co je nejlepší způsob, jak zahájit zápis textové šablony?  
  
1.  Zápis konkrétní příklad vygenerovaný soubor.  
  
2.  Zapnout do textové šablony vložením `<#@template #>` – direktiva a direktivy a kód potřebné k načtení vstupního souboru nebo model.  
  
3.  Progresivně nahraďte výraz a bloky kódu části souboru.  
  
### <a name="what-is-a-model"></a>Co je "model"?  
  
-   Vstup číst vaše šablona. Může to být v souboru nebo v databázi. To může být XML, nebo výkresu aplikace Visio nebo jazyk specifické pro doménu (DSL) nebo modelu UML nebo může být ve formátu prostého textu. Může možné rozdělit do několika souborů. Obvykle více než jednu šablonu přečte jeden model.  
  
     Z toho vyplývá termín "modelu" je reprezentuje některých aspektů vaší firmy více přímo než kódu generovaného programu nebo jiné soubory. Například je může představovat plán komunikace sítě, která bude dohled nad generovaného softwaru.  
  
### <a name="what-is-the-benefit-of-using-text-templates"></a>Co je výhodou používání textové šablony?  
 Obvykle vygenerujte více kód nebo další soubory z jeden model. Model reprezentuje požadavky přímo než generovaného kódu. Se vynechá podrobnosti implementace a je zapsán z hlediska požadavků na místo kód. Při změně požadavky – stejně jako obvykle – můžete aktualizovat model snadno a spolehlivě než různé části kódu programu.  
  
 Generování kódu je proto cenným nástrojem z perspektivy agilní vývoj metody.  
  
### <a name="what-best-practices-are-there-for-text-templates"></a>Jaké "osvědčené postupy" jsou pro textové šablony?  
  
-   Další informace najdete v tématu [pokyny pro textové šablony T4 zápis](../modeling/guidelines-for-writing-t4-text-templates.md).  
  
### <a name="what-is-t4"></a>Co je "T4"?  
  
-   Jiný název pro [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] text šablony funkce popsané v tomto poli. Předchozí verze, která nebyla publikována, byla zkratkou pro "Transformace šablony textu".
