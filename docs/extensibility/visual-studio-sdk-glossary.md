---
title: Glosář sady Visual Studio SDK | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- glossary [Visual Studio SDK]
ms.assetid: b64d432b-c39b-4904-ad18-3c3218b6e3aa
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6157b4bc3537a4f88feb91d512241451b8324ba7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682801"
---
# <a name="visual-studio-sdk-glossary"></a>Visual Studio SDK Glosář
Tento glosář obsahuje definice podmínek, které se používají v [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] dokumentaci.

## <a name="terms"></a>Podmínky
 doplněk aplikace nástroj, ovladač nebo jiný software přidané do primární aplikace. V sadě Visual Studio integrované vývojové prostředí (IDE) je doplněk aplikace založené na službě Automation, která rozšiřuje možnosti integrovaného vývojového prostředí.

 model automatizace modelu automatizace, známá v předchozích verzích sady Visual Studio jako model rozšiřitelnosti, je programovací rozhraní, které poskytuje přístup k základní rutiny tuto jednotku integrovaného vývojového prostředí. Doplňky, průvodci a makra použít objekty v modelu automatizace pro ovládací prvek nebo rozšiřovat funkce integrovaného vývojového prostředí.

 příkaz kontextu uživatelského rozhraní přidružení identifikátoru GUID, zda se příkaz uživatelského rozhraní nebo element jako je panel nástrojů. Příkaz kontextu uživatelského rozhraní je na rozdíl od kontext výběru není připojen k časového období.

 Příkaz kontextu uživatelského rozhraní umožňuje:

- Identifikátor GUID přiřadíte panel nástrojů, který se zobrazí, když se aktivuje konkrétní okno.

- Přiřadíte identifikátor GUID na dostupnost příkazu bez nutnosti načtení nebo spuštění VSPackage.

- Přiřaďte GUID ovlivnit aktivní vazbu klíče.

- Přiřadíte identifikátor GUID zapnout záznam makra.

