---
title: Nabídek a příkazů pro sadu Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 0a1ed675-2bd1-4603-ba3a-f40dfb5cfb69
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 16f67faf7ffe3a3fd119b7ddf002ab463822a830
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="menus-and-commands-for-visual-studio"></a>Nabídek a příkazů pro sadu Visual Studio
## <a name="command-usage"></a>Použití příkazu  
  
### <a name="overview"></a>Přehled  
 Na rozdíl od aplikace Microsoft Office, což je sada nástrojů, který zahrnuje mnoho samostatných produktů, Visual Studio obsahuje mnoho produktů, že každý přispívat jejich sady příkazů k globální Visual Studio IDE. Prostředí IDE spravuje složitosti tisíce příkazy pomocí filtrování funkce, která je k dispozici pro uživatele na základě kontextu.  
  
 Když se změní kontextu uživatele – například přepnutí na kód okno pro úpravy v okně návrhu – funkce, které nejsou nový kontext zmizí. Ve stejnou dobu, nové funkce povrchy společně s související dynamické informace, například vlastnosti a sady nástrojů možnosti. Uživatel nesmí Všimněte si, odkládací sady k dispozici příkaz. Pokud je uživatel odváděna nebo příkazy, které jsou uvedeny nebo nezobrazený zaměňovat, návrh uživatelského rozhraní musí úpravu. Aktuální kontext uživatele je vždy uvedené v jedné nebo více způsoby, například v záhlaví okna IDE, okno Vlastnosti nebo dialogové okno stránky vlastností.  
  
 Panely příkazů umožňují flexibilitu v uživatelském rozhraní. Příkaz pouze struktury vyplývajících pro Visual Studio prostředí jsou v hlavní nabídce a hlavní příkazový řádek, který může být přizpůsobit i i skryté. Další příkaz řádky zobrazí a zmizí závislosti na stavu aplikace. Panely nástrojů dokument může také obsahovat embedded panely nástrojů v rámci jejich okraje okna.  
  
#### <a name="basic-guidelines"></a>Základní pokyny  
  
##### <a name="use-existing-shared-commands-command-groups-and-menus-whenever-possible"></a>Použijte existující sdílené příkazy, příkaz skupiny a nabídky, kdykoli je to možné.  
 Vzhledem k tomu, že příkazy se obvykle zobrazují na základě v kontextu, použijte existující sdílené nabídky a skupin, příkaz zajistí, příkazovou strukturu zůstává relativně stálý mezi změny v kontextu. Opětovné použití sdílených příkazů a umístění nové příkazy blízko související sdílené příkazy také snižuje složitost IDE a vytvoří přívětivější prostředí. Pokud nový příkaz musí být definován, zkuste jej umístit do existující skupiny sdílené příkaz. Pokud do nové skupiny musí být definován, umístěte ji do existující sdílené nabídky blízko skupinu souvisejícím příkazem před vytvořením nové nabídky nejvyšší úrovně.  
  
##### <a name="do-not-create-icons-for-every-command"></a>Nevytvářejte ikony pro každý příkaz.  
 Vezměte v úvahu pečlivě před vytvořením ikona příkazu. Ikony by měl být vytvořen pouze pro příkazy který:  
  
-   zobrazí na panelu nástrojů výchozí.  
  
-   mohou uživatelé přidat na panel nástrojů prostřednictvím **přizpůsobit...**  dialogové okno.  
  
-   máte ikony přidružené o stejnou akci v jiného produktu společnosti Microsoft.  
  
##### <a name="limit-the-addition-of-keyboard-shortcuts"></a>Limit přidání klávesové zkratky  
 Velká většina uživatelů použít jen nepatrnou část klávesových zkratek všechny dostupné. Pokud máte pochybnosti, nemusíte vazbu vaší funkce k klávesové zkratky. Pracují s vaší uživatelské prostředí team před přidáním nové zkratky.  
  
##### <a name="give-commands-a-default-menu-placement"></a>Dejte příkazy nabídky Výchozí umístění.  
 Uvědomte si, že příkazech budou přizpůsobené jinými uživateli a návrhu je odpovídajícím způsobem. Neexistuje žádná taková věc jako skrytá příkaz. Všechny příkazy sady Visual Studio se zobrazí v **nástroje > Přizpůsobit** v dialogovém okně příkazového řádku automatického dokončování **nástroje > Možnosti > klávesnice** dialogové okno a prostředí nástroje pro vývoj (DTE). Ujistěte se, že vaše příkazy poskytnout název a popis v souboru .ctc, aby uživatelé mohli snadno najít.  
  
