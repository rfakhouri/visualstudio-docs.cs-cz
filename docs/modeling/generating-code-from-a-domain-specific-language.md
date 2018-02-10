---
title: "Generování kódu z jazyka domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: ad823ee772119f6398e47e6df6211360468b13ad
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="generating-code-from-a-domain-specific-language"></a>Vytváření kódu z jazyka specifického pro doménu
Microsoft [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] nabízí efektivní způsob, jak generovat kód, dokumentů, konfigurační soubory a jiné artefakty z dat v modelech. Pomocí [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], můžete vytvořit sadu tříd, které představují data a může zapisovat textové šablony ve třídách jejichž názvy a vlastnosti odrážet tato data.  
  
 Společnost Fabrikam má například soubor XML jména zákazníků a e-mailové adresy. Svého vývojáře vytvořit model, ve kterém je zákazník třídu s názvem vlastnosti a e-mailu. Jejich zápisu několik textové šablony ke zpracování dat, včetně fragment, který vytvoří tabulku všem zákazníkům jako součást stránku HTML:  
  
```  
<table>  
<# foreach (Customer c in ContactList) {  #>  
  <tr><td> <#= c.FullName #> </td>   
      <td> <#= c.EmailAddress #> </td> </tr>  
<# } #>  </table>  
```  
  
 Při zpracování databáze zákazníka soubor XML je načten do úložiště modelu. A *procesoru direktiv*, vytvořené pomocí [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], zpřístupní třídu Customer kód v textové šablony. Mnoho textové šablony můžete spustit na stejné úložiště.  
  
 Textové šablony jsou nezbytné pro [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]. Se používají ke generování zdrojového kódu pro elementy modelu domény, stejně jako VSPackage a ovládacích prvků, které se používají k integraci nástroje s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 Tato část popisuje některé z způsobů, jak vytvářet, upravovat a ladění textové šablony použité v [!INCLUDE[dsl](../modeling/includes/dsl_md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přístup k modelům z textových šablon](../modeling/accessing-models-from-text-templates.md)  
  
 Poskytuje základní informace o odkazující na jazyk specifické pro doménu v textové šablony.  
  
 [Návod: Ladění textové šablony přistupující k modelu](../modeling/walkthrough-debugging-a-text-template-that-accesses-a-model.md)  
  
 Popisuje postup řešení potíží a ladění na textové šablony, která odkazuje na jazyk, specifické pro doménu.  
  
 [Návod: Připojení hostitele k procesoru vygenerovaných direktiv](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)  
  
 Popisuje, jak připojit vlastní hostitel generovaného direktivy procesor.  
  
 [Příkaz DslTextTransform](../modeling/the-dsltexttransform-command.md)  
  
 Popisuje příkazového řádku, které provádí TextTransform spustitelný soubor na příkazovém řádku pro textové šablony, které odkazují na specifické pro doménu jazyky.  
  
## <a name="reference"></a>Odkaz  
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)  
  
 Poskytuje syntaxe direktivy textových šablon a řídicí bloky.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
 Vysvětluje proces transformace textových šablon.  
  
 [Vytvoření kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md)  
  
 Pokud jsou generování souborů z DSL na serveru, sestavení, přečtěte si toto téma.