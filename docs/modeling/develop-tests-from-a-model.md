---
title: Vývoj testů z modelu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- tests and requirements
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 0982bc72a98be6f015d580f3170a5790fe941867
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="develop-tests-from-a-model"></a>Vývoj testů z modelu
Požadavky a architektury modely můžete uspořádat testy systému a jeho součástí. Tento postup pomáhá, zajistěte, aby test požadavky, které jsou důležité pro uživatele a dalších zúčastněných osob a pomůže vám rychle aktualizovat testy při změně požadavky. Pokud používáte [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], můžete také zachovat propojení mezi modely a testy.  
  
 Informace, které verze sady Visual Studio podporují tyto funkce, najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="system-and-subsystem-testing"></a>Systém a testování subsystému  
 *Testování systému* také označované jako *testování přijetí*, znamená testování, zda byly splněny požadavky uživatelů. Tyto testy se zajímá externě viditelné chování systému místo interní návrhu.  
  
 Systémových testů jsou velmi cenné při rozšíření nebo přepracování systému. Mohou pomoci vyhnout se představení chyby při změně kódu.  
  
 Při plánování všech změn nebo rozšíření na systém, je užitečné začít s sadu systémových testů, které běží na stávajícím systému. Pak můžete rozšířit nebo upravit testů na testování nové požadavky, proveďte změny kódu a znovu spusťte kompletní sadu testů.  
  
 Při vývoji nového systému, můžete začít vytvářet testy ihned zahájí vývoj. Definováním testy předtím, než budete vyvíjet jednotlivých funkcí, můžete zaznamenat diskusí požadavky způsobem, velmi konkrétní.  
  
 Testování subsystému platí stejné zásady pro hlavní součásti systému. Jednotlivé komponenty je testován odděleně od ostatních součástí. Subsystém testuje se zaměřují na chování viditelné v součásti uživatelského rozhraní nebo rozhraní API.  
  
## <a name="deriving-system-tests-from-a-requirements-model"></a>Odvozování systémových testů z modelu požadavky  
 Můžete vytvořit a Udržovat vztah mezi systémových testů a požadavky na modelu. Chcete-li vytvořit tento vztah, zápisu testy, které odpovídají hlavních prvků modelu požadavky. Visual Studio je chránit vaše dosavadní relace umožňují vytvářet propojení mezi testy a součástí modelu. Další informace o modelech požadavky najdete v tématu [modelování uživatelských požadavků](../modeling/model-user-requirements.md).  
  
### <a name="write-tests-for-each-use-case"></a>Zápis testů pro každý případ použití  
 Pokud používáte [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], můžete vytvořit skupinu testů pro každý případ použití, který jste definovali ve model požadavky. Například pokud máte případ použití pořadí jídlem, což zahrnuje vytvoření pořadí a přidat položku pořadí, můžete vytvořit testů pro obě celkovým a podrobnější z těchto případů použití. 
  
 Může být užitečné tyto pokyny:  
  
-   Každý případ použití by měl mít několik testů pro hlavní cesty a výjimečných výstupy.  
  
-   Pokud jste popisují případu použití v modelu požadavky, je důležitější zadat jeho koncová podmínka, který je cíl, který je dosaženo, než k popisu podrobné postupy uživatel bude postupovat aby bylo možné dosáhnout. Koncová podmínka pořadí jídlem může být například která restaurace se připravuje jídlem pro zákazníka a že zákazník má placené. Koncová podmínka je kritérium, které by měl ověřit testy.  
  
-   Základní samostatné testy na samostatné klauzulích koncová podmínka. Můžete například vytvořte samostatné testy pro oznamování restaurace objednávky a za vyjádření platby od zákazníka. Toto oddělení má tyto výhody:  
  
    -   Změny v různých aspektů požadavky nastat často nezávisle. Oddělením testů na různé aspekty tímto způsobem můžete usnadňují aktualizovat testy při změně požadavků.  
  
    -   Pokud plán vývoj implementuje jeden aspekt jejich případ použití před jiný, můžete povolit testy samostatně jako postupuje vývoj.  
  
