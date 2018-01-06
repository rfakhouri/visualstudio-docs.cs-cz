---
title: "Glosář sady Visual Studio SDK | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: glossary [Visual Studio SDK]
ms.assetid: b64d432b-c39b-4904-ad18-3c3218b6e3aa
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fa0f7eaed09df717eb0746076715f9c780464df1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-sdk-glossary"></a>Glosář sady Visual Studio SDK
Tento glosář poskytuje definice podmínek, které se používají v [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] dokumentaci.  
  
## <a name="terms"></a>Podmínky  
 doplněk  
 Nástroj aplikací, ovladačů nebo jiný software přidané do primární aplikace. V sadě Visual Studio integrované vývojové prostředí (IDE) je doplněk aplikace založené na automatizaci, která rozšiřuje možnosti prostředí IDE.  
  
 model automatizace  
 Model automatizace známé v předchozích verzích sady Visual Studio jako model rozšiřitelnosti je programovací rozhraní, která poskytuje přístup k základní rutiny tuto jednotku prostředí IDE. Doplňky, průvodců a makra použít objekty v modelu automatizace pro ovládací prvek nebo rozšířit funkci rozhraní IDE.  
  
 příkaz kontextu uživatelského rozhraní  
 Identifikátor GUID přidružení viditelnost příkaz uživatelského rozhraní nebo elementu například panelu nástrojů. Příkaz uživatelského rozhraní kontext není na rozdíl od kontextu výběr v tom, že není připojený k časového období.  
  
 Kontext uživatelského rozhraní příkazů umožňuje:  
  
-   Identifikátor GUID přiřadíte panel nástrojů, který se zobrazí, když se aktivuje konkrétní okno.  
  
-   Bez nutnosti načtení nebo spuštění VSPackage přiřadíte dostupnost příkaz identifikátor GUID.  
  
-   Přiřaďte identifikátor GUID ovlivnit active vazbu na klíč.  
  
-   Přiřaďte identifikátor GUID zapnutí záznam makra.  
  
