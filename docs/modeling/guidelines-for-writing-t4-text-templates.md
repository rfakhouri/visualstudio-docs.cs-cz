---
title: Pokyny pro tvorbu textových šablon T4 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 4438bacd59eb0552521024de712b6d6989af8b19
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="guidelines-for-writing-t4-text-templates"></a>Pokyny pro tvorbu textových šablon T4
Tato obecná pravidla mohou být užitečné, pokud chcete generovat kód programu nebo jiných prostředků aplikace v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Jsou nejsou pevně pravidla.  
  
## <a name="guidelines-for-design-time-t4-templates"></a>Pokyny pro šablony T4 návrhu  
 Šablony T4 návrhu jsou šablony, které generují kód v vaší [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu v době návrhu. Další informace najdete v tématu [vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md).  
  
 Generovat proměnné aspektů aplikace.  
 Je nejvhodnější pro aplikace, která může změnit během projektu, nebo se změní mezi různými verzemi aplikace tyto aspekty generování kódu. Oddělte tyto proměnné aspekty z více invariantní aspekty, aby mohla snadněji určit, co má být vygenerován. Například pokud vaše aplikace obsahuje webovou stránku, samostatné stránce standardní obsluhující funkce z logiky, která definuje navigační cesty z jedné stránky na jiný.  
  
 Zakódujte proměnné aspekty v jedné nebo více zdrojových modelů.  
 Model je soubor nebo databáze, který čte každé šabloně získat konkrétní hodnoty pro proměnné části kódu, který se má vytvořit. Modely se databáze, soubory XML vlastní návrh, diagramy nebo jazyky specifické pro doménu. Jeden model se obvykle používá ke generování v mnoha souborech [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projektu. Každý soubor se vygeneroval ze samostatné šablony.  
  
 Můžete vytvořit více než jeden model v projektu. Například můžete třeba definovat model pro navigaci mezi webové stránky a samostatné model pro rozložení stránky.  
  
 Model se zaměřit na potřeb uživatelů a termínů, nikoli na implementaci.  
 V aplikaci webu, kterou byste očekávali modelu, který má odkazovat na webové stránky a hypertextové odkazy.  
  
 V ideálním případě zvolte formu prezentace, které vyhovuje druh informací, který představuje modelu. Model navigační cesty webového serveru může být například diagram polí a šipky.  
  
 Otestujte generovaného kódu.  
 Ověřte, že výsledný kód funguje jako uživatelé vyžadují pomocí manuální nebo automatizované testy. Nedošlo ke generování testů ze stejného modelu, ze které se generuje kód.  
  
 V některých případech obecné testy lze provést na modelu přímo. Můžete například napsat test, který zajistí, že každé stránky na webu dosažitelný z navigační z žádné jiné.  
  
 Povolit pro vlastní kód: generování částečné třídy.  
 Povolit pro kód, který můžete zapsat ručně kromě do generovaného kódu. Neobvyklé, že schéma generování kódu být schopni účet pro všechny možné změny, které by mohly nastat. Proto byste měli očekávat přidání k nebo přepsání některé generovaného kódu. Kde generovaného materiálu je v jazyce .NET, jako [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], dvě strategie jsou obzvláště užitečná:  
  
-   Vygenerované třídy by měl být částečné. Umožňuje přidání obsahu do generovaného kódu.  
  
-   Třídy by měl být vygenerován v párech, jednu, která dědí z jiných. Základní třída by měla obsahovat všechny vygenerované metody a vlastnosti a odvozené třídy musí obsahovat pouze konstruktory. To umožňuje ručně psané kódu generovaného metod přepsat.  
  
 V jiných generovaného jazyků, například XML, použijte `<#@include#>` – direktiva aby jednoduché kombinace rukou a generovaného obsahu. Ve složitějších případech můžete chtít zápisu následného zpracování krok, který kombinuje vygenerovaný soubor s ručně psané soubory.  
  
 Přesuňte běžné materiálu do zahrnout soubory nebo šablony běhu  
 Pokud chcete vyhnout, opakování podobné bloky textu a kódu ve více šablonách, použijte `<#@ include #>` – direktiva. Další informace najdete v tématu [T4 – direktiva zahrnují](../modeling/t4-include-directive.md).  
  
 Můžete také vytvořit spuštění textové šablony v samostatných projektu a potom je volat z návrhu šablony. Chcete-li to provést, použijte `<#@ assembly #>` – direktiva přístup k samostatné projektu. Příklady najdete v tématu ["Dědičnosti v textové šablony" v blogu Gareth Petr](http://go.microsoft.com/fwlink/?LinkId=208373).  
  
 Zvažte přesunutí velké bloky kódu do samostatné sestavení.  
 Pokud máte velké kód bloky a bloky funkce třídy, může být užitečné přesunout některé tento kód do metody, které zkompilujete v samostatných projektu. Můžete použít `<#@ assembly #>` – direktiva získat přístup ke kódu v šabloně. Další informace najdete v tématu [T4 – Direktiva Assembly](../modeling/t4-assembly-directive.md).  
  
 Metody můžete umístit do abstraktní třída, která může dědit vlastnosti šablony. Abstraktní třída musí dědit z <xref:Microsoft.VisualStudio.TextTemplating.TextTransformation?displayProperty=fullName>. Další informace najdete v tématu [T4 – direktiva Template](../modeling/t4-template-directive.md).  
  
 Generování kódu, není konfigurační soubory  
 Jedna z metod zápis proměnné aplikace je napsat kód obecné program, který přijímá konfigurační soubor. Aplikace napsané tímto způsobem je velmi flexibilní a můžete překonfigurovat, pokud obchodní požadavky změnit bez nutnosti opětovného sestavení aplikace. Z nevýhod tohoto přístupu je ale, že aplikace bude provádět menší také než více konkrétní aplikace. Také jeho kód programu bude obtížné číst a spravovat, částečně, protože má vždy jak nakládat s nejvíce obecné typy.  
  
 Naopak může být silného typu aplikace, jejichž proměnné části jsou generovány před kompilace. Díky tomu je mnohem jednodušší a spolehlivější a napsat kód, ručně psané integrovat do vygenerovaného součástí softwaru.  
  
 Pokud chcete získat úplné výhodou generování kódu, pokuste se generovat kód programu místo konfigurační soubory.  
  
 Používat složku vygeneruje kód  
 Umístění šablony a generované soubory v projektu složku s názvem **vygeneruje kód**, aby bylo vymazat, že tyto nejsou soubory, které by měl být upraven přímo. Pokud vytvoříte vlastní kód přepsání nebo přidání do vygenerované třídy, umístěte tyto třídy ve složce s názvem **vlastní kód**. Struktura typické projektu vypadá takto:  
  
```  
MyProject  
   Custom Code  
      Class1.cs  
      Class2.cs  
   Generated Code  
      Class1.tt  
          Class1.cs  
      Class2.tt  
          Class2.cs  
   AnotherClass.cs  
  
```  
  
## <a name="guidelines-for-run-time-preprocessed-t4-templates"></a>Pokyny pro šablony T4 Run-Time (předběžně zpracované)  
 Přesuňte běžné materiálu do zděděné šablony  
 Můžete sdílet metody a text bloky mezi textových šablon T4 dědičnosti. Další informace najdete v tématu [T4 – direktiva Template](../modeling/t4-template-directive.md).  
  
 Můžete taky zahrnout soubory, které mají běhu šablony.  
  
 Velké části kódu, přesuňte do konkrétní třídu.  
 Každé spuštění šablony generuje definici třídu, která má stejný název jako šablonu. Můžete napsat kód soubor, který obsahuje jiné částečné definice stejné třídy. K třídě tímto způsobem můžete přidat metody, pole a konstruktory. Tito členové lze volat z bloky kódu v šabloně.  
  
 Výhodou to je, že kódu je psát, protože není k dispozici IntelliSense. Kromě toho můžete dosáhnout lepší oddělení mezi prezentaci a logiku.  
  
 Například v **MyReportText.tt**:  
  
 `The total is: <#= ComputeTotal() #>`  
  
 V **MyReportText Methods.cs**:  
  
 `private string ComputeTotal() { ... }`  
  
 Povolit pro vlastní kód: zadejte body rozšíření  
 Vezměte v úvahu generování virtuální metody v \<#+ třída funkce blokuje #>. To umožňuje jeden šablonu, která má být použita v mnoha kontextech bez úprav. Místo změny v šabloně, můžete vytvořit odvozené třídy, která poskytuje minimální další logiku. Odvozená třída může být buď regulární kód, nebo může být spuštění šablony.  
  
 Například v MyStandardRunTimeTemplate.tt:  
  
```  
This page is copyright <#= CompanyName() #>.  
<#+ protected virtual string CompanyName() { return ""; } #>  
```  
  
 V kódu aplikace:  
  
```  
class FabrikamTemplate : MyStandardRunTimeTemplate  
{  
  protected override string CompanyName() { return "Fabrikam"; }  
}  
...  
  string PageToDisplay = new FabrikamTemplate().TextTransform();  
  
```  
  
## <a name="guidelines-for-all-t4-templates"></a>Pokyny pro všechny šablony T4  
 Samostatné shromažďování dat z textu  
 Pokuste se vyhnout směšování výpočtů a bloky textu. V každé šabloně textu, použijte první \<# kód blokovat #> Nastavení proměnných a provádět komplexní výpočty. Z prvního bloku textu na konci šablony nebo první \<#+ třída funkce blokovat #>, vyhněte se dlouho výrazy a zabránit smyčky a podmíněné příkazy pokud obsahují bloky textu. Tento postup usnadňuje šablonu pro čtení a údržbu.  
  
 Nepoužívejte `.tt` pro zahrnout soubory  
 Například používat příponu názvu souboru různých `.ttinclude` pro zahrnout soubory. Použití `.tt` pouze pro soubory, které mají být zpracovány buď jako spuštění nebo návrhu textové šablony. V některých případech [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozpozná `.tt` soubory a automaticky nastaví jejich vlastnosti pro zpracování.  
  
 Spusťte každé šabloně jako pevné prototypu.  
 Zápis příklad kódu nebo textu, kterou chcete vygenerovat a ujistěte se, zda je správný. Pak změňte jeho příponu .tt a přírůstkově vložení kódu, která upraví obsah načtením modelu.  
  
 Zvažte použití typu modelů.  
 I když můžete vytvořit schéma XML nebo databáze pro modely, může to být užitečné vytvořit konkrétní jazyk domény (DSL). DSL má výhodu, že vygeneruje třídu představují každý uzel ve schématu a vlastnosti představují atributy. To znamená, které můžete naprogramovat z hlediska obchodní model. Příklad:  
  
```  
Team Members:  
<# foreach (Person p in team.Members)   
 { #>   
    <#= p.Name #>   
<# } #>  
```  
  
 Zvažte použití diagramy pro modely.  
 Mnoho modely jsou efektivní zobrazovat a spravovat jednoduše jako text tabulky, zejména v případě, že jsou velmi velké.  
  
 Však pro některé druhy obchodní požadavky, je důležité o vysvětlení, komplexní sadu vztahy a pracovní toky a diagramy se nejlépe hodí střední. Výhodou diagram je snadno diskuse s uživatelů a dalších zúčastněných osob. Generování kódu z modelu na úrovni obchodní požadavky, se být kódu flexibilnější při změně požadavky.  
  
 Můžete taky navrhnout vlastní typ diagramu jako jazyk specifické pro doménu (DSL). Kód lze vygenerovat z UML i DSL, linky. Další informace najdete v tématu [analýza a modelování architektury](../modeling/analyze-and-model-your-architecture.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření kódu v době návrhu pomocí textových šablon T4](../modeling/design-time-code-generation-by-using-t4-text-templates.md)   
 [Generování textu za běhu pomocí textových šablon T4](../modeling/run-time-text-generation-with-t4-text-templates.md)
