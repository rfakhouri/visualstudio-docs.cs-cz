---
title: O jazycích specifických pro konkrétní domény
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: b12c11032527477348ac6542feb758db8dfe6a59
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="about-domain-specific-languages"></a>O jazycích specifických pro konkrétní domény

Na rozdíl od obecný jazyk například C# nebo UML jazyk specifické pro doménu (DSL) slouží k express příkazy v místo konkrétního problému, nebo doméně.

Známé DSL, linky obsahovat regulární výrazy a SQL. Každý DSL je mnohem lepší než obecný jazyk pro popis operace v textové řetězce nebo databáze, ale mnohem nejhorší popisující nápady, které jsou mimo svůj vlastní rozsah. Jednotlivé odvětví mají také vlastní DSL, linky. Například v odvětví telecommunications popis volání jazyky se často používají k zadejte pořadí stavů v telefonního hovoru a v vzduchem cestují oborový standard DSL se používá k popisu letu rezervace.

Vaši firmu a projekt také speciální sady koncepty, které může být popsáno pomocí DSL zabývat. Můžete třeba definovat DSL pro jednu z těchto aplikací:

-   Plán cesty navigace na webu.

-   Vzájemné propojení diagramy pro elektronické součásti.

-   Sítě dopravní pásů a zpracování zařízení pro letišti sobě.

Při návrhu DSL, můžete definovat *domény třída* pro každou důležité koncepty v doméně, jako je například webové stránce, svítilna nebo letiště vrácení se změnami podpory. Můžete definovat *vztahy domén* například hypertextový odkaz, přenosová nebo běžícím pásu propojení koncepty společně.

Vytvoření uživatelů vaší DSL *modelů.* Modely jsou *instance* linek. Například popisují určitý web nebo zapojení se určité zařízení nebo sobě zpracování systému v určitém letišti.

Vaši uživatelé můžete zobrazit model jako diagram nebo formuláře systému Windows. Modely lze také zobrazit ve formátu XML, který je, jak jsou uložené. Když definujete DSL, definujete jak instance každé domény třídy a relace zobrazí na obrazovce uživatele. Typické DSL se zobrazuje jako kolekci ikony nebo obdélníků pomocí šipky.

Následující obrázek znázorňuje model malé v graficky DSL:

![Tudor rodiny stromu modelu](../modeling/media/tudor_familytreemodel.png "Tudor_FamilyTreeModel")

## <a name="what-you-can-do-with-dsls"></a>Co můžete dělat s DSL, linky

Typická aplikace DSL je generování kódu programu nebo jiné artefakty. Když definujete vaší DSL, můžete definovat *textové šablony* , čtení model DSL a generování textových souborů.

Můžete například napsat šablony, které trvat plán letiště a generovat součástí softwaru pro zpracování, a také některé dokumenty uživatele, které popisují plán sobě.

Pokud jste definovali DSL, můžete ho distribuovat jiným uživatelům, kteří můžete nainstalovat na své počítače. Uživatelé vaší DSL můžete vytvořit a upravit modelů v sadě Visual Studio.

Můžete také definovat příkazy nabídky a jiné nástroje, které pomáhají uživatelům upravit DSL, omezení ověřování k zajištění, že je správně použít DSL a šablony položek, které pomáhají uživatelům vytvořit nové instance. Jeden nebo více DSL, linky s jejich nástroje a další rozšíření sady Visual Studio může obtékat jako integrované balíček.

Obvykle jazyka domény je vytvořena při vývojový tým má napsat podobné kód pro více produktů. Například společnost, která se specializuje na sobě systémy zpracování může definovat DSL sledovat sobě, ze kterého se mohou generovat kód pro každou instalaci. DSL výhody, může být srozumitelné svým zákazníkům, zda kód, který vygenerovala z něj spolehlivé a že v systému mohou být rychle aktualizovány, pokud se změní požadavky zákazníků.

[!INCLUDE[dsl](../modeling/includes/dsl_md.md)] Umožňuje vytvořit specifické pro doménu jazyka, který má vlastní grafický Návrhář a vlastní diagram zápis a pak použít ke generování příslušné zdrojového kódu pro každý projekt jazyka.

## <a name="domain-specific-development"></a>Vývoj pro specifické pro doménu

Vývoj pro specifické pro doménu je proces identifikace součástí vaší aplikace, které můžete modelovány pomocí pomocí jazyka specifické pro doménu a pak vytváření jazyk a jeho nasazení na vývojáře aplikace. Vývojáři pomocí jazyka domény sestavit modely, které jsou specifické pro své aplikace, používat modely ke generování zdrojového kódu a pak použít zdrojový kód pro vývoj aplikací.