-   Přiřaďte identifikátor GUID k aktivaci režimu ladění, nebo k přepnutí mezi návrhu a spuštění režimu v editoru.  
  
 komponenta  
 Softwarového produktu, který může být součástí funkce aplikace bez nutnosti jakékoli existující informace o implementaci softwarové aplikace. Komunikace mezi komponenty a aplikace je výhradně prostřednictvím rozhraní OLE stylu.  
  
 Správce komponent  
 Může služba `SOleComponentManager`, který poskytuje služby koordinaci bez uživatelského rozhraní pro součásti nejvyšší úrovně. `SOleComponentManager` Služby implementuje `IOleComponentManager` rozhraní.  
  
 Správce součástí uživatelského rozhraní  
 Může služba `SOleComponentUIManager`, který poskytuje uživatelské rozhraní spolupráce služeb. `SOleComponentUIManager` Služby implementuje `IOleComponentUIManager` a `IOleInPlaceComponentUIManager` rozhraní.  
  
 kontext kontejner objektů a dat  
 `IVsUserContext` Objektů (objekt COM) připojené k komponentu prostředí. Tento objekt obsahuje klíčová slova pro vyhledávání, klíčová slova F1 a atributy, které se týkají komponentu. Kontext sáčků dále přejděte na žádné dílčí kontext sáčky, které jsou propojeny s je.  
  
 kontext zprostředkovatele  
 Komponenta v integrovaném vývojovém prostředí, který má kontejner kontext s ním spojená. Tyto součásti zahrnují okno nástroje, editor nebo hierarchii projektu.  
  
 návrhář  
 Programovací rozhraní, které umožňuje uživatelům pracovat s prvky uživatelského rozhraní (formuláře, tlačítek a jiných ovládacích prvků).  
  
 DocData  
 Objekt COM zapouzdřením v základních datech dokumentu světě níž se nachází oddělení dokument/zobrazení (například v případě, textový editor, by to byl textová vyrovnávací paměť základní všechna zobrazení textového editoru). Pokud EditorFactory neposkytuje tento objekt, bude výroba IDE jeden jeho jménem. Je zodpovědností tohoto objektu je správa trvalosti dat a sdílení sémantiky pro více zobrazení přes to stejné `DocData`. Pokud `DocData` objektu podporuje `IOleCommandTarget` rozhraní, ji budou zahrnuty do směrování příkazů UIShell.  
  
 DocObject  
 Technologie používané k hostování uživatelského rozhraní v rámci od hostitele. Přesněji řečeno, tento termín se vztahuje na všechny vložení, který podporuje `IOleDocument` a související rozhraní. Tato technologie má mnoho potenciální aplikací, jako jsou například podrobností implementace dokumentů COM, nástroj windows v jazyce Visual Basic 5.0, Designer ActiveX v jazyce Visual Basic 6.0 a tak dále.  
  
 dokument  
 Lze obecně naleznete v dokumentu jako celku – jak `DocData` a `DocView`. Například DocumentFrame obsahuje `DocView`, ale také zachová odkaz na `DocData` pro zpracování trvalost.  
  
 DocView  
 DocObject, vkládání objektů nebo WindowPane, pomocí kterého uživatel pracuje k zobrazení a manipulaci s základní `DocData`. Všimněte si, uživatelé nemusí provádět žádné výhod Document/View – oddělení, který je součástí `DocObject` rozhraní návrhu. Uživatelé používat celý DocObject tak, aby fungoval jako zobrazení místo použití více abstraktní (a méně formalizovanou) hodnoty základní dat označuje jako `DocData`. `DocView`objekty jsou vždy integrované s objekty rámce dokumentu (podřízených oken MDI) rozhraní IDE.  
  
 DTE  
 `DTE` Objektu (rozšíření nástrojů vývoj) je nejvyšší přístupový bod v sadě Visual Studio automatizace modelu, který umožňuje prostřednictvím kódu programu automatizovat a rozšířit rozhraní IDE.  
  
 Dynamická okna nápovědy  
 Okno nástroje, které implementují rozhraní IDE a zobrazí se seznam vyhledávání – klíčové slovo nebo témata nápovědy F1.  
  
 editor  
 Kód (třída, CLSID), který implementuje `DocView`. Také implementuje `DocData` Pokud se podporuje oddělení dat nebo zobrazení.  
  
 přípona  
 Funkce, která upraví, umožní vlastní nastavení, nebo ho přidá k rozhraní IDE. Můžete vytvořit pomocí modelu automatizace nebo VSPackages rozšíření.  
  
 externí editoru  
 Editor, které nejsou specifické pro prostředí IDE, jako je například Microsoft Word. Ho byl zaregistrován prostřednictvím vlastní mechanismy a použít mimo prostředí IDE. Pokud lze jej vkládat tohoto editoru, zobrazí se v rámci okna v prostředí IDE. Pokud není možné vložit, vytvoří se samostatném okně nejvyšší úrovně.  
  
 hierarchie  
 Strom uzlů, každý uzel přidružené sadu vlastností.  
  
 nezávislé komponenty nejvyšší úrovně  
 Komponenta, která používá nemodálním okně nejvyšší úrovně a mohou pracovat efektivně jako samostatnou aplikaci okna, ale je implementovaný jako objekt v procesu. Proto musí komponentu nezávislé nejvyšší úrovně koordinovat podobu činnosti a zpráva smyčky službám pomocí rozhraní IDE. Objekty v procesu nemají své vlastní zpráva smyčky.  
  
 Poskytovatel informací o  
 Poskytovatel informací o je modul, který můžete vyhledat klíčová slova a vrátí seznam témat, ve formě `IVsUserContextItem` objekty. Zajistit F1 a vyhledávání položek – klíčové slovo pro poskytovatel informací o registraci vašeho zkompilovaný soubor nápovědy (. HxS) pomocí systému. Témata nápovědy v těchto souborech používané k zajištění seznam témat zobrazí v okně Nápověda pro dynamické a ukazuje, zda stisknutí klávesy F1.  
  
 součást na místě  
 VSPackage objekt, který implementuje `IOleInPlaceComponent` rozhraní pro správu okno, které je vizuálně obsažené v okně dokumentu vlastníkem rozhraní IDE. Na místě součásti neúčastnit standardní OLE-slučování nabídek; Místo toho se jejich prvky uživatelského rozhraní integrovat do rozhraní IDE.  
  
 Existují dva typy součástí místní: standardní kabelové místní součásti a součásti ovládacích prvků.  
  
 Mít komponenty, standardní kabelové místní nabídky, panely nástrojů a příkazy, které jsou úzce integrována do uživatelského rozhraní IDE, jako zobrazování, pokud byly vytvořené přímo v prostředí IDE.  
  
 Ovládací prvky součást nemají žádné vlastní elementy uživatelského rozhraní, integrované do rozhraní IDE; Místo toho používají nabídek, příkazy a panely nástrojů rozhraní IDE. Například příkaz Bold může bold vybrané aplikace word v rámci prvku RTF vložené ve formuláři. Však součástí ovládacích prvků může požádat o zobrazit dynamicky nainstalovaná součást konkrétní prvky uživatelského rozhraní.  
  
 Služba jazyka  
 Sada objektů, která umožňuje vývojářům VSPackage implementovat funkce editory kódu jazyka počítače, například textu a barevné označování označení.  
  
 Různé soubory projektu  
 Projekt používá k úklidové otevřených souborů, které nejsou ve všech projektech. Seznam položek v tomto projektu není trvalý.  
  
 projekt  
 Projekty jsou tvořeny hierarchie objektů, nebo které implementují objekty COM `IVsHierarchy` rozhraní.  
  
 Návrhář projektu konkrétní nebo editoru  
 Návrhář, která se nedá použít nezávisle na typu projektu. Všechny konkrétní projekt návrháři musíte zadat své informace objekt Factory editoru v registru. Prostředí IDE pak můžete vytvořit instanci Návrháře při každém otevření určitý typ souboru v určitém projektu.  
  
 okno typu projektu  
 Okno, které neustále sleduje hierarchie aktuálně aktivní projekt a položek z kontextu globální výběr. Typ projektu windows používat `SVsTrackSelectionEx` rozhraní IDE změny výstrah a zobrazit zpětné vazby uživatele. Průzkumník řešení je příkladem intervalu pro správu a typu projektu.  
  
 Vlastnosti – okno  
 Dříve prohlížeč vlastností.  
  
 referenční dokumentace založené na projekty  
 Projekt, který nevyžadují soubory pro projekt, který má být ve stejném adresáři. Místo toho jsou odkazy na soubory z dalších adresářů nesouvisejícími uložené a udržované pomocí samotného projektu.  
  
 spuštěné tabulce dokumentu  
 Vnitřní strukturu, podle kterého IDE udržuje seznam všechny aktuálně otevřené dokumenty. Tento seznam obsahuje všechny otevřené dokumenty v paměti bez ohledu na to, jestli dokumenty jsou aktuálně Upravovaný. Dokument je libovolnou položku, který je uložen, včetně uložené procedury otevřen v editoru, soubory v projektu nebo hlavní soubor projektu (například soubor *.vcproj).  
  
 Výběr kontextu  
 Data, která je součástí podrobností každého okna v prostředí IDE a slouží ke sledování aktivní výběr. Výběr kontextu se skládá z:  
  
