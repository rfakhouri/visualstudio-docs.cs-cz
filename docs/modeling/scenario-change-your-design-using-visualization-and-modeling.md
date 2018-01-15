---
title: "Scénář: Změna návrhu pomocí vizualizace a modelování | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: get-started-article
helpviewer_keywords:
- code visualization [Visual Studio ALM]
- modeling software [Visual Studio ALM]
- software modeling [Visual Studio ALM]
- walkthroughs [Visual Studio ALM], visualizing code
- walkthrough [Visual Studio ALM], visualizing code
- walkthrough [Visual Studio ALM], modeling software
- walkthroughs [Visual Studio ALM], modeling software
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2bec52fc091186aa660e10f1887f98bfdab5acc7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="scenario-change-your-design-using-visualization-and-modeling"></a>Scénář: Změna návrhu pomocí vizualizace a modelování
Ujistěte se, že váš systém software splňuje požadavky uživatelů pomocí vizualizace a modelování nástroje v sadě Visual Studio.
Pomocí nástrojů, jako je map kódu, diagramy závislostí a diagramů tříd do:  
  
 Jaké verze sady Visual Studio každý nástroj podpory najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
-   Vysvětlení, požadavky a obchodní procesy uživatelů.  
  
-   Vizualizovat a zkoumat existujícího kódu.  
  
-   Popisují změny stávajícího systému.  
  
-   Ověřte, že systém splňuje požadavky na jeho.  
  
-   Zachovat kód konzistentní s návrhu.  
  
 Tento názorný postup:  
  
-   Popisuje, jak tyto nástroje vám může hodit projektu softwaru.  
  
-   Ukazuje, jak můžete pomocí těchto nástrojů, bez ohledu na to budete přistupovat (vývoj), s příklad scénáře.  
  
 Další informace o těchto nástrojů a scénáře, které podporují, najdete v tématu:  
  
-   [Analýza a modelování vaší architektury](../modeling/analyze-and-model-your-architecture.md)  
  
-   [Vizualizace kódu](../modeling/visualize-code.md)  
  
##  <a name="ScenarioOverview"></a>Přehled scénáře  
 Tento scénář popisuje díly z životních vývoj softwaru dvě fiktivní společností: nyní večeři a Lucerne publikování. Večeři teď poskytuje službu webové jídlem doručení v Praze. Zákazníci, můžete pořadí jídlo a platí pro ně na večeři teď webu. Objednávky se pak odešlou do odpovídající místní restaurace pro doručení. Publikování Lucerne společnosti v New Yorku, spustí několik podnikům vypnout i na webu. Například se spustit webovou stránku, na které mohou zákazníci vystavit restaurace recenze.  
  
 Lucerne nedávno večeři teď získali a chce provést následující změny:  
  
-   Integrate svých webů tím, že přidání schopností zkontrolujte restaurace do večeři teď.  
  
-   Nahraďte večeři nyní je platba systému Lucerne na systému.  
  
-   Rozbalte služby večeři napříč oblasti.  
  
 Večeři teď používá SCRUM a extrémních programování. Mají velmi vysoká testovací pokrytí a velmi trochu nepodporované kódu. Vytváření malý, ale pracovní verze systému a pak postupně přidání funkce minimalizují rizika. Svůj kód vyvíjejí přes krátký a často iterací. Díky tomu je zapojení změn mohli bez obav, často Refaktorovat kód a zabránit "velký návrhu předem".  
  
 Lucerne udržuje kolekci významně větší a složitější systémů, z nichž některé jsou starší než 40 let. Jsou velmi opatrní při provádění změn z důvodu složitosti a oboru starší verze kódu. Následují přísnějším vývoj procesu, upřednostňují návrh podrobné řešení a dokumentu návrhu a změny, ke kterým došlo během vývoje.  
  
 Obě týmy pomocí diagramy modelování v sadě Visual Studio k vytvoření systémy, které splňují požadavky uživatelů. Team Foundation Server používají společně se dalších nástrojů pomáhá jim plánování, organizovat a spravovat práci.  
  
 Další informace o Team Foundation Server najdete v tématu:  
  