-   Při návrhu testy oddělte volba testovací data z kódu nebo skriptu, který určuje, zda bylo dosaženo koncová podmínka. Například může být testu jednoduché aritmetické funkce: vstup 4; Ověřte, zda je výstup 2. Místo toho návrh do skriptu jako: Zvolte vstup; násobení výstup samostatně a ověřte, zda je výsledek původní vstup. Tento styl umožňuje lišit vstupy testovací beze změny hlavního textu testu.  
  
#### <a name="linking-tests-to-use-cases"></a>Propojování testy na případy použití  
 Pokud používáte [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)] návrh a spouštění testů, můžete uspořádat testů v části požadavky, případ použití nebo uživatelské scénáře pracovních položek. Můžete se propojit tyto pracovní položky pro případy použití v modelu. To vám umožňuje rychle změny trasování požadavků na testy a pomáhá sledovat průběh každý případ použití.  
  
###### <a name="to-link-tests-to-a-use-case"></a>Propojení případu použití testů  
  
1.  V [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)], vytvořit požadavek a základní sady testů na něm.
  
     Požadavek, který vytvoříte je pracovní položku v [!INCLUDE[vstsTfsShort](../modeling/includes/vststfsshort_md.md)]. Může to být uživatelský scénář, požadavek nebo případ použití pracovní položkou, v závislosti na šabloně procesu, kterou používá váš projekt s [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]. Další informace najdete v tématu [sledování práce pomocí sady Visual Studio Team Services nebo Team Foundation Server](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503).  
  
2.  Pracovní položky požadavku na odkaz na jeden nebo více případy použití v modelu.  
  
     V diagramu případu použití, klikněte pravým tlačítkem na případ použití a pak klikněte na tlačítko **odkaz na pracovní položku**. 
  
3.  Přidejte do testovací sada, testovací případy, které ověřují případy použití.  
  
 Obvykle každé uživatelské scénáře nebo požadavky pracovní položky bude propojit několik případů použití v modelu a každý případ použití odkaz na několik uživatelské scénáře nebo požadavky. Je to proto, že každý uživatelský scénář nebo požadavek popisuje sadu úloh, které vyvíjet několik případů použití. Například v iterace časná projektu, může vyvíjet základní uživatelské scénáře, ve kterém můžete zvolit položky z katalogu a bylo dodáno zákazníka. Článek v novější iteraci, může být, že uživatel platí při dokončení pořadí a dodavatel obdrží peníze po odešle zboží.  Každý článek přidá klauzuli koncová podmínka případu použití zboží pořadí.  
  
 Můžete vytvořit samostatné odkazy z požadavky do klauzulích koncová podmínka napsáním tyto klauzule v samostatných komentáře v diagramu případu použití. Můžete propojit každý komentář k pracovní položce požadavek a propojit případ použití v diagramu komentář.  
  
### <a name="base-tests-on-the-requirements-types"></a>Základní testy na typy požadavků  
 Typy, které je, třídy, rozhraní a výčty modelu požadavky popisují koncepty a vztahy z hlediska jak uživatelé myslíte a komunikaci o své firmy. S vyloučením typy zajímají pouze k internímu řešení systému.  
  
 Návrh testů z hlediska tyto typy požadavků. Tento postup umožňuje Ujistěte se, že když jsou popsány změny požadavků na, je snadné se týkají změny potřebné změny v testech. Ji umožňuje zabývat testy a jejich zamýšlený výsledky přímo s koncovým uživatelům a dalších zúčastněných osob. To znamená, že uživatelů musí je udržovat mimo procesu vývoje a zabraňuje nechtěnému návrhu testů kolem možné nedostatky v návrhu.  
  
 Pro ruční testy tento postup zahrnuje se termínů modelu požadavky ve skriptech testu. Pro automatizované testy tento postup zahrnuje použití diagramů tříd požadavky jako základ pro testovacího kódu a vytváření přistupujícího objektu a aktualizační funkce propojení požadavek model pomocí kódu.  
  
 Například požadavky, které mohou zahrnovat modelu typy nabídky, položky nabídky, pořadím a přidružení mezi nimi. Tento model představuje informace, které je uložený a řešil jídlem řazení systému, ale nepředstavuje složitosti jeho implementace. V pracovní systému může být několik různých realizations každého typu v databázích, v uživatelská rozhraní a na rozhraní API. V distribuované systému může být několik variant každá instance uložené v různé části systému ve stejnou dobu.  
  
 K testování případ použití, jako je například přidat položku pořadí, můžou zahrnovat metoda testovací kód podobná této:  
  