##### <a name="do-not-duplicate-shared-commands-on-an-embedded-toolbar"></a>Není duplicitní sdílených příkazů na vložené panelu nástrojů.  
 Je užitečné k umístění příkazy v těsné blízkosti oblasti uživatele fokus. Jedním ze způsobů k tomu je vytvoření embedded panelu nástrojů v horní části okna nástroje nebo dokumentu editoru. Příkazy, které jsou umístěny na panelu nástrojů by měl být specifické pro oblast obsahu v rámci okna. Není duplicitní sdílených příkazů na panely nástrojů. Například umístění nikdy "Uložit" ikony v rámci embedded panelu nástrojů.  
  
### <a name="content-and-command-visibility"></a>Přehled obsahu a příkaz  
 Příkazy existovat v následující obory: **prostředí**, **hierarchie**, a **dokumentu**. Chcete-li mít jistotu při umísťování příkaz vědět každý obor.  
  
 Příkazy v **prostředí** obor vytvořit primární kontext a jsou sdílené mezi více kontexty. Změnit jejich viditelnost nebo uspořádání dokumenty a nástroje systému windows. Mezi příkazy v prostředí oboru jsou **nový projekt**, **připojit k serveru**, **připojit proces**, **Vyjmout**,  **Kopírování**, **vložení**, **najít**, **možnosti**, **přizpůsobit**, **nové okno**, a **zobrazit nápovědu**.  
  
 Příkazy v **hierarchie** oboru spravovat hierarchií v sadě Visual Studio, včetně **projektu**, **Team**, a **Data**. Se vztahují k projektu dílčí kontext – například **ladění**, **sestavení**, **Test**, **architektura**, nebo **analýza** . Mezi příkazy v hierarchii jsou oboru **přidat novou položku**, **nový dotaz**, **nastavení projektu**, **přidat nový zdroj dat**, **Spustí Průvodce výkonu**, a **nový Diagram**.  
  
 Příkazy v **dokumentu** act oboru na obsah dokumentu, například kód, návrh nebo dotazu na pracovní položku (WIQ). Jsou také fungovat v zobrazení okno nástroje nebo jinak jsou specifické pro dané okno nástroje. Příkazy oboru dokumentů slouží také na soubor objekty, které jsou sami konkrétní hierarchie, například **odebrat z projektu**. Mezi příkazy v dokumentu jsou oboru **Refaktorovat > přejmenujte**, **vytvořením kopie pracovní položky**, **Rozbalit vše**, **sbalit všechny**, a **Vytvoření úlohy uživatele**.  
  
### <a name="command-placement-decisions"></a>Příkaz umístění rozhodnutí  
 Jakmile jste se rozhodli vytvoření příkazu, budete muset určit jeho odpovídající umístění a zda k vytvoření klávesové zkratky. Postupujte podle tato rozhodnutí cesta k navázání kam umístit příkaz:  
  
 ![Příkaz umístění rozhodovací graf](../../extensibility/ux-guidelines/media/0501-a_commandplacement.png "0501 a_CommandPlacement")  
  
 **Cesta rozhodnutí pro příkaz umístění v sadě Visual Studio**  
  
### <a name="command-placement-in-menus"></a>Příkaz umístění v nabídkách  
  
#### <a name="main-menu-bar"></a>Přejděte z hlavní nabídky panelu  
 Hlavním panelu nabídek by měl být standardní umístění pro příkazy všechny balíčky kontextové nabídky, které podílet se na uživatelské rozhraní. Hlavním panelu nabídek se liší od jiných příkaz struktury v tomto prostředí se používá k řízení, které příkazy jsou viditelné. Všechny ostatní panely příkazů jednoduše zakázat příkazy, které jsou mimo kontext, zda jsou umístěny v nabídce nebo na panelu nástrojů.  
  
 Prostředí definuje sadu příkazů integrovaný do panelu přejděte z hlavní nabídky, které jsou společné pro celý IDE a víc domén úloh. Tyto příkazy jsou vždy viditelné bez ohledu na to z nich jsou načteny VSPackages do prostředí. I když VSPackages můžete rozšířit tuto sadu příkazů, příkaz nastavit z každý produkt a umístění jejich příkazy odpovídá každý týmu.  
  
 Struktura v hlavní nabídce sady Visual Studio můžete rozdělit do následujících kategorií nabídky:  
  
