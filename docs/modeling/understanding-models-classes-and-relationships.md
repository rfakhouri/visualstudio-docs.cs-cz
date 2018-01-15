---
title: "Principy modely, třídy a vztahy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, models
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a3ee963ef1ac4c4159f0fe1922bfafa90875fad7
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="understanding-models-classes-and-relationships"></a>Porozumění modelům, třídám a vztahům
Jazyk specifické pro doménu (DSL) je definován v souboru jeho definice DSL, spolu s vlastní program kód, který může zapsat. Většinu kódu programu v řešení DSL se generují z tohoto souboru.  
  
 Toto téma popisuje funkce centrální DSL definice.  
  
## <a name="the-dsl-definition"></a>Definice DSL  
 Když otevřete `Dsl\DslDefinition.dsl`, vaše [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] okno se podobá následující obrázek.  
  
 ![Návrhář DSL](../modeling/media/dsl_designer.png "dsl_designer")  
  
 V definici DSL nejdůležitější informace se zobrazí v diagramu DSL definice. Další informace, což je také součástí DslDefinition.dsl, se zobrazí v Průzkumníku DSL, které se obvykle zobrazuje na straně diagramu. Pracujete s diagram pro nejčastěji se vyskytující úlohy a pomocí Průzkumníka DSL pro pokročilejší vlastní nastavení.  
  
 Definice DSL diagram znázorňuje třídy domény, které definují prvků modelu a vztahy, které definují propojení mezi elementů modelu. Také ukazuje tvarů a konektory, které se používají k zobrazení prvků modelu pro uživatele.  
  
 ![Návrhář DSL s dráha](../modeling/media/dsl_desinger.png "dsl_desinger")  
  
 Když vyberete položku v definici DSL, diagram nebo v Průzkumníku DSL, zobrazí se informace o něm v okně Vlastnosti. V okně podrobností DSL, může se zobrazit další informace.  
  
### <a name="models-are-instances-of-dsls"></a>Modely jsou instancemi třídy DSL, linky  
 A *modelu* představuje instanci vaše DSL vytvořené uživatelem. Model obsahuje prvky modelu, které jsou instancemi třídy domény, které definujete, a odkazů mezi elementy, které jsou instancemi třídy vztahy domén, které definujete. Model může mít také tvarů a konektory, které budou zobrazovat v diagramu prvků modelu a odkazy. Definice DSL zahrnuje třídy tvaru, konektor třídy a třídy pro diagram.  
  
 Definice DSL je také označován jako *modelu domény*. Model DSL definice nebo domény je reprezentace návrhu jazyka specifické pro doménu, zatímco modelu je spuštění instance jazyka domény.  
  
## <a name="domain-classes-define-model-elements"></a>Domény třídy definují Model elementy  
 Třídy domény se používají k vytvoření různé prvky v doméně a odkazů mezi elementy se vztahy domén. Jsou to reprezentace návrhu elementů a odkazy, které bude vytvořena instance uživatelé jazyka návrhu při vytváření svých modelů.  
  
 Tento obrázek ukazuje model, který byl vytvořen uživatelem knihovna Hudba DSL. Hudba alb jsou reprezentované pomocí polí, které obsahují seznam skladeb. Umělci jsou reprezentované pomocí zaoblenými polí a jsou připojené k alb, ke kterým mají podílí.  
  
 ![Instance modelu generovaného DSL](../modeling/media/music_instance.png "Music_Instance")  
  
 Definice DSL odděluje dva aspekty. Vzhled elementů modelu v diagramu modelu je definována pomocí konektoru třídy a třídy tvaru. Informace v modelu je definována pomocí třídy domény a vztahy domén.  
  
 Následující obrázek znázorňuje třídy domény a vztahy v definici DSL knihovna Hudba.  
  
 ![Vložení a referenční dokumentace vztahy](../modeling/media/music_classes.png "Music_Classes")  
  
 Na obrázku čtyři domény třídy: Hudba, alb, umělcem a skladbu. Domény třídy definují vlastnosti domény, například název, název a tak dále. Ve instance model hodnoty některých z těchto vlastností jsou zobrazeny v diagramu.  
  
 Mezi třídami jsou vztahy domén: MusicHasAlbums, MusicHasArtists, AlbumbHasSongs a ArtistAppearedOnAlbums. Vztahy mít mnohočetnostmi například 1..1, 0.. *. Například každou skladbu musí mít relaci ke přesně jeden Album prostřednictvím AlbumHasSongs relace. Každý Album může mít libovolný počet skladeb.  
  
### <a name="rearranging-the-dsl-definition-diagram"></a>Změna uspořádání Diagram definice DSL  
 Všimněte si, že třídu domény může zobrazit několikrát diagram DSL definice Album stejně jako na tomto obrázku. Je vždy jeden hlavní zobrazení a může být některé *odkaz* zobrazení.  
  
 Chcete-li změnit definici DSL diagramu, můžete:  
  
