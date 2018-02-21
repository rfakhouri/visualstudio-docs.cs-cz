---
title: "Použití modelů ve vývojových procesech | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-modeling
ms.topic: get-started-article
helpviewer_keywords:
- UML, using models
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4d8d9b5632831c1d336f359aa4e4468da1543c73
ms.sourcegitcommit: bfa26fd7426af0d065cb2eef3d6827b5d6f7986c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/20/2018
---
# <a name="use-models-in-your-development-process"></a>Použití modelů ve vývojových procesech

V sadě Visual Studio můžete v modelu vám pomůžou pochopit a změnit systému, aplikace nebo součást. Model můžete vizualizovat na světě, ve kterém funguje systému, vysvětlení potřeby uživatelů, definovat architekturu systému, analyzovat kód a ujistěte se, že váš kód splňuje požadavky. Najdete v části [Channel 9 Video: architektura prostřednictvím modelování zlepšení](http://go.microsoft.com/fwlink/?LinkID=252078).

Informace, které verze sady Visual Studio podporovat každý typ modelu, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).

Modely vám můžou pomoct několika způsoby:

- Kreslení diagramy modelování pomáhá vysvětlení s koncepty týkajícími se požadavky, architektury a návrhu vysoké úrovně. Další informace najdete v tématu [modelování uživatelských požadavků](../modeling/model-user-requirements.md).

- Práce s modely můžete vystavit nekonzistence v požadavky.

- Umožňuje komunikaci s modely komunikovat důležité koncepty menší ambiguously než v přirozeném jazyce. Další informace najdete v tématu [modelování architektury aplikace](../modeling/model-your-app-s-architecture.md).

- V některých případech můžete modely pro generování kódu nebo jiné artefaktů, jako jsou databáze schémata nebo dokumenty. Například modelování součásti sady Visual Studio se generují z modelu. Další informace najdete v tématu [generování a konfigurace aplikace z modelů](../modeling/generate-and-configure-your-app-from-models.md).

Můžete vytvořit modely v celé řadě procesů z extrémně agilní na vysoká procedury.

## <a name="use-models-to-reduce-ambiguity"></a>Použití modelů ke snížení nejednoznačnosti

Modelování jazyk je nejednoznačný méně než přirozeného jazyka a je navržen pro express nápady, obvykle vyžadují při vývoji softwaru.

Pokud váš projekt má malých týmů následující agilní postupy, můžete použít modely můžete vysvětlení uživatelských scénářů. Diskuze s zákazníka o jejich potřeb vytvoření modelu můžete vygenerovat užitečné otázky mnohem rychlejší a napříč širší oblasti produktu, než psaní kódu Špička nebo prototypu.

Pokud váš projekt je velký a zahrnuje týmy v různých částech celém světě, můžete použít modely pomohou komunikovat požadavky a architektura mnohem efektivnější než ve formátu prostého textu.

V obou případech vytvoření modelu téměř vždy vede k výraznému snížení nekonzistence a nejednoznačnosti. Různé zúčastněným stranám často mají různé ujednání World firmy, ve kterém funguje v systému a různé vývojáři často mají různé ujednání toho, jak funguje v systému. Použití modelu jako fokus se zabývat obvykle zpřístupní tyto rozdíly. Další informace o tom, jak používat model ke snížení nekonzistence najdete v tématu [modelování uživatelských požadavků](../modeling/model-user-requirements.md).

## <a name="use-models-with-other-artifacts"></a>Použití modelů s artefaktů

Model není sám o sobě specifikaci požadavky nebo architekturu. Je nástroj pro více jasně vyjádření některé aspekty těchto věcí, ale ne všechny koncepty požadované při návrhu softwaru může být vyjádřený. Modely proto je nutné použít společně s jiným způsobem komunikace, například stránky v OneNote nebo odstavců, dokumentů Microsoft Office, pracovní položky v [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)], nebo rychlé poznámky na wall místnosti projektu. Kromě poslední položky všechny tyto typy objektů lze propojit s prvky součásti modelu.

Další aspekty specifikace, obvykle používané společně s modely patří. V závislosti na rozsahu a styl projektu může použít několik těchto aspektů nebo vůbec žádné použitím:

- Uživatelské scénáře. Uživatelský scénář je stručný popis, popsané s uživateli a ostatní účastníci aspektu chování systému, který bude doručen v jednom z projektu iterací. Typické uživatelský scénář začíná "zákazník bude moct..." Uživatelský scénář může způsobit skupinu případů použití, nebo můžete definovat rozšíření případy použití, které byly vyvinuty dříve. Definování nebo rozšíření případy použití pomáhá provést jasnější uživatelského scénáře.

- Žádosti o změnu. Žádost o změnu v více formální projektu je velmi podobná uživatelského scénáře v projektu na agilní. Agilní přístup zpracovává všechny požadavky jako změny na co byla vyvinuta v předchozí iterací.

- Použijte popis případu. Případ použití představuje jeden ze způsobů, ve kterém uživatel pracuje s systému pro dosažení určitého cíle. Úplný popis zahrnuje cíle, hlavní a alternativní pořadí událostí a výjimečných výstupy. Diagramu případu použití pomáhá shrnout a poskytovat přehled o případy použití.