##### <a name="core-menus"></a>Základní nabídky  
  
-   Soubor  
  
-   Upravit  
  
-   Zobrazit  
  
-   Nástroje  
  
-   Okno  
  
-   Nápověda  
  
##### <a name="project-specific-menus"></a>Nabídky specifické pro projekt  
  
-   Projekt  
  
-   Sestavení  
  
-   Ladit  
  
##### <a name="context-specific-menus"></a>Kontextové nabídky  
  
-   Tým  
  
-   Data  
  
-   Test  
  
-   Architektura  
  
-   Analyzovat  
  
##### <a name="document-specific-menus"></a>Specifické pro dokument nabídky  
  
-   Formát  
  
-   Tabulka  
  
##### <a name="when-designing-main-menus-adhere-to-these-rules"></a>Při navrhování hlavní nabídky, dodržovat tato pravidla:  
  
-   Není delší než 25 položky nejvyšší úrovně v daném kontextu  
  
-   Nabídky by měly překročit nikdy 600 pixelů na výšku.  
  
-   Vyhodnocení hlavní nabídky v několika kontextech, například v Ultimate SKU a obecné profil.  
  
-   Vysouvací nabídky jsou přijatelné.  
  
-   Vysouvací nabídky by mělo obsahovat aspoň tři položky a více než 7.  
  
-   Vysouvací nabídky by měli přejít pouze jedna úroveň hloubky – některé položky nabídky v sadě Visual Studio mít kaskádových dílčích, ale tento vzor není podporováno.  
  
-   Použití více než šest oddělovačů. Seskupení by měl splňovat na následujícím obrázku:  
  
     ![Pokyny pro seskupení hlavní nabídky](../../extensibility/ux-guidelines/media/0501-b_mainmenus.png "0501 b_MainMenus")  
  
-   Když je není potřeba mít jednotlivá seskupení na obrázku, přidání další seskupení je s omezeným přístupem.  
  
-   Jednotlivá seskupení by měl mít ze dvou do sedmi položky nabídky.  
  
#### <a name="main-menu-ordering"></a>Přejděte z hlavní nabídky řazení  
 Před přidáním nové položky nejvyšší úrovně, zvažte umístění příkaz v existující nabídky nejvyšší úrovně. Při přidávání nové nabídky nejvyšší úrovně, je nutné umístit na správné místo. Rozhodnete, zda je v nabídce specifické pro projekt, kontext nebo dokumentu. Ponechte název nabídek nejvyšší úrovně stručným a použít pouze jeden aplikace word.  
  
 Nabídky jádra by měl zarážku zbytek příkazy. Soubor, úpravy a zobrazení by měla být vždy na levé straně a nástroje, okno, a nápovědu by měla být vždy vpravo.  
  
#### <a name="context-menus"></a>Kontextové nabídky  
 Umístění příliš mnoho funkcionalitu v rámci kontextové nabídky výsledkem rozhraní je obtížné Další. Všechny hlavní funkce musí být k dispozici prostřednictvím panelu přejděte z hlavní nabídky. Umístění příkazů by měl být souhlasí s existující příkazy, aby se zabránilo duplicitní příkazy. Prostředí pro kontextové nabídky, definuje skupiny standardní nabídek, které by měly být zahrnuty v závislosti na tom, zda je kontextová nabídka pro řešení, uzel projektu nebo položka projektu.  
  
 Při navrhování kontextové nabídky, dodržovat stejná pravidla jako hlavní nabídky a navíc:  
  
-   Není delší než 25 položek nabídek nejvyšší úrovně.  
  
-   Vysouvací nabídky jsou přijatelné, ale musí není delší než jednu úroveň – nikdy nepoužívejte kaskádových kontextové nabídky.  
  
-   Použití více než šest oddělovačů.  
  
### <a name="command-placement-in-toolbars"></a>Příkaz umístění v panelech nástrojů  
  
#### <a name="general-toolbars"></a>Obecné panely nástrojů  
 Při návrhu a uspořádání panely nástrojů, postupujte podle těchto standardů:  
  
-   Nepoužívejte více než jedna operace na tlačítko. Jedno tlačítko = jednu akci.  
  
-   Použijte text spolu s ikonu pouze v případě, že musí být posílit s popiskem.  
  
-   Pole se seznamem použijte výhradně pro vlastnosti, které bude možné přepnout vícekrát jednu relaci. Jinak zpřístupnit vlastnost jinde.  
  
