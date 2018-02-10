---
title: "Přepsání a rozšíření generované třídy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, providing overridable classes
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: f86600b6fd4bb272ece4454e9a94032ed05f3af1
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="overriding-and-extending-the-generated-classes"></a>Přepisování a rozšiřování vygenerovaných tříd
DSL Definition je platforma, ve kterém můžete vytvořit výkonnou sadu nástrojů, které jsou založené na jazyce specifické pro doménu. Mnoho rozšíření a přizpůsobení můžete provést pomocí přepsání a rozšíření třídy, které se generují z definice DSL. Tyto třídy zahrnují nejen třídy domény, které jste definovali explicitně v diagramu definice DSL, ale také další třídy, které definují sada nástrojů, Průzkumník, serializace a tak dále.  
  
## <a name="extensibility-mechanisms"></a>Rozšiřitelnost mechanismy  
 Aby bylo možné rozšířit generovaného kódu jsou k dispozici několik mechanismů.  
  
### <a name="overriding-methods-in-a-partial-class"></a>Přepsání metody v konkrétní třídu  
 Definice pro třídu povolit třídu být definován více než jednom místě. To umožňuje oddělit generovaný kód z kód, který můžete psát sami. V kódu ručně zapisovat můžete přepsat třídy zdědí generovaného kódu.  
  
 Například, pokud v definici vaší DSL definujete domény třídy s názvem `Book`, můžete napsat vlastní kód, který přidá přepsání metody:  
  
 `public partial class Book`  
  
 `{`  
  
 `protected override void OnDeleting()`  
  
 `{`  
  
 `MessageBox.Show("Deleting book " + this.Title);`  
  
 `base.OnDeleting();`  
  
 `} }`  
  
> [!NOTE]
>  K přepsání metody v vygenerované třídy, vždy psát kód v souboru, která je oddělená od generované soubory. Obvykle je soubor obsažený ve složce s názvem CustomCode. Pokud provedete změny generovaného kódu, budou ztraceny při opětovném generování kódu z definice DSL.  
  
 Chcete-li zjistit, jaké metody můžete přepsat, zadejte **přepsat** ve třídě, následované mezerou. Popisek IntelliSense vám oznámí, jaké metody se dá přepsat.  
  
### <a name="double-derived-classes"></a>Dvojitý odvozené třídy  
 Většina metod v generované třídy dědí z dlouhodobého sadu tříd v oboru názvů modelování. Ale některé metody jsou definovány v generovaného kódu. Obvykle to znamená, že nelze přepsat je; nelze přepsat v jednu třídu metody, které jsou definovány v jiné definici částečné stejné třídy.  
  
 Nicméně můžete přepsat tyto metody nastavením **generuje dvojité odvozené** příznak pro třídu domény. Tato dvě třídy způsobí vygenerování, z nich bude abstraktní základní třídu druhé. Jsou všechny metody a vlastnosti definice v základní třídě a je pouze konstruktoru odvozené třídy.  
  
 Například v ukázce Library.dsl `CirculationBook` třída domény má `Generates``Double Derived` vlastnost nastavena na hodnotu `true`. Generovaný kód pro tuto třídu domény obsahuje dvě třídy:  
  
-   `CirculationBookBase`, který je abstraktní a který obsahuje všechny metody a vlastnosti.  
  
-   `CirculationBook`, který je odvozen z `CirculationBookBase`. Je prázdný, s výjimkou jeho konstruktory.  
  
 Pokud chcete přepsat libovolnou metodu, můžete například vytvořit definici částečné odvozené třídy `CirculationBook`. Metody generované a metody zděděno z rozhraní modelování můžete přepsat.  
  
 Tuto metodu můžete použít se všemi typy elementu, včetně elementů modelu, relace, tvarů, diagramy a konektory. Můžete také přepsat metody jiných vygenerované třídy. Některé vygenerované třídy, jako ToolboxHelper se vždy odvozenými na dvojitou hodnotu.  
  
### <a name="custom-constructors"></a>Vlastní konstruktory  
 Nejde přepsat konstruktor. I v dvojitou odvozené třídy musí být konstruktoru odvozené třídy.  
  
 Pokud chcete zadat vlastní konstruktor, můžete provést nastavením `Has Custom Constructor` pro třídu domény v definici DSL. Když kliknete na tlačítko **transformaci všech šablon**, generovaný kód nebude obsahovat konstruktoru pro tuto třídu. Bude zahrnovat volání chybí konstruktor. To způsobí, že zpráva o chybě při sestavování řešení. Dvakrát klikněte na zprávu o chybách poznámku generovaného kódu, který vysvětluje, co by měl poskytovat.  
  
 Zápis definice částečné třídy v souboru, která je oddělená od generované soubory a zadejte konstruktoru.  
  
### <a name="flagged-extension-points"></a>Označení rozšíření body  
 Označení rozšíření bod je místo v definici DSL, kde můžete nastavit vlastnost nebo zaškrtávací políčko k označení, že zadáte vlastní metody. Vlastní konstruktory jsou jedním z příkladů. Další příklady nastavení `Kind` vlastnosti domény vypočítaná nebo vlastní úložiště nebo nastavení **je vlastní** příznak v Tvůrci připojení.  
  
 V každém případě bude znovu vygenerovat kód, a nastaven příznak výsledkem chyba sestavení. Dvakrát klikněte na chybu, která vysvětluje, co je nutné zadat poznámku.  
  
### <a name="rules"></a>Pravidla  
 Správce transakcí umožňuje definovat pravidla, která spustí před ukončením transakcí, ve kterém má určené události došlo, například o změně ve vlastnosti. Pravidla jsou obvykle používány k udržování synchronism mezi různé elementy v úložišti. Například pravidla se používají a ujistěte se, že diagram zobrazuje aktuální stav modelu.  
  
 Na základě za třídy jsou definovaná pravidla, takže není nutné mít kód, zaregistruje pravidlo pro každý objekt. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
### <a name="store-events"></a>Uložení událostí  
 Modelování úložiště poskytuje mechanismus událostí, které můžete použít k naslouchání pro konkrétní typy změn v úložišti, včetně přidání nebo odstranění elementů změny hodnot vlastností a tak dále. Po ukončení transakce, ve kterém byly provedeny změny jsou volány obslužné rutiny událostí. Obvykle jsou tyto události použít k aktualizaci prostředky mimo úložišti.  
  
### <a name="net-events"></a>Události rozhraní .NET  
 Můžete se přihlásíte k některé události na tvarů. Můžete například poslouchat kliknutí myší na obrazce. Budete muset psát kód, který jako odběratel u událostí pro každý objekt. Tento kód může být napsán v přepsání InitializeInstanceResources().  
  
 Některé události se generují u ShapeFields, které se používají k vykreslení dekoratéry na obrazce. Příklad, naleznete v části [postupy: zachycení a klikněte na tvar nebo Dekoratéra](../modeling/how-to-intercept-a-click-on-a-shape-or-decorator.md).  
  
 Tyto události obvykle se nevyskytují v transakci. Pokud chcete provést změny v úložišti, měli byste vytvořit transakce.