```  
Order order = ... ; // set up an order  
// Store prior state:  
int countBefore = order.MenuItems.Count;   
// Perform use case:  
MenuItem chosenItem = ...; // choose an item  
AddItemToOrder (chosenItem, order);   
// Verify part of postcondition:  
int countAfter = order.MenuItems.Count;  
Assert (countAfter == countBefore = 1);   
```  
  
 Všimněte si, že tato metoda používá třídy modelu požadavky. Přidružení a atributy jsou realizovány jako vlastnosti .NET.  
  
 Chcete-li tato práce, vlastnosti třídy musí být definovaný jako funkce jen pro čtení nebo přístupové objekty, které přístup k systému k načtení informací o aktuálním stavu. Metody, které simulují případy použití, jako je AddItemToOrder musí jednotky systému prostřednictvím jejího rozhraní API nebo vrstva pod jeho uživatelské rozhraní. Konstruktory testovací objektů, jako je například pořadí a MenuItem musí také jednotky systému vytvořte odpovídající položky v rámci systému.  
  
 Řadu přístupové objekty a operace Updater bude již k dispozici prostřednictvím rozhraní API normální aplikace. Ale některé další funkce možná má být proveden zápis, aby bylo možné povolit testy. Tyto další přístupové objekty a operace Updater se někdy označují jako 'test instrumentace'. Protože závisejí na interní návrh systému, je zodpovědností systému vývojáři získají, zatímco testery napsat kód testů z hlediska požadavků modelu.  
  
 Při psaní automatizovaných testů můžete zabalit přístupové objekty a operace Updater obecné testy.
  
### <a name="tests-for-business-rules"></a>Testy u obchodních pravidel  
 Některé požadavky přímo nesouvisejí s žádné jeden případ použití. Například obchodní DinnerNow umožňuje zákazníkům vybrat z mnoha nabídky, ale vyžaduje, aby v každé pořadí všechny zvolené položky musí být z jednoho nabídky. Toto obchodní pravidlo může být vyjádřený jako neutrální o přidružení mezi objednávky, nabídky a položky v modelu třída požadavky.  
  
 Výchozí pravidlo druhu řídí pouze všechny případy použití, které jsou aktuálně definovány, ale také všechny další případy použití, které budou později určené. Proto je užitečný pro zápis samostatně z jakékoli případ použití a k testování samostatně z případy použití.  
  
## <a name="deriving-subsystem-tests-from-models"></a>Odvozování subsystému testy z modelů  
 V návrhu vysoké úrovně velké systému můžete identifikovat součásti nebo subsystémy. Tyto představují částí, které může být navrženy samostatně, nebo jsou umístěny na různých počítačích nebo jsou opakovaně použitelné moduly, které můžete rekombinované mnoha způsoby. 
  
 Můžete použít pro každou hlavní součást stejnými zásadami jako použijte pro celý systém. Ve velkých projektech jednotlivé komponenty může mít vlastní požadavky model. V menší projekty Architektonický model nebo hlavnímu návrhu vytvořit zobrazíte součástech a jejich interakce. Další informace najdete v tématu [modelování architektury aplikace](../modeling/model-your-app-s-architecture.md).  
  
 V obou případech můžete vytvořit vztah mezi prvků modelu a testy subsystém stejným způsobem, jako byste mezi požadavky modelu a systémových testů.  
  