-   Šířka pole se seznamem rovnat šířku nejdelší položky v rámci pole + 30 %. Například pokud nejdelší položka je 200 pixelů, pak pole se seznamem mělo 260 pixelů.  
  
-   Omezte použití oddělovače. Použití oddělovače vedle rozevírací je proti vzor, protože obrazec rozevíracího seznamu sám funguje jako vizuálního oddělovače.  
  
-   Ikona skupiny by měl obsahovat od 3 do šesti ikony.  
  
-   Pokud kvalifikátory mít za následek více užitečné příkazy, použijte tlačítko rozdělení, které ukládá poslední nastavení:  
  
     ![Rozdělení tlačítka v sadě Visual Studio](../../extensibility/ux-guidelines/media/0501-c_splitbuttons.png "0501 c_SplitButtons")  
  
     **Příklad tlačítka rozdělení. Šest příkazy na levé straně, můžete místo toho začlenit do jediného tlačítka.**  
  
#### <a name="product-specific-toolbars"></a>Panely nástrojů určitého produktu  
 Každý produkt zajistí, že obsahuje často používané výchozí nástrojů a důležité příkazy a každý produkt výchozí nástrojů by se měla objevit při prvním spuštění sady Visual Studio po instalaci produktu.  
  
 Produkty by je měli využít také sdílené příkaz skupiny a nabídek poskytuje rozhraní IDE. Každou skupinu sdílené příkaz je umístěn ve sdílené nabídky určená k uspořádání související příkazy smysluplný způsobem pro uživatele. Je důležité kvůli snížení složitosti využít tuto strukturu sdílené příkaz.  
  
#### <a name="global-toolbars"></a>Globální panely nástrojů  
 Globální panely nástrojů se vyžadují pro jeden řádek vpravo mimo pole. Při vytváření nových panelů nástrojů globální, postupujte podle pokynů pro tento typ panelu nástrojů.  
  
 **Panel nástrojů obecné pokyny:**  
  
-   Každý nástrojů má 24 pixelů v běžné ovládací prvky (úchytu, přetečení).  
  
-   Tlačítko panelu nástrojů, je 22 pixelů široké, včetně odsazení. Provedení ikonu tlačítko rozdělení přidá další 11 pixelů šířky.  
  
-   Je povolen duplicitních příkazy napříč panely nástrojů.  
  
 **Panely nástrojů specifické pro dokument** zobrazí, když je aktivní určitý typ souboru a při jiný typ souboru stane aktivní zmizí.  
  
-   Panely nástrojů specifické pro dokument nemůže obsahovat více než 12 tlačítka.  
  
-   Celková šířka panelu nástrojů nesmí být delší než 300 pixelů.  
  
-   Každý typ souborů může mít jeden embedded panelu nástrojů nebo jeden globální nástrojů specifické pro dokument, ale ne obojí.  
  
 **Panely nástrojů konkrétní** se zobrazí při určitých kontextu je nastavit a zpravidla zůstane aktivní po delší dobu.  
  
-   Tlačítko limit pro všechny konkrétní panely nástrojů je 18.  
  
-   Pokud většina uživatelů nebude využívat konzistentně příkazy tohoto panelu nástrojů, když je aktivní kontextu, pak nemusíte přidružit tento panel nástrojů kontextu.  
  
-   Ujistěte se, že panelu nástrojů zmizí při ukončení kontextu. Žádná z těchto panely nástrojů by se zobrazit při spuštění.  
  
 **Panely nástrojů s žádný kontext** nikdy nezobrazí automaticky. Tyto zobrazují, pouze když uživatel aktivuje je. Zachovat maximální šířka níže 200 pixelů.  
  
### <a name="general-organization-and-shell-defined-groups"></a>Obecné organizace a prostředí definované skupiny  
 Použijte existující sdílené příkazy, příkaz skupin a nabídek. Pokud nový příkaz musí být definován, zkuste jej umístit do existující skupiny sdílené příkaz. Pokud do nové skupiny musí být definován, zkuste jej umístit do existující sdílené nabídky blízko skupinu souvisejícím příkazem před vytvořením nové nabídky nejvyšší úrovně. Tím se snižuje složitost příkazu a zajistit konzistentní příkaz umístění v prostředí IDE.  
  
 Sdílený **formát** nabídky, obvykle se zobrazí v kontextu windows dokument návrháře stylu je znázorněno na následujícím obrázku:  
  
 ![Visual Studio formát nabídku s popisky](../../extensibility/ux-guidelines/media/0501-d_formatmenu.png "0501 d_FormatMenu")  
  
 **Skupiny nabídek v sadě Visual Studio**  
  