- Scénáře. Scénář je docela podrobný popis pořadí událostí zobrazuje, jak systému, uživatelů a jiné systémy vzájemně spolupracují a zadejte hodnotu zúčastněným stranám. Může trvat tvaru slide show uživatelského rozhraní nebo prototyp uživatelské rozhraní. Můžete ho popisují případ použití jednoho nebo posloupnost případy použití.

- Glosář. Glosář požadavky projektu popisuje slova, pomocí kterých zákazníci zabývat jejich world. Uživatelské rozhraní a požadavků na modely měli použít také tyto podmínky. Diagram třída může pomoci vysvětlení vztahy mezi většinu tyto podmínky. Vytváření diagramů a glosář pouze snižuje nedorozuměním mezi uživateli a vývojáře, ale také téměř vždy zpřístupní nedorozuměním mezi různých obchodních zúčastněným stranám.

- Obchodní pravidla. Mnoho obchodní pravidla může být vyjádřený jako výchozí omezení u přidružení a atributů v modelu třída požadavky a jako omezení v diagramech pořadí.

- Hlavnímu návrhu. Popisuje hlavní části a jak je umístit společně. Součást, pořadí a diagramy rozhraní jsou hlavní součástí hlavnímu návrhu.

- Vzory návrhu. Popis pravidla návrhu, které jsou sdíleny mezi různé části systému.

- Otestujte specifikace. Test skripty a návrhy pro testovací kód můžete provést vhodné využít aktivity a pořadí diagramy k popisu pořadí kroků testu. Systémových testů by měla být vyjádřena z hlediska požadavků modelu tak, aby se snadno jde změnit, pokud požadavky na změnu.

- Plánu projektu. Plánu projektu nebo nevyřízených položek definuje, kdy budou doručeny každou funkci. Jednotlivé funkce můžete definovat pomocí s informacemi o tom, co použít případy a obchodní pravidla se implementuje nebo rozšiřuje. Buď najdete případy použití a obchodní pravidla přímo v plánu nebo můžete definovat sadu funkcí, v samostatných dokumentu a použijte funkci názvy v plánu.

## <a name="use-models-in-iteration-planning"></a>Použití modelů ve plánování iterace

I když jsou všechny projekty v jejich škálování a organizace liší, je jako řadu opakování mezi dvěma a šesti týdny plánované typické projektu. Je důležité naplánovat dostatek iterací povolit zpětnou vazbu od časná iterací, který se má použít k nastavení oboru a plány pro novější iterací.

Následující návrhy vám může být užitečné pomohou pochopit výhody modelování v iterativní projektu.

### <a name="sharpen-focus-as-each-iteration-approaches"></a>Zostřit fokus jako každé iteraci blíží

Jako každé iteraci blíží, používejte modely chcete určit, co se má doručit na konci iterace.

- Model není všechno podrobně v časná iterací. V první iteraci vytvořit diagramu tříd pro hlavní položky v glosáři uživatele, kreslení diagram případů hlavní využití a kreslení diagram hlavní součásti. Nepopisují některý z těchto jemné podrobně, protože podrobností změní později v projektu. K vytvoření seznamu funkcí nebo hlavní uživatelské scénáře použijte definovaná v tomto modelu. Funkce přiřadíte iterací tak, aby přibližně vyrovnávání zátěže odhadované v rámci projektu. Tato přiřazení se změní později v projektu.

- Pokuste se implementovat v iterace časná zjednodušené verzích všechny nejdůležitější případy použití. Rozšíření ty případy použití v novější iterací. Tento přístup pomáhá snížit riziko zjišťování závadu v požadavcích na nebo architekturu příliš pozdní v projektu udělat něco o něm.

- Téměř na konci každé iteraci uloženy požadavky dílny podrobně definovat požadavky nebo uživatelskými scénáři, které bude vyvinuté v další iterace. Pozvěte uživatelům a zúčastněným stranám firmy, kteří se můžete rozhodnout, priority, a také vývojářům a testery systému. Povolit tři hodiny určit požadavky pro iterace 2týden.

- Cílem pracoviště je pro každého souhlasit, co se provádí na konci další iterace. Pomocí modely jako jeden z nástrojů vysvětlení požadavky. Výstup pracoviště je nevyřízené položky iteraci: tedy seznam vývoj úloh v [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] a testovací sady v [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)].

- V požadavky na pracoviště zabývat návrh pouze, pokud jsou je potřeba určit odhady pro vývoj úlohy. Jinak použijte diskuzi na chování systému, který uživatelé mohou zaznamenat přímo. Požadavky na modelu oddělte od Architektonický model.

- Běžné uživatele zúčastněným stranám mají obvykle žádné problémy pochopení diagramů UML, přičemž některé pokyny od vás.

### <a name="link-model-to-work-items"></a>Model odkazu na pracovní položky

Po požadavky na pracoviště vypracovala podrobnosti požadavky modelu a modelu propojit vývojářských úloh. Můžete to provést pomocí propojení pracovních položek v [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] na elementy v modelu.