## <a name="aspects-of-graphical-domain-specific-development"></a>Aspekty grafické vývoj specifické pro doménu

Grafické domény jazyka musí zahrnovat následující funkce:

- Zápis

- Model domény

- Generování artefaktů

- Serializace

- Integrace se sadou Visual Studio

### <a name="notation"></a>Zápis

Jazyka domény musí mít přiměřené malého elementů, které se dají snadno definované a rozšířené představují konstrukce specifické pro doménu. Zápis se skládá z tvarů, které představují prvky, a konektory, které představují vztahy mezi elementy, na povrchu Grafický diagram. V [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], obrazce může být dále rozšiřována a vylepšení představují elementy jazyka specifické pro doménu.

### <a name="domain-model"></a>Model domény

Jazyka domény musíte kombinovat sadu elementů a vztahů mezi nimi do souvislý gramatika. Musí také definovat, zda jsou platné kombinace elementů a vztahů. Například programovací jazyky obvykle zakázat cyklické dědičnosti, ve kterém je jednu třídu odvozenou od třídy sekundu a druhé třídy je odvozena od třídy první. Omezení slouží také k express obchodní logiky, například jedna osoba nelze závislé služby sám. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] pomocí omezení express druhy omezení, které vyžadují nejvíc jazyky specifické pro doménu.

### <a name="artifact-generation"></a>Generování artefaktů

Jedním z hlavní účely jazyka domény je ke generování artefakt, například zdrojový kód, soubor XML nebo některá použitelné data. Změny v modelu obvykle znamená změnu artefakt. Můžete použít [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] generování artefaktů a obnovit je při změně modelu.

### <a name="serialization"></a>Serializace

Jazyk specifické pro doménu musí nastavit jako trvalý, v některých formulář, který lze upravovat, uložit, ukončeno a znovu načíst. [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] používá formát XML, který umožňuje definovat a přizpůsobit, jak je jazyka specifické pro doménu serializován nebo trvalé.

### <a name="integration-with-visual-studio"></a>Integrace se sadou Visual Studio

Protože [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] je hostován v sadě Visual Studio, rozšiřuje mnoha windows Visual Studio a ovládací prvky. To také umožňuje přizpůsobit chování příkazy nabídky, položek sady nástrojů a další prvky uživatelského rozhraní.

Můžete také vytvořit adaptér sběrnice modelu pro váš jazyk specifické pro doménu. Tento adaptér umožňuje referenční model a elementů v rámci modelu a umožňuje, které můžete psát kód, které můžete používat a aktualizovat instance DSL. Pomocí o efektivní mechanismus modelu sběrnice můžete napsat rozšíření Visual Studia, které pracují s více modelů. Je také možné zapsat samostatné aplikace, které pracují s modely. Další informace najdete v tématu [integrace modelů pomocí Visual Studio Modelbus](../modeling/integrating-models-by-using-visual-studio-modelbus.md).

## <a name="benefits-of-domain-specific-development"></a>Výhody vývoj specifické pro doménu

Jazyka domény můžou poskytovat následující výhody:

- Obsahuje konstrukce, přesně splňující místo na problém.

     Na rozdíl od pro obecné účely jazyky jazyka domény se skládá z elementů a vztahy, které přímo představují logiku prostoru problém. Například pojistku aplikace musí obsahovat prvky pro zásady a deklarace identity. Jazyk specifické pro doménu usnadňuje aplikací a najít a opravit chyby logiky.

- Umožňuje bez vývojáři a osoby neznáte domény pochopit celkový návrh.

     Pomocí grafického rozhraní jazyka specifické pro doménu můžete vytvořit vizuální reprezentace domény tak, aby bez vývojářům snadno porozumíte návrhu aplikace.

- Usnadňuje vytvoření prototypu konečné aplikace.

     Vývojáři mohou použít kód, který generuje jejich modelu k vytvoření prototypu aplikace, která můžete zobrazit na klienty.

## <a name="the-process-of-domain-specific-development"></a>Proces vývoje specifické pro doménu

Většina softwaru vývojové týmy, které používají specifické pro doménu jazyky použijte následující postup vytvoření a používání jejich modely:

-   Tým rozlišuje části proměnné domény z části, které nikdy nezmění.

-   Vývojáři psát kód pro pevné části a nechte body rozšíření pro proměnné části.

-   Vývojář softwaru realizace nebo architekt vytvoří jazyk specifické pro doménu, která zahrnuje vzory návrhu pevné částí domény, a body rozšíření pro proměnné části.

-   Vývojář softwaru realizace nebo architekt nasadí jazyka domény pro vývojáře různé aplikace, které vytvoří tým.

-   Každý vývojář vytvoří model, který se vztahuje na konkrétní aplikaci.