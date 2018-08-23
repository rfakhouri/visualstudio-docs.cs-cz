---
title: Generování kódu z jazyka specifického pro doménu | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3706cc9-2afd-456a-a879-68425a248ebc
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 3fbe7e40a277174eb556a61b50eb88279adebfb2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669901"
---
# <a name="generating-code-from-a-domain-specific-language"></a>Vytváření kódu z jazyka specifického pro doménu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [generování kódu z jazyka specifického pro doménu](https://docs.microsoft.com/visualstudio/modeling/generating-code-from-a-domain-specific-language).  
  
Microsoft [!INCLUDE[dsl](../includes/dsl-md.md)] poskytuje efektivní způsob, jak generovat kód, dokumenty, konfigurační soubory a další artefakty z dat ve modely. Pomocí [!INCLUDE[dsl](../includes/dsl-md.md)], můžete vytvořit sadu tříd, které představují data a můžete napsat textové šablony v třídách názvy a vlastnosti odrážet tato data.  
  
 Třeba společnost Fabrikam má soubor XML jména zákazníka a e-mailové adresy. Jejich vývojáři vytvářet model, ve kterém je zákazník třídu s názvem vlastnosti a e-mailu. Zapisují několik textových šablon ke zpracování dat, včetně tento fragment, který vytvoří tabulku ze všech zákazníků jako součást stránky HTML:  
  
```  
<table>  
<# foreach (Customer c in ContactList) {  #>  
  <tr><td> <#= c.FullName #> </td>   
      <td> <#= c.EmailAddress #> </td> </tr>  
<# } #>  </table>  
```  
  
 Při zpracování databáze zákazníka, je do úložiště modelu čtení souboru XML. A *procesor direktiv*, které byly vytvořeny pomocí [!INCLUDE[dsl](../includes/dsl-md.md)], zpřístupní třídu Customer kód v textové šabloně. Mnoho šablon textu je možné spustit na stejné úložiště.  
  
 Textové šablony jsou nezbytné k [!INCLUDE[dsl](../includes/dsl-md.md)]. Používají se k vygenerování zdrojového kódu pro elementy modelu domény stejně jako u sady VSPackage a ovládací prvky, které se používají k integraci nástroje s [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
 Tato část popisuje některé ze způsobů, jak vytvořit, upravit a ladění textové šablony používané [!INCLUDE[dsl](../includes/dsl-md.md)].  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přístup k modelům z textových šablon](../modeling/accessing-models-from-text-templates.md)  
  
 Poskytuje základní informace o odkazech jazyka specifického pro doménu v textových šablonách.  
  
 [Návod: Ladění textové šablony přistupující k modelu](../modeling/walkthrough-debugging-a-text-template-that-accesses-a-model.md)  
  
 Popisuje postup řešení potíží a ladění textové šablony, který odkazuje na jazyka specifického pro doménu.  
  
 [Návod: Připojení hostitele k procesoru vygenerovaných direktiv](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)  
  
 Popisuje postup připojení vlastního hostitele k procesoru vygenerovaných direktiv.  
  
 [Příkaz DslTextTransform](../modeling/the-dsltexttransform-command.md)  
  
 Popisuje souboru příkazů, které provádí TextTransform spustitelný soubor na příkazovém řádku pro textové šablony, které odkazují na jazyky specifickými pro doménu.  
  
## <a name="reference"></a>Odkaz  
 [Zápis textové šablony T4](../modeling/writing-a-t4-text-template.md)  
  
 Poskytuje syntaxi direktivy textové šablony a řídicí bloky.  
  
## <a name="related-sections"></a>Související oddíly  
 [Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
 Tento článek vysvětluje proces transformace textových šablon.  
  
 [Vytvoření kódu v procesu sestavení](../modeling/code-generation-in-a-build-process.md)  
  
 Přečtěte si toto téma, pokud jsou generování souborů z DSL na serveru sestavení.