Můžete propojit libovolného elementu k pracovním položkám, ale nejužitečnější elementy jsou následující:

- Komentář popisující obchodních pravidel nebo kvality služeb požadavky. Další informace najdete v tématu [modelování uživatelských požadavků](../modeling/model-user-requirements.md).

### <a name="link-model-to-tests"></a>Odkaz modelu do testů

Pomocí modelu požadavky na návrh přijetí testů. Vytvořte tyto testy souběžně vývojové práci.

Další informace o tato technika, najdete v části [vývoj testů z modelu](../modeling/develop-tests-from-a-model.md).

### <a name="estimate-remaining-work"></a>Odhad zbývající práce

Požadavky na modelu může pomoci odhadnout celková velikost projektu ve vztahu k velikost každé iteraci. Hodnocením číslo a složitost případy použití a třídy vám může pomoci odhadnout vývoji, které se bude vyžadovat. Když jste dokončili první několik iterací porovnání požadavky popsané a požadavky, je stále tak, aby pokrývalo mohou poskytnout přibližnou míru náklady a oboru zbytku projektu.

Téměř na konci každé iteraci zkontrolujte přiřazení požadavky na budoucí iterací. Může být užitečné představující stav softwaru na konci každé iteraci jako subsystému v diagramu případu použití. Diskuze můžete přesunout případy použití a použít případu rozšíření z jednoho z těchto subsystémy do jiného.

## <a name="levels-of-abstraction"></a>Úrovní abstrakce

Modely mají celou řadu abstrakce ve vztahu k softwaru. Většina konkrétní modely přímo představují programovém kódu a nejvíce abstraktní modely představují obchodní koncepty, které může nebo nemusí být reprezentován v kódu.

Model lze zobrazit pomocí několik druhů diagramů. Informace o modelů a diagramů najdete v tématu [vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md).

Různé druhy diagramu jsou užitečné pro popisující návrh s různou úrovní abstrakce. Mnoho typů diagramu jsou užitečné na více než jedné úrovni. Tato tabulka ukazuje, jak se dají využít každý typ diagramu.

|Úroveň návrhu|Diagram typy|
|------------------|-------------------|
|Obchodní proces<br /><br /> Principy kontext, ve kterém se použije váš systém vám pomůže pochopit uživatelé musí z něj.|– Diagramy tříd koncepční popisují koncepty obchodní používaných v rámci obchodní proces.|
|Požadavky na uživatele<br /><br /> Definice toho, co uživatelé potřebovat z vašeho systému.|-Obchodní pravidla a kvalitu služeb požadavky můžete popsané v samostatné dokumenty.|
|Vysoké úrovně návrhu<br /><br /> Celková struktura systému: hlavní součásti a jak se spojte společně.|– Diagramy závislost popisují struktury systému na konkrétní části. Můžete ověřit kód programu proti závislostí diagramy zajistit, že bude odpovídat architektuře.|
|Analýza kódu<br /><br /> Diagramy lze vygenerovat z kódu.|– Diagramy závislost zobrazit závislosti mezi třídami. Aktualizovaný kódu můžete ověřovat na diagram závislostí.<br />– Diagramy tříd zobrazit třídy v kódu.|

## <a name="external-resources"></a>Externí zdroje

|**Kategorie**|**Odkazy**|
|------------------|---------------|
|**Videa**|![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [MSDN How do I videa: postup vytvoření a použití modelů a diagramů UML (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkId=214460)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: UML s Visual Studio 2010](http://go.microsoft.com/fwlink/?LinkID=201106)<br /><br /> ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo") [MSDN How do I řady: UML nástrojů a rozšíření (Visual Studio 2010 Ultimate)](http://go.microsoft.com/fwlink/?LinkID=214467)|
|**Fóra**|- [Visual Studio vizualizace a modelování nástroje](http://go.microsoft.com/fwlink/?LinkId=184720)<br />- [Visual Studio vizualizace a modelování SDK (nástroje DSL)](http://go.microsoft.com/fwlink/?LinkId=184721)|
|**Blogy**|[Visual Studio ALM + Team Foundation Server Blog](http://go.microsoft.com/fwlink/?LinkID=201340)|
|**Technické články a deníků**|[Architektura softwaru MSDN](http://go.microsoft.com/fwlink/?LinkId=201343)<br /><br /> [Pokyny k nástrojům architektury sady Visual Studio](../modeling/visual-studio-architecture-tooling-guidance.md)|

## <a name="see-also"></a>Viz také

[Použití modelů ve agilní vývoj](http://msdn.microsoft.com/592ac27c-3d3e-454a-9c38-b76658ed137f) 
[vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md) 
[modelování uživatelských požadavků](../modeling/model-user-requirements.md) 
[modelu vaší aplikace Architektura](../modeling/model-your-app-s-architecture.md) 
[vývoj testů z modelu](../modeling/develop-tests-from-a-model.md) 
[strukturujte svá řešení modelování](../modeling/structure-your-modeling-solution.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
