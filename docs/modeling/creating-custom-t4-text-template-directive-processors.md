---
title: "Vytváření vlastních T4 Text šablony procesory direktiv | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: text templates, custom directive processors
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: fe637b6ae730cf70113abda14fad794c30868242
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="creating-custom-t4-text-template-directive-processors"></a>Vytváření vlastních procesorů pro direktivy textových šablon T4
*Proces transformace textových šablon* trvá *textové šablony* souboru jako vstup a vytváří textový soubor jako výstup. *Text šablony transformační modul* proces a modul komunikuje se službou hostitele transformace textových šablon a textové šablony jeden nebo více ovládacích prvků *procesory direktiv* k dokončení proces. Další informace najdete v tématu [proces transformace textových šablon](../modeling/the-text-template-transformation-process.md).  
  
 Vytvoření vlastního procesoru direktiv, vytvořte třídu, která dědí z buď <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> nebo <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>.  
  
 Rozdíl mezi tyto dva je, že <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> implementuje minimální rozhraní, které jsou nezbytné k získávání parametrů od uživatele a ke generování kód, který vytvoří výstup souboru šablony. <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>implementuje vyžaduje/poskytuje vzoru návrhu. <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>zpracovává dva speciální parametry `requires` a `provides`.  Například může vlastního procesoru direktiv přijmout názvu souboru od uživatele, otevřete a čtení tohoto souboru a potom uložte text tohoto souboru do proměnné s názvem `fileText`. Podtřídou třídy <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor> třída může trvat názvu souboru od uživatele jako hodnotu `requires` parametrů a názvu proměnné, do které chcete uložit text jako hodnotu `provides` parametr. Tento procesor by otevřít a čtení tohoto souboru a potom uložte text souboru v zadané proměnné.  
  
 Před voláním vlastního procesoru direktiv z textové šablony v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], je nutné zaregistrovat.  
  
 Další informace o tom, jak přidat klíč registru najdete v tématu [nasazení procesor – direktiva vlastní](../modeling/deploying-a-custom-directive-processor.md).  
  
## <a name="custom-directives"></a>Vlastní direktivy  
 Vlastní – Direktiva vypadá takto:  
  
 `<#@ MyDirective Processor="MyDirectiveProcessor" parameter1="value1" ... #>`  
  
 Vlastního procesoru direktiv můžete použít, když chcete přistupovat k externím datům nebo prostředky z textové šablony.  
  
 Různé textové šablony můžete sdílet funkce, která poskytuje jeden procesor direktiv, takže procesory direktiv poskytnout způsob, jak Multi-Factor kód pro opakované použití. Integrované `include` – direktiva je podobný, protože se používají k zohlednit si kód a jejich sdílení mezi různé textové šablony. Rozdíl je, že všechny funkce, která `include` – direktiva poskytuje je pevná a nepřijímá žádné parametry. Pokud chcete poskytovat běžné funkce textové šablony a povolit šablonu, kterou chcete předat parametry, je nutné vytvořit vlastního procesoru direktiv.  
  
 Některé příklady vlastní procesory direktiv může být:  
  
-   Procesoru direktiv vrátit data z databáze, která přijímá jako parametry uživatelské jméno a heslo.  
  
-   Procesoru direktiv otevřít a přečíst si soubor, který přijímá název souboru jako parametr.  
  
### <a name="principal-parts-of-a-custom-directive-processor"></a>Hlavní součástí vlastního procesoru direktiv  
 K vývoji procesoru direktiv, je nutné vytvořit třídu, která dědí z buď <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> nebo <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>.  
  
 Nejdůležitější `DirectiveProcessor` se tyto metody, které je nutné implementovat.  
  
-   `bool IsDirectiveSupported(string directiveName)`-Návratový `true` Pokud vaše procesoru direktiv můžete řešit s názvem direktivu.  
  
-   `void ProcessDirective (string directiveName, IDictionary<string, string> arguments)`-Šablony modul volá tuto metodu pro každý výskyt – direktiva v šabloně. Procesor měli uložit výsledky.  
  
 Po všechna volání ProcessDirective() zavolá modul ukázka těchto metod:  
  
-   `string[] GetReferencesForProcessingRun()`-Vrátí názvy sestavení, které vyžaduje kód šablony.  
  
-   `string[] GetImportsForProcessingRun()`-Vrátí obory názvů, který lze použít v kód šablony.  
  
-   `string GetClassCodeForProcessingRun()`-Návratový kód metody, vlastnosti a další deklarace, které můžete použít kód šablony. Nejjednodušší způsob je vytvořit řetězec obsahující C# nebo kód jazyka Visual Basic. Chcete-li vaše procesoru direktiv schopná volaná ze šablony, která používá žádný jazyk CLR, může vytvořit příkazy jako strom CodeDom a vrátit výsledek serializaci stromu v jazyce použitém šablonou.  
  
-   Další informace najdete v tématu [návod: vytvoření vlastní – direktiva procesor](../modeling/walkthrough-creating-a-custom-directive-processor.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Nasazení vlastního procesoru direktiv](../modeling/deploying-a-custom-directive-processor.md)  
 Vysvětluje, jak zaregistrovat vlastního procesoru direktiv.  
  
 [Návod: Vytvoření vlastního procesoru direktiv](../modeling/walkthrough-creating-a-custom-directive-processor.md)  
 Popisuje postup vytvoření vlastního procesoru direktiv, jak zaregistrovat a otestovat procesoru direktiv a způsob formátování výstupní soubor ve formátu HTML.