### <a name="isolate-components-with-provided-and-required-interfaces"></a>Izolace součásti pomocí zadaného a požadované rozhraní  
 Je užitečný k identifikaci všechny závislosti, které má komponentu na dalších částí systému nebo externích služeb a k reprezentaci jako požadované rozhraní. Tento postup obvykle vede k některé změna, která zůstane komponentu mnohem víc odpojeného a snadno oddělit od ostatního návrhu.  
  
 Výhodou tohoto oddělení je, že součást mohou být provedeny pro testování nahrazením mock objektů služby, které se obvykle používá. Tyto jsou komponenty, které jsou nastavené pro účely testování. Komponentu imitované poskytuje rozhraní, které vyžaduje příslušné součásti, odpovídá na dotazy simulované daty. Komponenty imitované součástí dokončení testovacího harness, který můžete připojit na všechna rozhraní, které součásti.  
  
 Výhodou imitované testování je, že můžete vyvíjet příslušné součásti při s ostatními součástmi, jejichž služby se bude používat jsou stále ve vývoji.  
  
## <a name="maintain-the-relationships-between-tests-and-model"></a>Spravovat vztahy mezi testy a modelu  
 V typické projektu, který provádí iterace každých několik týdnů trvá Zkontrolujte požadavky na začátku každé iteraci. Schůzka popisuje funkce, které jsou dodávány v další iterace. Požadavky na modelu slouží k pomoci zabývat koncepty, scénáře a pořadí akcí, které se vyvinul. Účastníci firmy nastavit prioritu, vývojáři zkontrolujte odhad a testery Ujistěte se, že očekávané chování každé funkce pořízen správně.  
  
 Zápis testů je co nejúčinnější způsob, jak definovat požadavek, který je taky efektivní způsob, jak zkontrolujte, zda uživatel má vědět, co je požadováno. Ale že zápis testy trvá příliš dlouho udělat během dílny specifikace, vytváření modelů lze provést mnohem rychleji.  
  
 Z testování hlediska se dají považovat za sdruženou hodnotu pro testy model požadavky. Proto je důležité zachovat vztah mezi testy a modelu v rámci projektu.  
  
##  <a name="Attaching"></a> Připojení testovacích případů pro modelování elementy  
 Pokud váš projekt používá [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)], můžete propojit testy elementy v modelu. To umožňuje rychle najít testy vliv na změny v požadavcích na a vám pomůže sledovat v rozsahu, ke kterému bylo dosaženo požadavek.  
  
 Testy můžete propojit všechny typy elementu. Následuje několik příkladů:  
  
-   Propojení případu použití pro testy, které vykonávají ho.  
  
-   Zápis klauzulích koncová podmínka případů použití, nebo cílem na komentáře, které jsou propojeny s případ použití a testy propojit každý komentář.  
  
-   Zápis invariantní pravidla v komentářích na diagramů tříd nebo diagramy činnosti a propojit je s testy.  
  
-   Propojit testy diagram činnosti, nebo se jednotlivé aktivity.  
  
-   Sady testů propojte součásti nebo podsystém, který testuje.  
  
#### <a name="to-link-tests-to-a-model-element-or-relationship"></a>Propojení testy element modelu nebo relace  
  
1.  V [!INCLUDE[TCMlong](../modeling/includes/tcmlong_md.md)], vytvořit požadavek a základní sady testů na něm. 
  
     Požadavek, který vytvoříte je pracovní položku v [!INCLUDE[vstsTfsShort](../modeling/includes/vststfsshort_md.md)]. Může to být uživatelský scénář, požadavek nebo případ použití pracovní položkou, v závislosti na šabloně procesu, kterou používá váš projekt s [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]. Další informace najdete v tématu [sledování práce pomocí sady Visual Studio Team Services nebo Team Foundation Server](http://msdn.microsoft.com/Library/52aa8bc9-fc7e-4fae-9946-2ab255ca7503).  
  
2.  Pracovní položky požadavku propojte jeden či více elementů v modelu.  
  
     V diagramu modelování, klikněte pravým tlačítkem na prvek, komentáře nebo relace a pak klikněte na tlačítko **odkaz na pracovní položku**.
  
3.  Přidejte do testovací sadu, testovacích případů, které ověřují požadavek vyjádřené v elementu modelu.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření modelů pro aplikaci](../modeling/create-models-for-your-app.md)   
 [Modelování uživatelských požadavků](../modeling/model-user-requirements.md)   
 [Modelování architektury aplikace](../modeling/model-your-app-s-architecture.md)   
 [Analýza a modelování vaší architektury](../modeling/analyze-and-model-your-architecture.md)