-   Prohození hlavní a odkazovat na zobrazení pomocí **přineste zde stromu** a **rozdělení stromu** příkazy. Klikněte pravým tlačítkem na jednu doménu třídu chcete zobrazit tyto příkazy.  
  
-   Změnit pořadí domény třídy a třídy tvar stisknutím kombinace kláves Ctrl + šipka nahoru a Ctrl + šipka dolů.  
  
-   Sbalit nebo rozšíření třídy pomocí ikony v pravém horním každého tvaru.  
  
-   Sbalit části stromu kliknutím znaménka minus (-) v dolní části třídu domény.  
  
## <a name="inheritance"></a>Dědičnost  
 Domény třídy lze definovat pomocí dědičnosti. Chcete-li odvození dědičnosti, klikněte na nástroj dědičnosti, klikněte na tlačítko odvozené třídy a potom klikněte na základní třídy. Element modelu má všechny vlastnosti, které jsou definovány na své vlastní třídy domény, společně s všechny vlastnosti zděděn ze základní třídy. Rovněž dědí její role v vztazích.  
  
 Dědičnost mohou sloužit také mezi relace, tvarů a konektory. Dědičnost musí je udržovat v rámci stejné skupiny. Obrazce nelze dědí z třídy domény.  
  
## <a name="domain-relationships"></a>Vztahy domén  
 Prvky modelu lze propojit pomocí relace. Odkazy jsou vždy binární; propojit se právě dva elementy. Ale libovolný element, může mít mnoho odkazy na jiné objekty, a může existovat i více než jeden odkaz mezi stejného páru elementů.  
  
 Stejně jako jiné třídy elementů můžete definovat, můžete definovat různé třídy odkazy. Je volána třída odkazu *relace domény*. Relace domény určuje, které třídy element její instance může připojit. Každý konci relace se nazývá *role*, a relace domény definuje názvy pro dvě role, a také pro vztah sám sebe.  
  
 Existují dva typy vztahů mezi doménami: vložení vztahy a referenčních relací. Diagram DSL definice vnoření vztahy mít plné čáry na každou roli a referenčních relací mít přerušované čáry.  
  
### <a name="embedding-relationships"></a>Vložení relace  
 Každý element v modelu, s výjimkou svůj kořen, je cílem jednoho vnoření propojení. Proto je celý model tvoří jediného stromu vnoření odkazy. Relaci vnoření představuje členství ve skupině nebo vlastnictví. Dva elementy modelu, které souvisejí s tímto způsobem se také označují jako nadřazené a podřízené. Podřízená říká, že je vložit do nadřazené.  
  
 Vnoření odkazy nejsou zobrazeny obvykle explicitně jako konektory v diagramu. Místo toho se obvykle představují členství ve skupině. Kořen modelu je reprezentována diagramu a elementy vložených v ní jsou zobrazeny jako obrazce v diagramu.  
  
 V příkladu má kořenová třída Hudba relaci vnoření MusicHasAlbums do alb, která má vnoření AlbumHasSongs k skladbu. Skladeb zobrazují jako položky v seznamu v každé Album. Hudba má také vnoření MusicHasArtists k třídě umělcem, jejichž instance se zobrazí také jako tvarů v diagramu.  
  
 Ve výchozím nastavení vložené prvky jsou automaticky odstraněna svých nadřazených složek, se odstraní.  
  
 Když je model uložit do souboru ve formátu XML, vložené prvky vnořena ve svých nadřazených složek, pokud jste upravili serializaci.  
  
> [!NOTE]
>  Vložení není stejný jako dědičnosti. Podřízené objekty v relaci vnoření nedědí vlastnosti nadřazeného objektu. Vložení je typ vazby mezi elementy modelu. Dědičnost je vztah mezi třídami a nedojde k vytvoření propojení mezi prvky modelu.  
  
### <a name="embedding-rules"></a>Vložení pravidla  
 Každý element ve instance model musí být cílem přesně jeden vnoření odkaz, s výjimkou kořen modelu.  
  
 Proto každé domény neabstraktní třídy, s výjimkou kořenová třída musí být cílem alespoň jeden vnoření relace, nebo musí dědit, vkládání ze základní třídy. Třída může být cílem vložené dvě části, ale jeho elementy modelu instance může mít pouze jednu nadřazenou položku v čase. Násobnost z cíle do zdroje musí být 0..1 nebo 1..1.  
  