-   Ukazatel `IVsHierarchy` rozhraní hierarchii projektu  
  
-   Identifikátor položky položky projektu.  
  
-   Ukazatel `ISelectionContainer` rozhraní poskytování přístupu k vlastnosti pro aktivní objekty.  
  
-   Pole hodnot elementu.  
  
 service  
 Kontrakt pro sadu rozhraní modelu COM, které se nacházejí v jednom objektu COM. Při vytváření služby, která je identifikovaná identifikátorem GUID, můžete definovat sadu rozhraní modelu COM, které provádí službu. Objekty modelu COM pomocí služby pro vzájemnou komunikaci.  
  
 Řešení  
 Skupina související projekty, se kterými uživatel pracuje.  
  
 Standardní návrháře  
 Návrhář, který lze použít nezávisle na typu projektu. Všechny standardní návrháři musíte zadat své informace objekt Factory editoru v registru. Prostředí IDE pak můžete vytvořit instanci Návrháře při každém otevření souboru s konkrétní příponou. Do souboru musí zachovat data.  
  
 standardního editoru  
 Editor, který lze použít nezávislou libovolného typu konkrétní projekt. Takové editory mít EditorFactories zaregistrován v registru. To umožňuje IDE pro vyhledání a vyvolání editoru.  
  
 Standardní editor operačního systému  
 Vložení, který není sady Visual Studio konkrétní. Je zaregistrována pomocí známých Win32 klíče (například Průzkumník Win32 umí vyvolání). Pokud takové editoru lze jej vkládat, editor se pořád zobrazí na jeho místo v prostředí IDE. Pro takové editory, jinak se vytvoří samostatném okně nejvyšší úrovně.  
  
 dílčí kontext kontejner objektů a dat  
 `IVsUserContext` Objekt propojené s kontejner kontextu. Tento objekt obsahuje klíčová slova pro vyhledávání, klíčová slova F1 a atributy pro výběr v rámci komponentu IDE. Dílčí kontext příklady příkazu v okně nástroje nebo klíčové slovo v editoru.  
  
 Seznam úkolů  
 Okno nástroje, které implementují rozhraní IDE a zobrazí seznam aktivních úloh.  
  
 Textová vyrovnávací paměť  
 Běžný název pro objekt `VSTextBuffer`.  
  
 Zobrazení textu  
 Běžný název pro objekt `VSTextView`.  
  
 součást nejvyšší úrovně nástroje  
 Komponenta, která funguje jako nemodální automaticky otevíraném okně, úzce spolupráci se uživatelské rozhraní IDE. Jako nezávislé komponenty nejvyšší úrovně musí komponenty nejvyšší úrovně nástroje také koordinovat podobu činnosti a zpráva smyčky službám pomocí rozhraní IDE.  
  
 součást nejvyšší úrovně  
 VSPackage objekt, který spravuje nemodálním okně nejvyšší úrovně místo klientské oblasti okna IDE. Implementace nejvyšší úrovně součásti `IOleComponent` rozhraní využívat výhod zpráva smyčky služby, jako je například přístup do doby nečinnosti.  
  
 Aktivní uživatelského rozhraní  
 VSPackage objekt, který je viditelná a má právě fokus.  
  
 Hierarchie uživatelského rozhraní  
 Objekt modelu COM, který implementuje `IVsUIHierarchy` rozhraní umožňuje zobrazení hierarchie. Implementuje okno hierarchie uživatelského rozhraní `ISelectionContainer` rozhraní aktualizace okno vlastností; ostatní typu projektu windows můžete tuto implementaci použít v případě potřeby.  
  
 VSCT  
 Tabulka příkaz sady Visual Studio. .Vsct soubor obsahuje informace o umístění a chování nabídek, panely nástrojů a příkazy ve formátu XML.  
  
 VSPackage  
 Instalovat část softwaru, který rozšiřuje Visual Studio IDE přispěje jeden nebo více následujících akcí: uživatelské rozhraní, služby, typy projektů nebo editor nebo designer. VSPackage se skládá z objektu COM, který implementuje `IVsPackage` rozhraní a jeden nebo více dalších COM objekty, které implementace jiných rozhraní pro podporu výběr a další funkce. Kromě toho VSPackage má požadavky na konkrétní registrace.