### <a name="reducing-and-reusing-commands"></a>Omezení a opakované používání příkazů  
 Příkazy se obvykle zobrazují na základě v kontextu, chcete-li snížit počet příkazů, které se uživateli zobrazí v daném okamžiku. Ale měli také znovu použít stávající sdílené nabídky a příkaz skupiny zajistit, že příkazovou strukturu zůstává relativně ustájení mezi změny v kontextu.  
  
 Opětovné použití sdílených příkazů a umístění nové příkazy blízko související sdílené příkazy snižuje složitost IDE a vytvoří přívětivější prostředí.  
  
## <a name="naming-commands"></a>Názvy příkazů  
  
### <a name="naming-conventions"></a>Zásady vytváření názvů  
 Příkaz konzistentní názvy je důležité, aby uživatelé mohli najít a spustit příkazy, buď pomocí příkazového řádku nebo vytvoření vazby na klávesové zkratky. Názvy příkazů také pomůže pochopit, jaké účel příkaz slouží, jakmile se zobrazí na panelu nástrojů nebo v nabídce kaskádových nebo kontextu uživatele.  
  
#### <a name="when-naming-commands"></a>Pojmenování při příkazy:  
  
-   Vytvořte text tak, aby se snadno lokalizovatelný. Další informace o lokalizaci text najdete v tématu [World připravenosti pro sadu Visual Studio](http://msdn.microsoft.com/en-us/1cc35051-8126-441f-bea9-059245a47b1d).  
  
-   Být stručné sdělení. Příkazy měli používat více než tří slov.  
  
-   Použít první písmeno velké malá a velká písmena: první písmena jednotlivých slov by měla být velkými písmeny. Další informace o formátování textu v sadě Visual Studio najdete v tématu [styl textu](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md#BKMK_TextStyle).  
  
-   Vzít v úvahu, kde budou umístěné příkaz. Je v nabídek nejvyšší úrovně nebo rozevírací nabídka? Například když seskupení zarovnání příkazy v plovoucím panelem nejvyšší úrovně příkazu by měl být "Align" a příkazy plovoucím panelem by měl být "Vlevo," "Vpravo", "Center", "Justify" a tak dále. By bylo nadbytečné název plovoucím panelem příkazů "Align vlevo" nebo "Align právo."  
  
     ![Visual Studio formátu nabídky](../../extensibility/ux-guidelines/media/0502-a_formatmenu.png "0502 a_FormatMenu")  
  
### <a name="using-icons-with-commands"></a>Pomocí ikony příkazů  
 Reserve být Sparing Table použití ikonu párování s příkazy. I když přiřazení jedinečné bitovou kopii pomocí příkazu hastens uživateli možnost pro identifikaci tohoto příkazu, visual zbytečné soubory a neefektivnost se provádějí pomocí bitové kopie nadměrné využití. Následující pravidla pomoci při rozhodování, jestli se mají vytvořit ikona příkazu.  
  
#### <a name="use-an-icon-with-a-command-only-if"></a>Použijte ikonu s pouze pokud příkaz:  
  
-   Stejný příkaz obsahuje ikonu přidružena v jiné viditelného produktu společnosti Microsoft, jako je například jeden z aplikace Microsoft Office.  
  
-   Příkaz se umístí na panelu nástrojů, výchozí.  
  
-   Příkaz je speciální příkaz, který uživatelé je pravděpodobné, že pro přidání do panelu nástrojů pomocí **"Přizpůsobit..."** dialogové okno.  
  
## <a name="access-and-shortcut-keys"></a>Přístup a zástupce klíče  
  
### <a name="overview"></a>Přehled  
 Existují dva druhy klíče Přiřazení klávesové:  
  
-   **Přístupové klíče** (také označované jako akcelerátorů) povolit přístup klávesnice přes v nabídkách pro tvorba příkazů a každý popisek v dialogovém okně uživatelského rozhraní. Přístupové klávesy jsou většinou za účelem usnadnění, jsou přiřazeny všechny nabídky a většina pole ovládací prvky dialogového okna, neměli být zvyklí, vliv jenom na aktuální okno a lokalizace.  
  
-   **Klávesové zkratky** většinou používat ovládací prvek (Ctrl) a klíče pořadí určena funkční. Jsou navrženy více pro pokročilé uživatele a podpora zvýšení produktivity. Tyto jsou přiřazeny pouze většinu často používané příkazy a povolit Rychlý přístup při obcházení v hlavní nabídce. Klávesové zkratky by měla být zvyklí, a pro které musí být přiřazena důvod konzistentní se schématem profil. Zástupce klíče schémata se může lišit profil z profilu. Uživatel může přizpůsobit klávesové zkratky prostřednictvím **nástroje > Možnosti > klávesnice**.  
  
### <a name="assigning-access-keys"></a>Přiřazení přístupových kláves  
 Přístupové klávesy obsahovat alternativní plus alfanumerické klíče. Přiřaďte přístupový klíč pro každou položku nabídky bez výjimky. Postupujte podle Windows a běžné konvence pro přiřazení přístupových kláves. například přístupový klíč pro **soubor > Nový** by měla být vždy **Alt, F, N**.  
  
 Šířka v pixelech jedním písmena, například "i" (v velká nebo malá písmena) nebo malá "l" a nepoužíváte jsou tyto obtížné rozlišit nepoužívejte znaky s dolní dotahy (g, j, p, otázek a y).  
  
 Nepoužívejte duplicitní klíče, pokud je to možné. V případech, kdy nevyhnutelné duplicity systém nabídek zpracovává konflikty cyklického všechny příkazy, které používají klíče. Jako příklad pro hypotetické "Number" příkazů v nabídce Soubor, který duplikuje přístupový klíč "N" **Alt, F, N** by vytvoření nového souboru, a **Alt, F, N, N** by proveďte příkaz "Číslo".  
  
### <a name="assigning-shortcut-keys"></a>Přiřazení klávesové zkratky  
 Nepřiřazujte nové klávesové zkratky, protože nejsou nutné pro každý příkaz a daně systému (a uživatelské paměti), pokud Nepromyšlené. Data z zkušeností zlepšování Program uživatelů (CEIP) označuje, že uživatelé sady Visual Studio používat pouze malou podmnožinu integrované zástupce.  
  
 Při definování zástupce, postupujte podle těchto pravidel:  
  
-   **Použití ovládacího prvku (Ctrl) a určena funkční klávesy pořadí.**  
  
-   **Zachovejte zástupce často používaných.** Udržujte nejoblíbenější zástupce.  
  
-   **Usnadňují zadejte zkratky editor.** BIND – typ zkratky příkazy, že vývojáři potřebujete nejvíce při psaní kódu. Například **Edit.InvokeSmartTag** musí mít rychlé klávesovou zkratku jako Ctrl +/ a není Alt + Shift + F10.  
  
-   **Zajistit pro konzistentně motivu zástupce.**  
  
-   **Postupujte podle pokynů Windows k určení, které modifikátor klíče využívat.** Pomocí kombinace kláves Ctrl pro příkazy, které mají rozsáhlé důsledky, jako je například příkazy, které platí pro celý dokument. Pomocí klávesy Shift kombinace pro příkazy, které rozšířit nebo doplňují akce standardní klávesovou zkratku. Nepoužívejte kombinace kláves Ctrl + Alt.  
  
-   **Odeberte nadbytečné zástupce.** Pokud máte starší verze funkce, zvažte odebrání zkratky, které se používají s extrémně infrequency (méně než 10 x z dat programu CEIP) nebo střední infrequency (méně než 100krát z dat programu CEIP), pokud přístupový klíč poskytuje rychlý přístup k stejný příkaz. Příklad: C Alt, H, otevře se obsah nápovědy k /.  
  
 Není k dispozici jednoduchý způsob, jak zkontrolovat dostupnost zástupce. Pokud chcete přidat zástupce, postupujte takto:  
  
1.  Zkontrolujte seznam [Visual Studio 2013 zkratky](http://visualstudioshortcuts.com/2013/) k určení, zda jsou podobné příkazy k seskupení váš s.  
  
2.  Přejděte na **nástroje > Možnosti > prostředí > klávesnice** a testování vaší zástupce. Zkontrolujte, zda že každý schéma mapování klávesnice uvedené v části "Použít následující schéma mapování klávesnice Další." Obecné, C#, VB a C++ profilů, zkontrolujte jako ty, sdílené složky jedinečný zástupce. Vaše místní je k dispozici, pokud není namapované v některém z těchto míst.