### <a name="the-explorer-displays-the-embedding-tree"></a>Průzkumníku zobrazí stromu vnoření  
 DSL Definition vytvoří také explorer, který uživatelé uvidí spolu s jejich diagramu modelu.  
  
 ![Vygenerovaný explorer DSL](../modeling/media/music_explorer.png "Music_Explorer")  
  
 Průzkumníku ukazuje všechny elementy v modelu, včetně těch, pro které nebyly definovány žádné tvarů. Zobrazuje elementů a vztahů vnoření, ale není odkaz relace.  
  
 Hodnoty vlastnosti domény elementu najdete uživatel vybere na prvek v diagramu modelu nebo v Průzkumníku modelu a otevře se okno Vlastnosti. Zobrazí všechny domény vlastnosti, včetně těch, které nejsou zobrazeny v diagramu. V příkladu skladeb má název i Genre, ale pouze hodnotu názvu je zobrazen v diagramu.  
  
## <a name="reference-relationships"></a>Referenční relace  
 Referenční vztah představuje jakýkoli druh vztah, který není vložení.  
  
 Referenční relace se obvykle zobrazují v diagramu jako konektory mezi tvary.  
  
 V reprezentaci XML modelu odkazem mezi dvěma prvky je reprezentována pomocí *zástupných názvů.* To znamená jsou tyto monikery názvy, které jedinečně identifikují každý prvek v modelu. Uzel XML pro každý element modelu obsahuje uzel, který určuje název relace a moniker jiného elementu.  
  
## <a name="roles"></a>Role  
 Každé domény relace má dvě role, zdrojovou roli a roli cíl.  
  
 Na následujícím obrázku, řádek mezi **vydavatele** třída domény a **PublisherCatalog** relace domény je zdrojovou roli. Řádek mezi relace domény a **Album** domény třída je target role.  
  
 ![Role a vlastnosti. ] (../modeling/media/propertycode.png "PropertyCode")  
  
 Názvy přidružené k relaci jsou zvlášť důležité při psaní kódu programu, který prochází skrz modelu. Například při sestavování řešení DSL generovaná třída vydavatele má vlastnost katalog, který je kolekce alb. Třída Album má vlastnost Publisher, který je jedna instance třídy vydavatele.  
  
 Když vytvoříte vztah v definici DSL, názvy vlastností a vztahů mají výchozí hodnoty. Můžete je však změnit.  
  
## <a name="multiplicities"></a>Mnohočetnostmi  
 Mnohočetnostmi zadejte, kolik prvky můžete mít na stejný atribut role v relaci domény. V příkladu nula m (0..\*) násobnost nastavení na **katalogu** role určuje, že jakoukoli instanci systému **vydavatele** domény třída může mít jako mnoho  **PublisherCatalog** vztah odkazy tak, jak chcete jí přidělit.  
  
 Zadáním v diagramu nebo změnou konfigurace násobnosti atributu role `Multiplicity` vlastnost **vlastnosti** okno. Následující tabulka popisuje nastavení pro tuto vlastnost.  
  
|Násobnost typu|Popis|  
|-----------------------|-----------------|  
|0.. * (nula k mnoha)|Každá instance třídy domény může mít více instancí relace nebo žádné instance relace.|  
|0..1 (nula na jednu)|Každá instance třídy domény může mít více než jednu instanci relace nebo žádné instance relace.|  
|1..1 (jeden)|Každá instance třídy domény může mít jednu instanci relace. Z jakékoli instance třídy roli nelze vytvořit více než jednu instanci této relace. Pokud je povoleno ověření, se zobrazí chyba ověření při jakékoli instance třídy role má žádná instance relace.|  
|1.. * (jedna k mnoha)|Každá instance třídy na roli, která má toto násobnost může mít více instancí relace a každá instance musí mít aspoň jednu instanci relace. Pokud je povoleno ověření, se zobrazí chyba ověření při jakékoli instance třídy role má žádná instance relace.|  
  
## <a name="domain-relationships-as-classes"></a>Vztahy domén jako třídy  
 Odkaz je reprezentována v úložišti jako instanci LinkElement, která je odvozená třída ModelElement. Tyto vlastnosti můžete definovat v diagramu modelu domény u domény relací.  
  
 Relaci můžete provést také v zdroje nebo cíle jiné relace. V diagramu modelu domény, klikněte pravým tlačítkem na vztah domény a pak klikněte na tlačítko **zobrazit jako třída**. Zobrazí se další třídy pole. Pak můžete k němu připojit relací.  
  
 Můžete definovat relaci částečně podle dědičnosti, stejně jako v doméně třídy. Vyberte odvozené relace a nastavte **vztahu základní** v okně Vlastnosti.  
  
 Odvozené relace se specializuje jeho základní relace. Domény třídy to, které odkazy by měl být odvozen od nebo stejný jako propojená vztahem základní třídy. V modelu je vytvořen odkaz odvozené relace, představuje instanci odvozené i základní relace. V programovém kódu můžete přejít na v opačném směru odkaz pomocí vlastnosti generovány základní nebo odvozené třídy.  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)