- Přiřadíte identifikátor GUID k aktivaci režimu ladění nebo přepínat mezi návrhem a režimu běhu v editoru.

  komponenta software, který můžete vytvořit součást funkce aplikace bez této aplikace má již existující informace o implementaci pro software. Komunikace mezi komponenty a aplikace je výhradně prostřednictvím rozhraní OLE style.

  služby Správce komponent, `SOleComponentManager`, který poskytuje služby koordinace bez uživatelského rozhraní pro součásti nejvyšší úrovně. `SOleComponentManager` Služba implementuje `IOleComponentManager` rozhraní.

  součásti uživatelského rozhraní Správce služby, `SOleComponentUIManager`, který poskytuje uživatelské rozhraní koordinace služby. `SOleComponentUIManager` Služba implementuje `IOleComponentUIManager` a `IOleInPlaceComponentUIManager` rozhraní.

  kontejner objektů a dat kontextu `IVsUserContext` objekt (objekt modelu COM) připojené k jako součást prostředí. Tento objekt obsahuje klíčová slova pro vyhledávání, **F1** klíčová slova a atributy, které se vztahují na komponentu. Kontext kontejnery objektů a dat dále odkazovat na žádné kontext kontejnery objektů a dat, které jsou propojeny k nim.

  kontext zprostředkovatele A komponenty v integrovaném vývojovém prostředí, který se má kontext kontejneru s ním spojená. Tyto součásti zahrnují panel nástrojů, editor nebo projekt hierarchie.

  Návrhář programovací rozhraní, který umožňuje uživatelům pracovat s prvky uživatelského rozhraní (formuláře, tlačítka a další ovládací prvky).

  Objekt DocData A COM zapouzdření podkladová data dokumentu ve světě, ve kterých je oddělení dokument/zobrazení (například v případě text editor, by to byl textové vyrovnávací paměti základního všechna zobrazení textového editoru). Pokud EditorFactory neposkytuje tento objekt, rozhraní IDE vyrábí jeden svým jménem. Odpovědnosti tento objekt je ke správě trvalost dat a sdílení sémantiky pro více zobrazení přes to stejné `DocData`. Pokud `DocData` podporuje `IOleCommandTarget` rozhraní, je zahrnutý v směrování příkazů UIShell.

  K hostování uživatelského rozhraní v rámci poskytované hostitelem používá technologii DocObject. Přesněji řečeno, tento výraz odkazuje na všechny vložení, který podporuje `IOleDocument` a souvisejících rozhraní. Tato technologie má mnoho možných aplikací, jako jsou podrobnosti implementace modelu COM dokumentů, oken nástrojů v jazyce Visual Basic 5.0, návrháři ActiveX v jazyce Visual Basic 6.0 a tak dále.

  dokument slouží k obecně naleznete v dokumentu jako celek – jak `DocData` a `DocView`. Například DocumentFrame obsahuje `DocView`, ale také uchovává odkaz na `DocData` zpracování trvalosti.

  DocView The DocObject/vložení/WindowPane pomocí kterého uživatel pracuje na Zobrazit a pracovat s podkladovým `DocData`. Není uživatelé využívají výhod Document/View oddělení, který je součástí `DocObject` návrh rozhraní. Uživatelé používat celý DocObject tak, aby fungoval jako zobrazení namísto použití více abstraktní (a méně formalizovanou) pojem podkladová data označované jako `DocData`. `DocView` objekty jsou vždy integrované s objekty rámce dokumentu (podřízených oken MDI) rozhraní IDE.

  DTE `DTE` (rozšíření nástrojů pro vývoj) objektu je úplně nahoře přístupový bod v modelu automatizace sady Visual Studio, který umožňuje programově automatizovat a rozšířit rozhraní IDE.

  Dynamická nápověda panelu nástrojů okno, které je implementované integrovaným vývojovým prostředím a zobrazí seznam vyhledávání – klíčové slovo nebo **F1** témata nápovědy.

  Editor kódu (třída, identifikátor CLSID), který implementuje `DocView`. Implementuje navíc `DocData` Pokud podporuje zobrazení a data oddělení.

  rozšíření A funkce, která upravuje, upraví nebo přidá do rozhraní IDE. Vytváření rozšíření pomocí modelu automatizace nebo rozšíření VSPackages.

  externí editor editor, který se neomezuje jen na rozhraní IDE, jako je například Microsoft Word. Byl zaregistrován prostřednictvím vlastní mechanismy a je možné mimo rozhraní IDE. Pokud tento editor může být vložen, zobrazí se v rámci okna v rozhraní IDE. Pokud nemůže být vložený, se vytvoří samostatné okno nejvyšší úrovně.

  hierarchie stromu uzlů, každý uzel přidružený sadu vlastností.

  součást nezávislé nejvyšší úrovně A součást, která používá nemodálního okna nejvyšší úrovně a může efektivně pracovat jako samostatné aplikace rozhraní okna, ale je implementována jako objekt v rámci procesu. Proto musí komponentu nezávislé nejvyšší úrovně koordinovat modalitě a služba smyčky zpráv pomocí integrovaného vývojového prostředí. Objekty v rámci procesu nemají své vlastní smyčku zpráv.

  Poskytovatel informací o zprostředkovateli informace je modul, který můžete vyhledat klíčová slova a vrátí seznam témat, formu `IVsUserContextItem` objekty. K poskytování **F1** – klíčové slovo vyhledávání položek pro zprostředkovatele informace, zaregistrujte zkompilovaný soubor nápovědy (*. HxS*) se systémem. Témata nápovědy v těchto souborech zadejte seznam témat týkajících se zobrazí v okně Dynamická nápověda a zobrazí, zda uživatel stiskne **F1**.

  místní objekt balíčku VSPackage A komponenty, který implementuje `IOleInPlaceComponent` rozhraní pro správu okno, které je vizuálně obsažené v okně dokumentu vlastněné integrovaného vývojového prostředí. Místní součásti není součástí standardní OLE-slučování nabídek; Místo toho jsou jejich prvky uživatelského rozhraní integrace do integrovaného vývojového prostředí.

  Existují dva typy místní komponenty: standardní kabelové místní komponenty a ovládací prvky komponenty.

  Standardní kabelové místní součásti mají nabídky, panely nástrojů a příkazů, které jsou úzce integrovány do uživatelského rozhraní IDE, jako povolí, pokud byly vytvořeny přímo do integrovaného vývojového prostředí.

  Součásti ovládacích prvků nemáte žádný vlastní prvky uživatelského rozhraní, integrovaný do rozhraní IDE; Místo toho používají nabídek rozhraní IDE, příkazy a panelů nástrojů. Může například použít příkaz tučné mají být zobrazena tučně vybrané aplikace word v rámci ovládacího prvku RTF vložené ve formuláři. Součásti ovládacích prvků však může vyžádat, aby dynamicky nainstalované komponenty konkrétní prvky uživatelského rozhraní zobrazily.

  jazykové služby A sadu objektů, které umožňuje vývojářům VSPackage k implementaci funkcí jazyka počítače editory kódu, jako je text označení a barevné označování.

  Různé soubory projektu projektu použitému k uložení otevřených souborů, které nejsou v každém projektu. Seznam položek v tomto projektu není trvalý.

  Projekt projekty jsou tvořené hierarchie objekty nebo objekty COM, které implementují `IVsHierarchy` rozhraní.

  specifické pro projekt Návrhář nebo editor A Návrhář, který nelze použít bez ohledu na jejich typ projektu. Všechny návrháře specifické pro projekt, musíte zadat informace o jejich objekt pro vytváření editoru v registru. Integrované vývojové prostředí pak můžete vytvořit instanci Návrháře pokaždé, když určitý typ souboru se otevře v konkrétním projektu.

  okna okno A typu projektu, který neustále sleduje hierarchie aktuálně aktivní projektu a položky z kontextu globálního výběru. Pomocí typu projektu windows `SVsTrackSelectionEx` IDE změny výstrah a zobrazit zpětné vazby pro uživatele. Průzkumník řešení je příkladem okno typ projektu.

  Okno Vlastnosti dříve prohlížeč vlastností.

  odkaz na projekty založené na projekt, který nevyžaduje, aby soubory projektu ve stejném adresáři. Místo toho odkazy na soubory z jiných adresářů nesouvisejících ukládání a udržuje samotného projektu.

  spuštění tabulky interní strukturu dokumentu pomocí kterého rozhraní IDE udržuje seznam všech aktuálně otevřených dokumentů. Seznam obsahuje všechny otevřené dokumenty v paměti bez ohledu na to, zda dokumenty jsou právě upravována. Dokument je všechny položky, které se uloží, včetně uložených procedur otevřít v editoru, soubory v projektu nebo souboru hlavního projektu (například soubor *.vcproj).

  kontext výběru dat, která je součástí podrobností každého okna v rozhraní IDE a slouží ke sledování aktivních výběrů. Výběr kontext se skládá z:

- Ukazatel `IVsHierarchy` rozhraní hierarchie projektu

- Identifikátor položky, položky projektu.

- Ukazatel `ISelectionContainer` rozhraní poskytuje přístup k vlastnostem pro aktivní objekty.

- Pole hodnoty prvku.

  servisní smlouva pro sadu rozhraní modelu COM, který se nachází v jednom objektu COM. Při vytváření služby, který je určený identifikátorem GUID, můžete definovat sadu rozhraní modelu COM, které provádí služba. Objekty modelu COM pomocí služby pro komunikaci mezi sebou.

  řešení seskupení souvisejících projektů, se kterými uživatel pracuje.

  Standardní návrháře návrháře, který se dají používat nezávisle na typu projektu. Všechny standardní návrháře musíte zadat informace o jejich objekt pro vytváření editoru v registru. Integrované vývojové prostředí pak můžete vytvořit instanci Návrháře při každém otevření souboru s konkrétní příponou. Data musíte zachovat do souboru.

  Standardní editor Editor, který je možné nezávisle na žádné konkrétní typ projektu. Takové editory obsahují EditorFactories zaregistrovaný v registru. To umožňuje rozhraní IDE k vyhledání a vyvolání editoru.

  Standardní editor operačního systému vložení, který není konkrétní Visual Studio. Je zaregistrované pomocí dobře známých klíčů Win32 (například Průzkumník systému Win32 ví, jak vyvolat). Pokud takové editor může být vložen, editor stále hlásí na příslušné místo v integrovaném vývojovém prostředí. V opačném případě se vytvoří samostatné okno nejvyšší úrovně pro takové editory.

  kontext kontejner objektů a dat `IVsUserContext` objekt propojený s kontejner kontextu. Objekt obsahuje klíčová slova pro vyhledávání, **F1** klíčová slova a atributy pro výběr v rámci jako součást integrované vývojové prostředí. Kontext příklady příkazu v panelu nástrojů nebo klíčové slovo v editoru.

  Okno nástroje seznamu úkolů, které je implementované integrovaným vývojovým prostředím a zobrazí seznam aktivních úloh.

  Běžný název textové vyrovnávací paměti pro objekt `VSTextBuffer`.

  Text zobrazení běžný název pro objekt `VSTextView`.

  Nástroj pro součást nejvyšší úrovně A součást, která funguje jako nemodálního automaticky otevíraném okně, úzce koordinaci s uživatelským rozhraním rozhraní IDE. Stejně jako nezávislé komponenty nejvyšší úrovně musí komponenty nejvyšší úrovně nástroje také koordinovat modalitě a služba smyčky zpráv pomocí integrovaného vývojového prostředí.

  součást nejvyšší úrovně A VSPackage objektu, který spravuje nemodální okno nejvyšší úrovně namísto klientské oblasti okna IDE. Nejvyšší úrovně komponenty implementovaly `IOleComponent` rozhraní, abyste mohli využívat služba smyčky zpráv, jako je například přístup do nečinnosti.

  Objekt uživatelského rozhraní aktivní A VSPackage, která je viditelná a má právě fokus.

  Objekt modelu COM A hierarchie uživatelského rozhraní, která implementuje `IVsUIHierarchy` rozhraní umožňuje zobrazení hierarchie. V okně hierarchie uživatelského rozhraní implementuje `ISelectionContainer` rozhraní aktualizovat v okně Vlastnosti; ostatní okna typ projektu můžete tuto implementaci použít v případě potřeby.

  VSCT tabulky příkazů sady Visual Studio. Souboru .vsct obsahuje informace o umístění a chování, nabídek, panelů nástrojů a příkazů ve formátu XML.

  VSPackage Instalovatelné softwarového produktu, který přispívá jeden nebo více z následujících položek je rozšířením rozhraní IDE sady Visual Studio: uživatelské rozhraní, služby, typy projektů nebo editoru nebo návrháře. VSPackage se skládá z objektu modelu COM, který implementuje `IVsPackage` rozhraní a jeden nebo více jiných objektů COM, které implementují jiných rozhraní pro podporu výběru a další funkce. Kromě toho VSPackage má požadavky na konkrétní registraci.