-   [Plánování a sledování práce](#PlanningTracking)  
  
-   [Testování, ověřování a kontrolu v aktualizované kódu](#TestValidateCheckInCode)  
  
##  <a name="ModelingDiagramsTools"></a>Role architektura a modelování diagramy při vývoji softwaru  
 Následující tabulka popisuje role, které tyto nástroje můžete přehrát během několika a různých fázích životního cyklu softwaru:  
  
||**Modelování uživatelských požadavků**|**Modelování obchodních procesů**|**Architektura systému a návrh**|**Vizualizace kódu & zkoumání**|**Ověření**|  
|------|------------------------------------|-----------------------------------|--------------------------------------|------------------------------------------|----------------------|  
|Diagram specifické pro doménu jazyk (DSL)|Ano|Ano|Ano|||  
|Diagram závislostí, ověření vrstev|||Ano|Ano|Ano|  
|Mapa kódu|||Ano|Ano|Ano|  
|Návrhář tříd (založené na kódu)||||Ano||  
  
Kreslení závislostí diagramy, musíte vytvořit projekt modelování v rámci stávajícího řešení nebo novou. Tyto diagramy musí být vytvořený v projektu modelování.
Položky v diagramech závislosti nacházejí v projektu modelování, ale nejsou uložené v společného modelu. Mapy kódu a diagramů tříd rozhraní .NET vytvořené z kódu existují mimo projekt modelování.  
  
 Další informace:  
  
-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)  
  
-   [Postupy: Přidání diagramů tříd do projektů (Návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)  
  
-   [Sada Modeling SDK pro Visual Studio – jazyky specifické pro doménu](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
  
 Jak týmy také používají ověřování závislostí a ujistěte se, že kód ve vývoji konzistentní s návrhu.  
  
 Další informace:  
  
-   [Zachování konzistentní s návrh kódu](#ValidatingCode)  
  
-   [Logická architektura popisují: závislost diagramy](#DescribeLayers)  
  
-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)  
  
    > [!NOTE]
    >  Některé verze sady Visual Studio podporují pro vizualizace a modelování závislostí ověření a jen pro čtení verzích map kódu. Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
##  <a name="UnderstandingCommunicating"></a>Principy a komunikaci informace o systému  
 Neexistuje žádné předepsaných pořadí pro pomocí sady Visual Studio modelování diagramy, abyste je mohli používat podle jejich potřeb s potřebám nebo přístupu. Obvykle týmy pokroku jejich modely interaktivně a často v jeho průběhu. Každý diagram nabízí konkrétní síly vám pomohou pochopit, popis a komunikaci různé aspekty systému ve vývoji.  
  
 Nyní večeři a Lucerne komunikovat s každou další a účastníky projektu s použitím diagramů jako běžné jazyk. Například večeři teď používá diagramy k provedení těchto úloh:  
  
-   Vizualizace kódu existující.  
  
-   Komunikovat s Lucerne o nových nebo aktualizovaných uživatelských scénářů.  
  
-   Identifikujte změny, které jsou potřebné k podpoře nových nebo aktualizovaných uživatelských scénářů.  
  
 Lucerne diagramy používá k provedení těchto úloh:  
  
-   Další informace o obchodní proces večeři teď.  
  
-   Porozumějte návrhu systému.  
  
-   Komunikovat s večeři teď o nových nebo aktualizovaných uživatelských požadavků.  
  
-   Dokument aktualizace systému.  
  
 Diagramy jsou integrované s produktem Team Foundation Server, aby týmy plánování, spravovat a sledovat práci snadněji. Například používají modely k identifikaci testovací případy a vývojářských úloh a k zjištění přibližné hodnoty práci. Odkazy Lucerne Team Foundation Server pracovních položek k elementům modelu tak, aby můžete monitorovat průběh a ujistěte se, že systém splňuje požadavky uživatelů. Například se propojit případy použití testovacího případu pracovních položek, uvidí, že jsou splněny případy použití, když všechny testy byly úspěšné.  
  
 Než se týmy zkontrolujte v jejich změny, se ověřit kód proti testy a návrh spuštěním sestavení, které zahrnují ověření závislostí a automatizované testy. To pomáhá, ujistěte se, že aktualizovaný kódu není v konfliktu s návrh a rozdělit dříve pracovní funkce.  
  
 Další informace:  
  
-   [Identifikace změny stávajícího systému](#DeterminingChanges)  
  
-   [Zachování konzistentní s návrh kódu](#ValidatingCode)  
  
-   [Obecné tipy pro vytváření a použití modelů](#GeneralTips)  
  
-   [Plánování a sledování práce](#PlanningTracking)  
  
-   [Testování, ověřování a kontrolu v aktualizované kódu](#TestValidateCheckInCode)  

###  <a name="DeterminingChanges"></a>Identifikace změny stávajícího systému  
 Večeři nyní musíte odhadnout náklady splňuje nový požadavek. To závisí částečně na kolik této změny bude mít vliv na ostatní části systému. Aby mohl snadněji pochopit to, jeden vývojářů večeři vytvoří tyto mapy a diagramy z existujícího kódu:  
  
|**Mapa nebo diagram**|**Zobrazuje**|  
|------------------------|---------------|  
|*Mapa kódu*<br /><br /> Další informace:<br /><br /> -   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)<br />-   [Přizpůsobení map kódu úpravou souborů DGML](../modeling/customize-code-maps-by-editing-the-dgml-files.md)|Závislosti a dalších vazeb v kódu.<br /><br /> Například večeři nyní může spustit kontrolou map kódu sestavení přehled informací o sestavení a jejich závislosti. Jejich můžete přejít k podrobnostem mapy a prozkoumejte obory názvů a třídy v těchto sestavení.<br /><br /> Večeři teď můžete také vytvořit mapy prozkoumat konkrétní oblasti a dalších typů vztahů v kódu. Průzkumník řešení používají k vyhledání a výběr oblastí a vztahy, které je zajímají.|  
|*Diagram založené na kódu – třída*<br /><br /> V tématu [postupy: Přidání diagramů tříd do projektů (návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|Existující třídy v kódu|  
  
 Třeba vývojář vytvoří mapa kódu. Jana upraví jeho oboru a zaměřit se na oblasti, které ovlivní nový scénář. Tyto oblasti jsou vybrané a zvýrazní na mapě:  
  
 ![Graf závislostí Namespace](../modeling/media/namespace_reviewsystem.png "Namespace_ReviewSystem")  
  
 **Namespace Mapa kódu**  
  
 Vývojář rozšíří vybrané obory názvů zobrazíte jejich tříd, metod a relace:  
  
 ![Graf závislostí rozšířené obor názvů](../modeling/media/dep_reviewsystem.png "Dep_ReviewSystem")  
  
 **Mapa kódu rozšířené oboru názvů s viditelné skupinu křížové odkazy**  
  
 Vývojář prověří kód najít ovlivněných třídy a metody. Každé změny projeví jako zajistěte je, znovu generovat kód mapuje po každé změně. V tématu [vizualizace kódu](../modeling/visualize-code.md).  
  
 Popis změny dalšími částmi systému, jako je například součástí nebo interakce, může tým kreslení tyto prvky v Tabule. Následující diagramy se taky může kreslení v sadě Visual Studio tak, aby podrobnosti můžete zaznamenat, spravované a rozumím jim obě týmy:  
  
|**Diagramy**|**Popisuje**|  
|------------------|-------------------|  
|*Diagram založené na kódu – třída*<br /><br /> V tématu [postupy: Přidání diagramů tříd do projektů (návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|Existující třídy v kódu.|  
  
###  <a name="ValidatingCode"></a>Zachování konzistentní s návrh kódu  
 Nyní večeři musí zajistit, že aktualizovaný kódu zůstává konzistentní s návrhu. Uživatel vytvořit diagramy závislosti, které popisují vrstvy funkce v systému, zadejte povolených závislosti mezi artefakty řešení je a přidružení pro tyto vrstvy.  
  
|**Diagram**|**Popisuje**|  
|-----------------|-------------------|  
|*Diagram závislostí*<br /><br /> Další informace:<br /><br /> -   [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md)<br />-   [Diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md)<br />-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|Logická architektura kód.<br /><br /> Diagram závislostí slouží k uspořádání a mapuje artefakty v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení názvem skupiny abstraktní *vrstvy*. Tyto vrstvy Identifikujte role, úlohy nebo funkce, které tyto artefakty provádět v systému.<br /><br /> Diagramy vrstev jsou užitečné pro popisující zamýšlené systému a ověřování vyvíjející kódu proti tohoto návrhu.<br /><br /> K vytvoření vrstvy, přetáhněte položky z Průzkumníku řešení, map kódu, zobrazení tříd a prohlížeč objektů. Kreslení nové vrstvy, pomocí sady nástrojů nebo klikněte pravým tlačítkem na povrch diagramu.<br /><br /> Chcete-li zobrazit existující závislosti, klikněte pravým tlačítkem myši na povrch diagram vrstvy a pak klikněte na tlačítko **generovat závislosti**. Pokud chcete zadat určený závislosti, kreslení nové závislosti.|  
  
 Například následující závislost diagram popisuje závislosti mezi vrstvy a počtu artefaktů, které jsou spojeny s každou vrstvu:  
  
 ![Diagram závislostí integrované platebních systému](../modeling/media/layer_integrated_dnlucerne.png "Layer_Integrated_DNLucerne")  
  
 **Diagram závislostí**  
  
 Abyste měli jistotu, že je v konfliktu s návrh nedojde během vývoje kódu, používá týmy, které ověření závislost na sestavení, které se spouštějí na Team Foundation Build. Uživatel také vytvořit vlastní úlohu MSBuild vyžadovat ověření závislostí v jejich operace vrácení se změnami. Sestavení sestavy používají ke shromažďování chyb při ověřování.  
  
 Další informace:  
  
-   [Zadejte vaše procesu sestavení](http://msdn.microsoft.com/Library/61593e10-d24b-492f-b19a-af4d85abea6b)  
  
-   [Chcete-li ověřit změny používat proces ověřované vrácení se změnami sestavení](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec)  
  
-   [Přizpůsobení šablony procesu sestavení](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)  
  
###  <a name="GeneralTips"></a>Obecné tipy pro vytváření a použití modelů  
  
-   Většina diagramy skládat z uzlů, které jsou připojena linkami. Pro každý typ diagramu sady nástrojů poskytuje různé druhy uzly a řádky.  
  
     Otevření panelu nástrojů na **zobrazení** nabídky, klikněte na tlačítko **sada nástrojů**.  
  
-   Můžete vytvořit uzel, přetáhněte ji z panelu nástrojů pro diagram. Některé typy uzlů musí být přetáhli existujícím uzlům. V diagramu součásti, například musí být nový port přidaný do existující součást.  
  
-   Na řádku nebo připojení, klikněte na příslušný nástroj v panelu nástrojů, klikněte na zdrojový uzel a potom klikněte na cílový uzel. Některé řádky lze vytvořit pouze mezi určité typy uzlů. Při přesunutí ukazatele nad možné zdroje nebo cíle, ukazatele označuje, zda můžete vytvořit připojení.  
  
###  <a name="PlanningTracking"></a>Plánování a sledování práce  
 Diagramy modelování Visual Studio jsou integrované s produktem Team Foundation Server, aby mohli plánování, Správa a sledování práce snadněji. Jak týmy pomocí modely k identifikaci testovací případy a vývojářských úloh a k zjištění přibližné hodnoty práci. Vytvoří Lucerne a odkazy Team Foundation Server pracovních položek k elementům modelu, například případy použití nebo součásti. Díky tomu sledovat jejich průběh a trasování práci zpět na požadavky uživatelů. Díky tomu Ujistěte se, že jejich změny dále splňovat tyto požadavky.  
  
 Podle postupu jejich prací, jejich pracovní položky, aby odpovídala času, který budou stráví v jejich úlohy aktualizace týmy. Také monitorování a hlášení stavu na práci s použitím následujících funkcí Team Foundation Server:  
  
-   Denní *sestavy úbytku práce* , zobrazit, zda bude po dokončení plánovaná práce v očekávaném čase. Generují jiné podobné sestavy ze serveru Team Foundation Server můžete sledovat průběh chyb.  
  
-   *List iterací* používající aplikaci Microsoft Excel pomohou tým monitorovat a vyrovnávání zátěže mezi její členy. Tento list je propojena k serveru Team Foundation Server a poskytuje fokus diskusi během jejich pravidelné schůzky.  
  
-   A *řídicí panel vývoj* používající Microsoft Office Project zachovat týmem informován o důležité informace projektu.  
  
 Další informace:  
  
-   [Sledování práce pomocí sady Visual Studio Team Services nebo Team Foundation Server](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503)  
  
-   [Grafy, řídicí panely a sestavy pro Visual Studio ALM](http://msdn.microsoft.com/Library/1f28ba6c-c5e5-46d3-9209-ede24ae78e48)  
  
-   [Vytvoření nevyřízených položek a úloh s použitím aplikace Project](http://msdn.microsoft.com/Library/be5cef4f-755f-4ffe-8dd7-876d1e02c330)  
  
###  <a name="TestValidateCheckInCode"></a>Testování, ověřování a kontrolu v kódu  
 Jak týmy dokončete všechny úlohy, zkontrolujte svůj kód do správy verzí Team Foundation a zobrazovat výzva ze serveru Team Foundation Server, v případě, že zapomenete. Před Team Foundation Server přijímá jejich vrácení se změnami, týmy spustit testy jednotek a závislostí ověřování k ověření před jejich testovací případy a návrh kód. Team Foundation Server používají spuštění sestavení, testy částí automatizované a pravidelně ověření závislostí. To pomáhá, ujistěte se, že kód splňuje následující kritéria:  
  
-   Funguje.  
  
-   Je dříve nezalamuje funkční kód.  
  
-   Nekoliduje s návrhu.  
  
 Večeři teď má velké kolekce automatizovaných testů, které Lucerne můžete znovu použít, protože téměř všechny platit stále. Lucerne můžete také vytvořit na tyto testy a přidat nové tak, aby pokrývalo nové funkce. I taky pomocí sady Visual Studio spouštění manuálních testů.  
  
 Pokud chcete mít jistotu, že kód odpovídá návrh, nakonfigurujte týmy jejich sestavení v Team Foundation Build zahrnout ověření závislostí. Pokud dojde k konfliktů, vygeneruje se sestavu s podrobnostmi.  
  
 Další informace:  
  
-   [Testování aplikace](https://www.visualstudio.com/docs/test/overview)  
  
-   [Ověřování systému během vývoje](../modeling/validate-your-system-during-development.md)  
  
-   [Použití správy verzí](http://go.microsoft.com/fwlink/?LinkID=525605)  
  
-   [Sestavení aplikace](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)  
  
##  <a name="UpdatingSystem"></a>Aktualizace systému pomocí vizualizace a modelování  
 Lucerne a večeři teď musíte integrovat jejich platebních systémy. Diagramy modelování v sadě Visual Studio snadněji provedení této úlohy zobrazit v následujících částech:  
  
-   [Vizualizace kódu existující: Mapy kódu](#VisualizeCode)  
  
-   [Definování Glosář typy: diagramy tříd](#DefineClasses)  
  
-   [Logická architektura popisují: závislost diagramy](#DescribeLayers)  
  
 Další informace:  
  
-   [Vizualizace kódu](../modeling/visualize-code.md)  
  
-   [Použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md)  
  
-   [Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)  
 
###  <a name="VisualizeCode"></a>Vizualizace kódu existující: Mapy kódu  
 Mapy kódu zobrazit aktuální organizace a vztahů v kódu. Položky jsou reprezentované pomocí *uzly* na mapě, a vztahy jsou reprezentované pomocí *odkazy*. Mapy kódu můžete provádět následující druhy úloh:  
  
-   Prozkoumejte neznámým kódem.  
  
-   Pochopení, kdy a jak navrhované změny mohou ovlivnit existujícího kódu.  
  
-   Oblasti složitost, přirozené závislosti nebo vzory nebo jiné oblasti, které může mít užitek z zlepšování najít.  
  
 Například večeři nyní musíte odhadnout náklady na komponentu PaymentProcessing aktualizace. To závisí částečně na kolik této změny bude mít vliv na ostatní části systému. Aby mohl snadněji pochopit to, jeden vývojářů večeři generuje mapy kódu z kódu a upraví oboru zaměřuje na oblasti, které by mohly mít dopad změny.  
  
 Následující mapa zobrazuje závislosti mezi třídou PaymentProcessing a dalšími částmi systému večeři teď zobrazovaných vybrané:  
  
 ![Graf závislostí pro večeři teď platebních systém](../modeling/media/dep_dnpayment.png "Dep_DNPayment")  
  
 **Mapa kódu večeři teď platebních systému**  
  
 Vývojáři jsou zde popsány mapy rozšíření třídy PaymentProcessing a její členy zobrazíte oblastí, které se vztahuje potenciálně výběrem:  
  
 ![Metody uvnitř PaymentProcessing a závislosti](../modeling/media/depgraph_expandeddn.png "DepGraph_ExpandedDN")  
  
 **Metody uvnitř PaymentProcessing třídy a jejich závislosti**  
  
 Generují následující mapa pro systém platebních Lucerne zkontrolovat její tříd, metod a závislosti. Tým uvidí Lucerne systému může také vyžadovat pracovní k interakci se ostatní části večeři teď:  
  
 ![Graf závislostí pro systém platebních Lucerne](../modeling/media/depgraph_lucernepay.png "DepGraph_LucernePay")  
  
 **Mapa kódu pro systém platebních Lucerne**  
  
 Jak týmy společně zjištění změn, které jsou nutné k integraci dvou systémů. Se rozhodnou Refaktorovat kód, takže ho bude jednodušší aktualizovat. Třída PaymentApprover se přesune do oboru názvů DinnerNow.Business a bude vyžadovat některé nové metody. Třídy teď večeři, které zpracování transakcí bude mít vlastní obor názvů. Týmy vytvoření a použití pracovních položek pro plánování, uspořádání a sledování práci. Jejich propojení pracovních položek k elementům modelu tam, kde je užitečné.  
  
 Po reorganizace kód, týmy generovat nové Mapa kódu zobrazíte aktualizované struktura a vztahů:  
  
 ![Graf závislostí reorganizovány všechny kódem](../modeling/media/depgraph_integrated.png "DepGraph_Integrated")  
  
 **Mapa kódu reorganizovány všechny kódem**  
  
 Tato mapa znázorňuje, že třída PaymentApprover je nyní v oboru názvů DinnerNow.Business a má některé nové metody. Transakce třídy večeři teď teď mají vlastní PaymentSystem názvů, který usnadňuje řešení s tímto kódem později.  
  
#### <a name="creating-a-code-map"></a>Vytváření mapy kódu  
  
-   Pro rychlý přehled o zdrojovém kódu použijte následující postup Generovat mapu kódu:  
  
     Na **architektura** nabídky, klikněte na tlačítko **Generovat mapu kódu pro řešení**.  
  
     Pro rychlý přehled o zkompilovaný kód vytvoření mapy prázdný kód a poté přetáhněte soubory sestavení nebo binární soubory na povrch mapy.  
  
-   Prozkoumat konkrétní kód nebo položky řešení, vyberte položky a vztahy, které chcete vizualizovat pomocí Průzkumníka řešení. Potom můžete buď vygenerovat nové mapování nebo přidat vybrané položky do existující mapu. V tématu [mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md).  
  
-   Chcete-li prozkoumat mapy, změna uspořádání rozložení tak, aby vyhovoval druhy úloh, které chcete provést.  
  
     Například k vizualizaci rozvrstvení v kódu, vyberte rozložení stromu. V tématu [Procházet a uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md).  
  
#### <a name="summary-strengths-of-code-maps"></a>Souhrn: Síly mapy kódu  
 Mapy kódu vám pomůže:  
  
-   Další informace o organizaci a vztahů v existujícím kódu.  
  
-   Určete oblasti, které by mohly mít dopad navrhované změny.  
  
-   Najít oblasti složitost vzory, vrstvy nebo jiné oblasti, které může zlepšit usnadnění kód udržovat, změnit a znovu použít.  
  
#### <a name="relationship-to-other-diagrams"></a>Vztah k jiným diagramům  
  
|**Diagram**|**Popisuje**|  
|-----------------|-------------------|  
|Diagram závislostí|Logická architektura systému. Pomocí závislosti ověření a ujistěte se, že kód zůstává konzistentní s návrhu.<br /><br /> Můžete určit existující dependencys nebo zamýšlené dependencys, vytvoření mapy kódu a seskupení souvisejících položek. Pokud chcete vytvořit diagram závislostí, najdete v části:<br /><br /> -   [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md)|  
|Diagram třídy (založené na kódu)|Existující třídy v kódu pro konkrétní projekt.<br /><br /> Účelem vizualizace a upravit existující třídy v kódu, použijte návrhář tříd.<br /><br /> V tématu [postupy: Přidání diagramů tříd do projektů (návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md).|  
  
###  <a name="DefineClasses"></a>Definování Glosář typy: diagramy tříd  
 Diagramy tříd definovat entitami, podmínky a koncepty, které jsou součástí systému a jejich vztahů s jednu na druhou. Například můžete použít tyto diagramy během vývoje pro popis atributů a operací pro každou třídu, bez ohledu na jejich implementace jazyk nebo styl.  
  
 Abyste Lucerne popisují a popisují entit, které v případě použití procesu platebních jejich kreslení následující diagram třídy:  
  
 ![Zpracování platebních entity v diagramu tříd](../modeling/media/uml_payentities.png "UML_PayEntities")  
  
 **Zpracování platebních entity v diagramu – třída**  
  
 Tento diagram znázorňuje, že zákazník může mít mnoho objednávek a různých způsobů, které pro objednávky. Bankovní účet a CreditCard dědí platba.  
  
 Během vývoje Lucerne používá následující diagram třída popsat a popisují podrobnosti o každé třídě:  
  
 ![Zpracování platebních entity podrobnosti o diagramu tříd](../modeling/media/uml_payment.png "UML_Payment")  
  
 **Podrobnosti o platebních procesu v diagramu – třída**  
    
#### <a name="drawing-a-class-diagram"></a>Kreslení Diagram – třída  
 Diagram třída má následující hlavní funkce:  
  
-   Typy, jako jsou třídy, rozhraní a výčty:  
  
    -   A *třída* je definice objektů, které sdílejí konkrétní strukturální nebo chování vlastností.  
  
    -   *Rozhraní* definuje část externě viditelné chování objektu.  
  
    -   *Výčtu* je třídění, který obsahuje seznam hodnot literálu.  
  
-   *Atributy* jsou hodnoty typu, které popisují každou instanci *třídění*. Třídění je obecné název pro typy, součásti, případy použití a i aktéři.  
  
-   *Operace* jsou metody nebo funkce, které můžete provádět instancí třídění.  
  
-   *Přidružení* označuje nějaký druh vztah mezi dvěma třídění.  
  
    -   *Agregace* je určující sdílené vlastnictví mezi třídění přidružení.  
  
    -   A *složení* je přidružení, které určuje vztah mezi třídění celá část.  
  
     Chcete-li zobrazit agregací nebo složení, nastavte **agregace** vlastnost na přidružení. **Sdílené** ukazuje agregací a **složené** ukazuje složení.  
  
-   A *závislostí* znamená, že změna definice jednoho třídění může změnit definici klasifikátor jiné.  
  
-   A *generalizace* označuje, že konkrétní třídění dědí z Obecné třídění součástí jeho definice. A *zjištění* označuje, že třída implementuje operace a atributy, které nabízí rozhraní.  
  
     Chcete-li vytvořit tyto relace, použijte **dědičnosti** nástroj. Alternativně můžete vyjádřené realizace *typu Lupa*.  
  
-   *Balíčky* jsou skupiny třídění, přidružení, životnosti, komponent a dalších balíčků. *Import* vztahy znamená, že jeden balíček zahrnuje všechny definice jiný balíček.  
  
 Návrhář tříd jako výchozí bod pro prozkoumat a popisují existujících tříd, slouží k vytvoření diagramů tříd z kódu.  
  
-   [Postupy: Přidání diagramů tříd do projektů (Návrhář tříd)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)  
  
#### <a name="summary-strengths-of-class-diagrams"></a>Souhrn: Síly diagramy tříd  
 Diagramy tříd můžete definovat:  
  
-   Běžný Glosář termínů používat, když hovoříte o potřeb uživatelů a entit, které v systému. V tématu [modelování uživatelských požadavků](../modeling/model-user-requirements.md).  
  
-   Typy, které jsou používány částmi systému, například komponenty, bez ohledu na jejich provádění. V tématu [modelování architektury aplikace](../modeling/model-your-app-s-architecture.md).  
  
-   Relace, jako je například závislosti mezi typy. Například můžete zobrazit, že jeden typ může být přidružen více instancí jiného typu.  
  
#### <a name="relationship-to-other-diagrams"></a>Vztah k jiným diagramům  
  
|**Diagram**|**Popis**|  
|-----------------|---------------------|  
|Diagram závislostí|Logická architektura systému definujte, protože se týká třídy.<br /><br /> Pomocí závislosti ověření a ujistěte se, že kód zůstává konzistentní s návrhu.<br /><br /> Další informace:<br /><br /> -   [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md)<br />-   [Diagramy závislost: pokyny](../modeling/layer-diagrams-guidelines.md)<br />-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)|  
|Mapa kódu|Vizualizace organizace a vztahů v existujícím kódu.<br /><br /> Chcete-li identifikovat své metody, třídy a jejich vztahů, vytvořte Mapa kódu, který ukazuje těchto elementů.<br /><br /> Další informace:<br /><br /> -   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)|  
  
###  <a name="DescribeLayers"></a>Logická architektura popisují: závislost diagramy  
 Diagramy závislostí popisují logická architektura systému podle uspořádání artefakty ve vašem řešení do skupiny abstraktní, nebo *vrstvy*. Artefakty může být celou řadu věcí, například obory názvů, projekty, tříd, metod a tak dále. Vrstvy představují a popisují role nebo úlohy, které artefakty provádění v systému. Ověření vrstev můžete použít také v sestavení a operace vrácení se změnami a ujistěte se, že kód zůstává konzistentní s jeho návrhu.  
  
 Pokud chcete zachovat kód konzistentní s návrh, teď večeři a Lucerne použijte následující diagram závislostí ověřit svůj kód vývoj:  
  
 ![Diagram závislostí integrované platebních systému](../modeling/media/layer_integrated_dnlucerne.png "Layer_Integrated_DNLucerne")  
  
 **Diagram závislostí pro večeři nyní integrována Lucerne**  
  
 Vrstvy v tomto diagramu propojit odpovídající artefakty večeři teď a Lucerne řešení. Pro příklad, obchodní vrstvy odkazy na obor názvů DinnerNow.Business a její členy, které nyní zahrnují PaymentApprover třídy. Přístup k prostředkům vrstvy odkazy do oboru názvů DinnerNow.Data. Šipky, nebo *závislosti*, určit, že pouze vrstvě podnikání můžete používat funkci ve vrstvě přístupu k prostředkům. Jak týmy aktualizovat svůj kód, ověření vrstev se provádí pravidelně, catch je v konfliktu, kdy k nim dojde, abyste mohli týmy rychlého řešení.  
  
 Týmy spolupracují přírůstkově integrovat a testování těchto dvou systémech. Se nejprve ujistěte se, že PaymentApprover a zbytek večeři nyní fungovat s navzájem úspěšně před jejich řešit PaymentProcessing.  
  
 Následující mapa kódu zobrazuje nové volání mezi teď večeři a PaymentApprover:  
  
 ![Graf závislostí aktualizované pomocí integrovaného systému](../modeling/media/depgraph_intsystem.png "DepGraph_IntSystem")  
  
 **Mapa kódu pomocí volání aktualizované – metoda**  
  
 Po jejich potvrdit, že systém funguje podle očekávání, teď večeři si kód PaymentProcessing komentáře. Ověření sestavy vrstvy jsou čisté a výsledné Mapa kódu ukazuje, že neexistují žádné další závislosti PaymentProcessing:  
  
 ![Graf závislostí bez PaymentProcessing](../modeling/media/depgraph_nomore.png "DepGraph_NoMore")  
  
 **Mapa kódu bez PaymentProcessing**  
  
#### <a name="drawing-a-dependency-diagram"></a>Kreslení Diagram závislostí  
 Diagram závislostí má následující hlavní funkce:  
  
-   *Vrstvy* popisují logické skupiny artefakty.  
  
-   A *odkaz* je přidružení mezi vrstvou a artefakt.  
  
     Vytvoření vrstev z artefaktů, přetáhněte položky z Průzkumníka řešení, map kódu, zobrazení tříd nebo prohlížeč objektů. Kreslení nové vrstvy a propojit je s artefakty, pomocí panelu nástrojů nebo klikněte pravým tlačítkem myši na povrch diagram vytvoření vrstvy a poté přetáhněte položky na tyto vrstvy.  
  
     Číslo na vrstvě zobrazuje číslo artefaktů, které jsou propojeny s vrstvě. Tyto artefakty může být obory názvů, projekty, tříd, metod a tak dále. Při překladu počet artefakty na vrstvě, mějte na paměti následující:  
  
    -   Pokud vrstva odkazuje na artefakt, který obsahuje jiné artefakty, ale vrstva není propojena přímo s jiným artefaktem, pak číslo obsahuje pouze propojené artefakty. Jiné artefakty jsou však zahrnuty do analýzy během ověřování vrstvy.  
  
         Pokud je vrstva například spojena s jedním oborem názvů, pak počet propojených artefaktů je 1, přestože obor názvů obsahuje třídy. Pokud vrstva obsahuje rovněž propojení s jednotlivými třídami v oboru názvů, bude počet zahrnovat propojené třídy.  
  
    -   Pokud například vrstva obsahuje jiné vrstvy, které jsou spojeny s artefakty, pak je vrstva kontejneru také propojena s těmito artefakty, i když číslo vrstvy kontejneru tyto artefakty neobsahuje.  
  
     Informace o artefakty, které jsou propojeny s vrstvou, klikněte pravým tlačítkem závislost a pak klikněte na tlačítko **zobrazení odkazy** otevřete **Explorer vrstvy**.  
  
-   A *závislostí* označuje, že jedné vrstvy můžete použít funkci v jiné vrstvě, ale ne naopak. A *obousměrného závislostí* označuje, že jedné vrstvy můžete použít funkci v jiné vrstvě a naopak.  
  
     Pokud chcete zobrazit stávající závislosti v diagramu závislostí, klikněte pravým tlačítkem myši na povrch diagramu a klikněte **generovat závislosti**. K popisu určený závislosti, kreslení nové.  
  
 Další informace:  
  
-   [Vytváření diagramů závislostí z kódu](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Diagramy závislostí: Referenční dokumentace](../modeling/layer-diagrams-reference.md)  
  
-   [Diagramy závislostí: Pokyny](../modeling/layer-diagrams-guidelines.md)  
  
-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)  
  
#### <a name="summary-strengths-of-dependency-diagrams"></a>Souhrn: Síly diagramy závislostí  
 Diagramy závislostí vám pomůže:  
  
-   Popisují logická architektura systému podle funkce jeho artefaktů.  
  
-   Ujistěte se, že kód ve vývoji odpovídá zadané návrhu.  
  
#### <a name="relationship-to-other-diagrams"></a>Vztah k jiným diagramům  
  
|**Diagram**|**Popis**|  
|-----------------|---------------------|  
|Mapa kódu|Vizualizace organizace a vztahů v existujícím kódu.<br /><br /> Pokud chcete vytvořit vrstvy, Generovat mapu kódu a poté seskupit položky na mapě jako potenciální vrstvy. Přetáhněte skupiny z mapy diagramu závislostí.<br /><br /> Další informace:<br /><br /> -   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)<br />-   [Procházení a změna uspořádání map kódu](../modeling/browse-and-rearrange-code-maps.md)|  
  
## <a name="external-resources"></a>Externí zdroje  
  
|**Kategorie**|**Odkazy**|  
|------------------|---------------|  
|**Fóra**|-   [Visual Studio vizualizace a modelování nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio vizualizace a modelování SDK (nástroje DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
  
## <a name="see-also"></a>Viz také  
 [Vizualizace kódu](../modeling/visualize-code.md)   
 [Použití modelů ve vývojových procesech](../modeling/use-models-in-your-development-process.md)   
 [Použití modelů ve agilní vývoj](http://msdn.microsoft.com/en-us/592ac27c-3d3e-454a-9c38-b76658ed137f)   
 [Ověřování systému během vývoje](../modeling/validate-your-system-during-development.md)   

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
 
