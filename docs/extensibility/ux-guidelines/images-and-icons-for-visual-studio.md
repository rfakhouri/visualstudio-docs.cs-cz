---
title: "Bitové kopie a ikony pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f410325e-9cf2-4f39-b6d7-b672121c2691
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7856f8fac7e986f3e5383fa91261de39fe815a28
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="images-and-icons-for-visual-studio"></a>Bitové kopie a ikony pro sadu Visual Studio
##  <a name="BKMK_ImageUseInVisualStudio"></a>Použití bitové kopie v sadě Visual Studio  
 Před vytvořením kresby, zvažte provedení použití obrázků 1 000 + v [knihovna obrázků Visual Studio](http://www.microsoft.com/en-my/download/details.aspx?id=35825).  
  
### <a name="types-of-images"></a>Typy obrázků  
  
-   **Ikony**. Malé bitové kopie, které se zobrazují v příkazy, hierarchie, šablon a tak dále. Výchozí velikost ikony použít v sadě Visual Studio je PNG velikosti 16 x 16. Ikony vytváří služba image automaticky generovat formátu XAML pro podporu HDPI.  
  
     **Poznámka:** při Image se používají v nabídce systému, byste je neměli vytvářet ikonu pro každý příkaz. Poraďte se [nabídek a příkazů pro sadu Visual Studio](../../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md) zobrazíte, zda váš příkaz měli získat ikonu.  
  
-   **Miniatury.** Obrázků použitých v oblasti náhledu dialogového okna, jako je například dialogové okno Nový projekt.  
  
-   **Dialogové okno Image.** Bitové kopie, které se zobrazují v dialogová okna nebo průvodců, buď jako popisný grafiky nebo indikátory zprávy. Použijte zřídka a pouze v případě potřeby k objasnění konceptu obtížné nebo k získání pozornost uživatele (výstrah, upozornění).  
  
-   **Animovaný bitové kopie.** V indikátory průběhu stavové řádky a dialogová okna operaci použít.  
  
-   **Kurzory.** Slouží k určení, zda je povoleno operace pomocí myši, kde může být zrušená, objekt a tak dále.  
  
##  <a name="BKMK_IconDesign"></a>Ikona návrhu  
  
### <a name="overview"></a>Přehled  
 Visual Studio použije moderních styl ikony, které mají čistou geometry a 50/50 rovnováhu mezi počtem kladné nebo záporné (světlý nebo tmavý) a použít přímé, nerozumí metaphors. Zásadní ikonu center body návrhu kolem přehlednost, zjednodušení a kontext.  
  
-   **Přehlednost:** soustředit na jedná jádra, která poskytuje ikonu jeho významy a osobnosti.  
  
-   **Zjednodušení:** snižte ikonu na její základní význam – načtení motivu s právě nezbytné elementy a žádné frills.  
  
-   **Kontext:** vezměte v úvahu všechny aspekty role na ikonu během vývoje pojem, který je zásadní při rozhodování o prvky, které tvoří jádro jedná na ikonu.  
  
 U ikon jsou počet body návrhu, aby se zabránilo:  
  
-   Nepoužívejte ikony, které označují prvky uživatelského rozhraní s výjimkou v případě nutnosti. Vyberte více abstraktní nebo symbolické přístup, pokud element uživatelského rozhraní není běžné, zřejmá, ani jedinečný.  
  
-   Není vhodné používat nadměrně společné prvky, jako jsou dokumenty, složek, šipky a lupu. Pomocí těchto prvků jenom v případě, že je nezbytně nutné, aby na ikonu význam. Například s ikonou lupy pravé straně by měl být uveden pouze hledání, procházet a najít.  
  
-   I když některé prvky starší ikona udržovat použití perspektivy, nevytvářejte nové ikony s perspektivy Pokud element chybí přehlednost bez ní.  
  
-   Nemáte cram příliš velkého množství informací do ikony. Jednoduché bitovou kopii, která se dá snadno rozpoznat nebo se dozvěděli, jak symbol rozpoznatelném oceníte, víc než příliš složité image. Ikona nelze všechno.  
  
### <a name="icon-creation"></a>Ikona vytvoření  
  
#### <a name="concept-development"></a>Koncept vývoj  
 Visual Studio má v jeho uživatelském rozhraní širokou škálu typy ikon. Pečlivě zvažte typ ikonu během vývoje. Nepoužívejte jasné nebo neobvyklé objektů uživatelského rozhraní pro prvky vaši ikonu. Zvolit symbolický odkaz v těchto případech, například s ikonou inteligentních značek. Upozorňujeme, že význam abstraktní značky na levé straně zřejmější, než je verze nepřesných, na základě uživatelského rozhraní na pravé straně:  
  
|||  
|-|-|  
|**Správné použití symbolický dokumentů**|**Nesprávné použití symbolický dokumentů**|  
|![Ikona správné inteligentní značky](../../extensibility/ux-guidelines/media/0404-01_smarttagcorrect.png "0404 01_SmartTagCorrect")|![Nesprávný ikona inteligentní značky](../../extensibility/ux-guidelines/media/0404-02_smarttagincorrect.png "0404 02_SmartTagIncorrect")|  
  
 Existuje instancí, ve kterých je standardní, snadno rozpoznatelné prvky uživatelského rozhraní fungují dobře u ikon. Přidáte že okno je jedním z těchto příkladů:  
  
|||  
|-|-|  
|**Správný prvek uživatelského rozhraní v ikony**|**Nesprávný prvek uživatelského rozhraní v ikony**|  
|![Správné ikony Přidat okno](../../extensibility/ux-guidelines/media/0404-03_addwindowcorrect.png "0404 03_AddWindowCorrect")|![Nesprávný ikona Přidat okno](../../extensibility/ux-guidelines/media/0404-04_addwindowincorrect.png "0404 04_AddWindowIncorrect")|  
  
 Nepoužívejte dokumentu jako základní prvek Pokud to není nezbytně nutné, aby na ikonu význam. Bez dokumentu dojde ke ztrátě nebo element na Přidat dokument (pod) význam, zatímco s aktualizací není nutný pro komunikaci význam element dokumentu.  
  
|||  
|-|-|  
|**Správné použití ikony dokumentu**|**Nesprávné použití ikony dokumentu**|  
|![Ikona správné dokumentu](../../extensibility/ux-guidelines/media/0404-05_documenticoncorrect.png "0404 05_DocumentIconCorrect")|![Nesprávný ikona dokumentu](../../extensibility/ux-guidelines/media/0404-06_documenticonincorrect.png "0404 06_DocumentIconIncorrect")|  
  
 Koncept "Zobrazit" by měl být zobrazen na ikonu, která nejlépe znázorňuje, co je zobrazeno, například stejně jako u příkladu zobrazit všechny soubory. Jedná přehledu může slouží k určení koncepci "Zobrazit" v případě potřeby jako příklad zobrazení prostředků.  
  
|||  
|-|-|  
|**"Zobrazit"**|**"Zobrazit"**|  
|![Zobrazit ikonu](../../extensibility/ux-guidelines/media/0404-07_show.png "0404 07_Show")|![Ikona zobrazení](../../extensibility/ux-guidelines/media/0404-08_view.png "0404 08_View")|  
  
 Pravého okraje zvětšení pohotovostní ikonu, by měl představují pouze vyhledávání, najít a procházení. Variant směřující vlevo s znaménko plus nebo minus by měla představovat pouze zvětšení v / oddálení.  
  
|||  
|-|-|  
|**"Vyhledat"**|**"Přiblížení"**|  
|![Ikonu hledání](../../extensibility/ux-guidelines/media/0404-09_search.png "0404 09_Search")|![Ikona přiblížení](../../extensibility/ux-guidelines/media/0404-10_zoom.png "0404 10_Zoom")|  
  
 Ve stromové zobrazení, nepoužívejte ikonou složky a modifikační. Pokud je k dispozici, použijte pouze modifikátor.  
  
|||  
|-|-|  
|**Správné stromové zobrazení ikon**|**Nesprávný stromové zobrazení ikon**|  
|![Ikona zobrazení správné stromu &#40; 1 &#41; ] (../../extensibility/ux-guidelines/media/0404-11_treeviewcorrect1.png "0404 11_TreeViewCorrect1") ![opravte ikona zobrazení stromu &#40; 2 &#41;] (../../extensibility/ux-guidelines/media/0404-12_treeviewcorrect2.png "0404 12_TreeViewCorrect2")|![Ikona zobrazení nesprávný stromu &#40; 1 &#41; ] (../../extensibility/ux-guidelines/media/0404-13_treeviewincorrect1.png "0404 13_TreeViewIncorrect1") ![nesprávný ikona zobrazení stromu &#40; 2 &#41;] (../../extensibility/ux-guidelines/media/0404-14_treeviewincorrect2.png "0404 14_TreeViewIncorrect2")|  
  
### <a name="style-details"></a>Styl Podrobnosti  
  
#### <a name="layout"></a>Rozložení  
 Prvky zásobníku, jak je uvedeno pro standardní velikosti 16 x 16 ikony:  
  
 ![Zásobník rozložení pro velikosti 16 x 16 ikony](../../extensibility/ux-guidelines/media/0404-15_layoutstack.png "0404 15_LayoutStack")<br />Rozložení zásobníku u ikon, 16 x 16.
  
 Stav oznámení prvky jsou lepší použít jako samostatné ikony. Existují kontextů, ale, ve kterých oznámení by měla být skládaný na základní elementu, například ikonou úloha ukončena:  
  
 ![Samostatné oznámení v sadě Visual Studio](../../extensibility/ux-guidelines/media/0404-16_standalonenotificationicons.png "0404 16_StandaloneNotificationIcons")<br />Samostatné oznámení ikony
  
 ![Ikona dokončení úlohy](../../extensibility/ux-guidelines/media/0404-17_taskcomplete.png "0404 17_TaskComplete")<br />Ikona dokončení úlohy
  
 Ikony projektu jsou obvykle .ico, který soubory, které obsahují více velikostí. Většina velikosti 16 x 16 ikony obsahují stejné prvky. Verze 32 x 32 mají další podrobnosti, včetně typu projektu v případě potřeby.  
  
 ![Projekt ikony v sadě Visual Studio](../../extensibility/ux-guidelines/media/0404-18_iconprojectthreesizes.png "0404 18_IconProjectThreeSizes")<br />Projektu knihovny ovládacího prvku Windows VB ikony, velikosti 16 x 16 a 32 x 32. 
  
 Center ikony v rámci jeho pixelů. Pokud tento způsob není možný, zarovnejte na ikonu na začátek nebo napravo od rámečku.  
  
 ![Ikona zarovnaný na střed v rámci pixelů](../../extensibility/ux-guidelines/media/0404-19_iconcentered.png "0404 19_IconCentered")<br />Ikona zarovnaný na střed v rámci pixelů
  
 ![Ikona zarovnán top napravo od rámce pixelů](../../extensibility/ux-guidelines/media/0404-20_icontopright.png "0404 20_IconTopRight")<br />Ikona zarovnán horní napravo od rámečku
  
 ![Ikona zarovnaný na střed a zarovnán horní pixelů rámce](../../extensibility/ux-guidelines/media/0404-21_icontopalign.png "0404 21_IconTopAlign")<br />Ikona zarovnaný na střed a zarovnat do horní části rámečku
  
 K dosažení ideální zarovnání a vyrovnávat, vyhněte se programy blokují element base na ikonu s akce glyfů. Místní glyfů v horní pravé base element. Při přidávání dalších elementu, vezměte v úvahu zarovnání a rovnováhou mezi počtem ikonu.  
  
|||  
|-|-|  
|**Správné zarovnání a zůstatek**|**Nesprávný zarovnání a zůstatek**|  
|![Opravte vyrovnávání ikonu a zarovnání](../../extensibility/ux-guidelines/media/0404-22_alignbalancecorrect.png "0404 22_AlignBalanceCorrect")|![Nesprávný ikonu vyrovnávat a zarovnání](../../extensibility/ux-guidelines/media/0404-23_alignbalanceincorrect.png "0404 23_AlignBalanceIncorrect")|  
  
 Zkontrolujte velikost paritní u ikon, které sdílejí elementy a používají se v sadách. Všimněte si, že v nesprávný párování kruh a ŠIPKA nadměrnou velikost a se neshodují.  
  
|||  
|-|-|  
|**Parita správnou velikost**|**Nesprávná velikost parita**|  
|![Opravte velikost ikony a parita](../../extensibility/ux-guidelines/media/0404-24_sizeparitycorrect.png "0404 24_SizeParityCorrect")|![Nesprávná velikost a parita](../../extensibility/ux-guidelines/media/0404-25_sizeparityincorrect.png "0404 25_SizeParityIncorrect")|  
  
 Používejte konzistentní řádku a visual váhu. Vyhodnoťte, jak na ikonu, které vytváříte porovnává další ikony pomocí porovnání vedle sebe. Nikdy nepoužívejte celý velikosti 16 x 16 rámečku, použijte 15 x 15 nebo menší. Poměr záporné kladnou (světlý light) by měl být 50/50.  
  
|||  
|-|-|  
|**Správné záporné kladnou poměr**|**Nesprávný poměr záporné kladnou**|  
|![Opravte visual váha pro ikon &#40; 1 &#41; ] (../../extensibility/ux-guidelines/media/0404-26_visualweightcorrect1.png "0404 26_VisualWeightCorrect1")<br /><br /> ![Opravte visual váha pro ikon &#40; 2 &#41; ] (../../extensibility/ux-guidelines/media/0404-27_visualweightcorrect2.png "0404 27_VisualWeightCorrect2")<br /><br /> ![Opravte visual váha pro ikon &#40; 3 &#41; ] (../../extensibility/ux-guidelines/media/0404-28_visualweightcorrect3.png "0404 28_VisualWeightCorrect3")|![Nesprávný visual váha pro ikony](../../extensibility/ux-guidelines/media/0404-29_visualweightincorrect.png "0404 29_VisualWeightIncorrect")|  
  
 Použijte jednoduchý, porovnatelný z hlediska tvarů a doplňkové úhly k vytváření prvky vaši zároveň zachovávají element integrity. Použijte 45° nebo 90° úhly, kde je to možné.  
  
 ![Opravte ikonu úhly](../../extensibility/ux-guidelines/media/0404-30_iconanglescorrect.png "0404 30_IconAnglesCorrect")  
  
#### <a name="perspective"></a>Perspektiva  
 Zachovat na ikonu jasné a srozumitelné. Pomocí perspektivy a zdroje světla pouze v případě potřeby. I když je zabránit pomocí perspektivy na ikonu elementy, nerozpoznatelný bez některé prvky. V takových případech komunikuje stylizované perspektivy přehlednost elementu.  
  
 ![3bod perspektivy](../../extensibility/ux-guidelines/media/0404-31_3pointperspective.png "0404 31_3PointPerspective")<br />3bod perspektivy
  
 ![1 bod perspektivy](../../extensibility/ux-guidelines/media/0404-32_1pointperspective.png "0404 32_1PointPerspective")<br />1 bod perspektivy
  
 Většina elementů by měl být čelí nebo šikmo vpravo:  
  
 ![Ikony šikmo právo](../../extensibility/ux-guidelines/media/0404-33_angledright.png "0404 33_AngledRight")  
  
 Používejte zdroje světla jenom v případě, že přidání nezbytné přehlednost do objektu.  
  
|||  
|-|-|  
|**Správné světelného zdroje**|**Nesprávný světelného zdroje**|  
|![Opravte zdroje světla u ikon,](../../extensibility/ux-guidelines/media/0404-34_lightsourcescorrect.png "0404 34_LightSourcesCorrect")|![Nesprávný zdroje světla u ikon,](../../extensibility/ux-guidelines/media/0404-35_lightsourcesincorrect.png "0404 35_LightSourcesIncorrect")|  
  
 Pomocí jsou podrobněji popsány dále pouze k vylepšení čitelnosti nebo lépe komunikovat jedná. Vyrovnávat (světlý light) záporné pozitivní by měl být 50/50.  
  
|||  
|-|-|  
|**Správné použití jsou podrobněji popsány dále**|**Nesprávné použití jsou podrobněji popsány dále**|  
|![Opravte jsou podrobněji popsány dále](../../extensibility/ux-guidelines/media/0404-36_outlinescorrect.png "0404 36_OutlinesCorrect")|![Nesprávný jsou podrobněji popsány dále](../../extensibility/ux-guidelines/media/0404-37_outlinesincorrect.png "0404 37_OutlinesIncorrect")|  
  
#### <a name="icon-types"></a>Typy ikon  
 **Skořápce a příkazový řádek** ikony obsahovat více než tří z těchto prvků: jeden základní jeden modifikátor, jednu akci nebo jeden stav.  
  
 ![Příklady skořápce a příkazový řádek ikony](../../extensibility/ux-guidelines/media/0404-38_shellicons.png "0404 38_ShellIcons")<br />Příklady skořápce a příkazový řádek ikony
  
 **Panelu nástrojů okna příkaz** ikony obsahovat více než tří z těchto prvků: jeden základní jeden modifikátor, jednu akci nebo jeden stav.  
  
 ![Příklady okno nástroje příkaz panelu ikony](../../extensibility/ux-guidelines/media/0404-39_toolwindowcommandbaricons.png "0404 39_ToolWindowCommandBarIcons")<br />Příklady nástroj okna příkazového řádku ikony
  
 **Stromové zobrazení disambiguator** ikony obsahovat více než tří z těchto prvků: jeden základní jeden modifikátor, jednu akci nebo jeden stav.  
  
 ![Příklady stromové zobrazení ikon disambiguator](../../extensibility/ux-guidelines/media/0404-40_treeviewicons.png "0404 40_TreeViewIcons")<br />Příklady stromové zobrazení disambiguator ikony
  
 **Na základě stavu hodnota taxonomii** ikony existovat v následujících stavů: aktivní, zakázáno aktivní a neaktivní zakázáno.  
  
 ![Příklady ikon na základě stavu hodnota taxonomii](../../extensibility/ux-guidelines/media/0404-41_statebasedtaxonomy.png "0404 41_StateBasedTaxonomy")<br />Příklady ikony taxonomii hodnotu na základě stavu
  
 **IntelliSense** ikony obsahovat více než tří z těchto prvků: jeden základní, jeden modifikátor a jeden stav.  
  
 ![Příklady IntelliSense ikony](../../extensibility/ux-guidelines/media/0404-42_intellisenseicons.png "0404 42_IntelliSenseIcons")<br />Příklady ikony IntelliSense
  
 **Malé (16 x 16) projektu** ikony by měl mít více než dva elementy: jeden základní a jeden modifikátor.  
  
 ![Příklady malé (16 x 16) projektu ikony](../../extensibility/ux-guidelines/media/0404-43_16x16project1.png "0404 43_16x16Project1") ![velikosti 16 x 16 projektu ikonu &#40; 2 &#41;] (../../extensibility/ux-guidelines/media/0404-44_16x16project2.png "0404 44_16x16Project2") ![velikosti 16 x 16 projektu ikonu &#40; 3 &#41;] (../../extensibility/ux-guidelines/media/0404-45_16x16project3.png "0404 45_16x16Project3")<br />Příklady malé ikony projektu (16 x 16.)
  
 **Velké projektu (32 x 32)** ikony skládat z více než čtyři následující elementy: jeden základní, jednu až dvě modifikátory a jeden jazyk překrytí.  
  
 ![Příklady velké (32 x 32) projektu ikony](../../extensibility/ux-guidelines/media/0404-46_32x32project.png "0404 46_32x32Project")<br />Příklady projektu (32 x 32) ikony. velké ikony
  
### <a name="production-details"></a>Podrobnosti výroby  
 Všechny nové prvky uživatelského rozhraní by měl být vytvořen pomocí Windows Presentation Foundation (WPF) a všechny nové ikony pro grafický subsystém WPF by měl být ve formátu PNG 32-bit. PNG 24bitový je starší verze formátu, který nepodporuje průhlednost a nedoporučuje se u ikony.  
  
 Uložte řešení při 96 DPI.  
  
#### <a name="file-types"></a>Typy souborů  
  
-   **32-bit PNG:** upřednostňované formát ikony. Formát souboru komprese beze ztrát dat, který může ukládat bitové kopie jedné rastrové (pixelů). soubory PNG 32-bit podporují průhlednost alfa kanálu, korekce gama a prokládání.  
  
-   **32-bit BMP:** pro ovládací prvky grafického subsystému WPF. 32-bit BMP označovaný taky jako XP nebo vysokou barvu, je formátu RGB/A bitovou kopii, bitovou kopii true-color s průhlednost alfa kanálu. Alfa kanálu je vrstva průhlednosti uvedených v aplikaci Adobe Photoshop, který pak je uložena v rámci rastrový obrázek jako další (čtvrtý) barevný kanál. Na černém pozadí se přidá během produkční kresby na všechny soubory BMP 32-bit zajistit rychlý vizuální upozornění o hloubku barev. Tato černém pozadí představuje oblasti zamaskovaná v uživatelském rozhraní.  
  
-   **32-bit ICO:** ikony projektu a přidat položku. Všechny soubory ICO jsou 32bitové true barvy s průhlednost alfa kanálu (RGB nebo A). Protože soubory ICO můžete uložit více velikosti a barvy depths, Vista ikony jsou často ve formátu ICO obsahující velikosti 16 x 16, 32 x 32, 48 × 48 a velikosti obrázků 256 x 256. Aby bylo možné zobrazit správně v Průzkumníku Windows, ICO soubory musí být uložena dolů do hloubky 24bitový a 8bitové barev pro každý velikost bitové kopie.  
  
-   **XAML:** návrhové ploše a ozdobného prvku systému Windows. Ikony XAML jsou vektorové obrazových souborů, které podporují škálování, otáčení, podání a průhlednost. Dnes nejsou běžné v sadě Visual Studio, ale jsou stále oblíbenější z důvodu jejich flexibilitě.  
  
-   **SVG**  
  
-   **BMP 24bitový:** pro panel příkazů sady Visual Studio. Formát obrázku RGB barvami hodnotu true, BMP 24bitový je konvence ikonu, která vytvoří vrstvu průhlednost pomocí Purpurová (R = 255, G = 0, B = 255) jako klíč barvu pro vrstvu, na více systémů knock průhlednost. V 24bitové BMP jsou zobrazené všechny fialové plochy pomocí barvu pozadí.  
  
-   **GIF 24bitový:** pro panel příkazů sady Visual Studio. Formát obrázku RGB barvami hodnotu true, který podporuje průhlednost. GIF – soubory se často používají v kresbě průvodce a animací ve formátu GIF.  
  
### <a name="icon-construction"></a>Ikona konstrukce  
 Nejmenší velikost ikony v sadě Visual Studio je velikosti 16 x 16. Největší společné použití je 32 x 32. Mějte na paměti nechcete zaplnit celý rámečku velikosti 16 x 16, 24 x 24 nebo 32 x 32 při navrhování ikonu. Ikona čitelná, uniform konstrukce je nezbytné pro rozpoznávání uživatele. Při vytváření ikony splňovat následující body.  
  
-   Ikony musí být jasné, srozumitelné a konzistentní.  
  
-   Je lepší použít elementy oznámení stavu jako jeden ikony, ne na zásobníku je nad ikonu základní elementu. V některých kontextech rozhraní může vyžadovat elementu stav, který chcete být spárována s base element.  
  
-   Ikony projektu jsou obvykle .ico, který soubory, které obsahují několik velikosti. Aktualizované pouze ikony velikosti 16 x 16, 24/24 a 32 x 32. Většina velikosti 16 x 16 a 24 x 24 ikony bude obsahovat stejné prvky. Ikony 32 x 32 obsahují další podrobnosti, včetně typu projektu jazyk, v případě potřeby.  
  
-   Pro 32 x 32 ikony mají základní prvky obvykle tloušťku čáry 2 pixelů. Tloušťku čáry 1 nebo 2 pixelů lze použít u elementů podrobností. Jejich použití by k určení, které je vhodnější.  
  
-   Máte alespoň 1 pixel mezery mezi elementy pro velikosti 16 x 16 a ikony 24 x 24. Ikony 32 x 32 použijte pixelů 2 mezery mezi elementy a mezi modifikátor a base element.  
  
 ![Element mezer pro ikony velikosti 16 x 16, 24/24 a 32 x 32](../../extensibility/ux-guidelines/media/0404-47_elementspacing.png "0404 47_ElementSpacing")<br />Vzdálenost prvků pro ikony velikosti 16 x 16, 24/24 a 32 x 32.
  
#### <a name="color-and-accessibility"></a>Barvy a usnadnění přístupu  
 Visual Studio předpisy vyžadují, aby všechny ikony v rámci produktu předat požadavky na usnadnění přístupu pro barvy a kontrast. Toho je dosaženo pomocí inverzi ikonu a při návrhu, je třeba si uvědomit, že se bude obrácený prostřednictvím kódu programu v rámci produktu.  
  
 Další informace o použití barev v sadě Visual Studio ikony najdete v tématu [pomocí barev v obrázcích](../../extensibility/ux-guidelines/images-and-icons-for-visual-studio.md#BKMK_UsingColorInImages).  
  
##  <a name="BKMK_UsingColorInImages"></a>Pomocí barev v obrázcích  
  
### <a name="overview"></a>Přehled  
 Jsou primárně jednobarevných ikony v sadě Visual Studio. Barva je vyhrazena pro vyjádření konkrétní informace a nikdy pro dekorace. Je použita barva:  
  
-   k označení akce  
  
-   výstrahy oznámení o stavu uživatele  
  
-   Chcete-li určit přidružení jazyk  
  
-   k odlišení položky v rámci technologie IntelliSense  
  
### <a name="accessibility"></a>Usnadnění  
 Visual Studio předpisy vyžadovat, že všechny ikony zaškrtnuté do produktu průchodu požadavky na usnadnění přístupu pro barvy a kontrast. Barvy palety visual jazyk byly testovány a splňovat tyto požadavky.  
  
#### <a name="color-inversion-for-dark-themes"></a>Inverze barev pro tmavý motivů  
 Aby bylo možné ikony, zobrazí se poměr správný kontrast v sadě Visual Studio tmavý motiv, je použita inverzi prostřednictvím kódu programu. Barvy v této příručce byla částečně vybrali tak, aby se Invertovat správně. Omezit využití barev palety, nebo při použití inverzi bude dojít k neočekávaným výsledkům.  
  
 ![Příklady ikony, které předtím jejich barvy obrácený](../../extensibility/ux-guidelines/media/0405-01_darkthemeinversion.png "0405 01_DarkThemeInversion")<br />Příklady ikony, které předtím jejich barvy obrácený
  
### <a name="base-palette"></a>Základní palety  
 Všechny standardní ikony obsahovat tři základní barvy. Ikony obsahovat žádné přechody nebo stíny s jedno nebo dvě výjimky pro 3D nástroj ikony.  
  
|Použití|Název|Hodnota (motiv světlý)|Vzorníku|Příklad|  
|-----------|----------|---------------------------|------------|-------------|  
|Pozadí nebo tmavý|VS BG|424242 / 66,66,66|![Vzorníku 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|![Příklad základní palety](../../extensibility/ux-guidelines/media/0405-02_basepaletteexample.png "0405 02_BasePaletteExample")|  
|Popředí/lehký|VS FG|F0EFF1 / 240,239,241|![Vzorníku F0EFF1](../../extensibility/ux-guidelines/media/0405_f0eff1.png "0405_F0EFF1")||  
|Obrys|VS Out|F6F6F6 / 246,246,246|![Vzorníku F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")||  
  
 Kromě základní barvy každá ikona může obsahovat jeden další barvu z rozšířené palety.  
  
### <a name="extended-palette"></a>Rozšířené palety  
  
#### <a name="action-modifiers"></a>Modifikátory akce  
 Následující čtyři barvy označují typy akcí, které vyžadují Modifikátory akce:  
  
|Použití|Název|Hodnota (všechny motivy)|Vzorníku|  
|-----------|----------|--------------------------|------------|  
|Kladné|Zelená akce VS|388A34 / 56,138,52|![Vzorníku 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|Záporný|Akce Red VS|A1260D / 161,38,13|![Vzorníku A1260D](../../extensibility/ux-guidelines/media/0405_a1260d.png "0405_A1260D")|  
|Neutrální|Modrá akce VS|00539C / 0,83,156|![Vzorníku 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|Vytvořit nový|Oranžová akce VS|C27D1A / 194,156,26|![Vzorníku C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
  
##### <a name="examples"></a>Příklady  
 Zelená se používá pro modifikátory kladné akce jako "Přidat", "Spustit," "Spustit" a "Ověřit".  
  
|||||  
|-|-|-|-|  
|![Spustit ikonu](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405 03_ActionModifierRun")<br />Spustit|![Spuštění dotazu ikonu](../../extensibility/ux-guidelines/media/0405-04_executequery.png "0405 04_ExecuteQuery")<br />Spuštění dotazu|![Přehrání všechny kroky ikonu](../../extensibility/ux-guidelines/media/0405-05_playallsteps.png "0405 05_PlayAllSteps")<br />Přehrání všechny kroky|![Přidání ovládacího prvku ikony](../../extensibility/ux-guidelines/media/0405-06_addcontrol.png "0405 06_AddControl")<br />Přidání ovládacího prvku|  
  
 Red se používá pro modifikátory záporné akce jako "Odstranit," "Stop", "Zrušit" a "Ukončit."  
  
|||||  
|-|-|-|-|  
|![Odstranit ikonu vztah](../../extensibility/ux-guidelines/media/0405-07_deleterelationship.png "0405 07_DeleteRelationship")<br />Odstranit vztah|![Odstranit ikonu sloupec](../../extensibility/ux-guidelines/media/0405-08_deletecolumn.png "0405 08_DeleteColumn")<br />Odstranit sloupce|![Ikona dotazu zastavení](../../extensibility/ux-guidelines/media/0405-09_stopquery.png "0405 09_StopQuery")<br />Ukončit dotaz|![Ikona offline připojení](../../extensibility/ux-guidelines/media/0405-10_connectionoffline.png "0405 10_ConnectionOffline")<br />Připojení do offline režimu|  
  
 Modrá se použije pro neutrální akce modifikátory nejčastěji reprezentována jako dvojice šipek, jako jsou "Otevřený" tlačítko Další. "Předchozí", "Importovat" a "Export".  
  
|||||  
|-|-|-|-|  
|![Přejděte na ikonu pole](../../extensibility/ux-guidelines/media/0405-11_gotofield.png "0405 11_GoToField")<br />Přejděte na pole|![Zpracovat v dávce Kontrola & č. 45; v ikonu](../../extensibility/ux-guidelines/media/0405-12_batchedcheckin.png "0405 12_BatchedCheckIn")<br />Dávkové vrácení se změnami|![Ikona editor adresu](../../extensibility/ux-guidelines/media/0405-13_addresseditor.png "0405 13_AddressEditor")<br />Adresa editoru|![Ikona editor přidružení](../../extensibility/ux-guidelines/media/0405-14_associationeditor.png "0405 14_AssociationEditor")<br />Přidružení editoru|  
  
 Tmavý zlatý slouží především pro modifikátor "New".  
  
|||||  
|-|-|-|-|  
|![Ikona nového projektu](../../extensibility/ux-guidelines/media/0405-15_newproject.png "0405 15_NewProject")<br />Nový projekt|![Vytvořit novou ikonu grafu](../../extensibility/ux-guidelines/media/0405-16_createnewgraph.png "0405 16_CreateNewGraph")<br />Vytvořit nový graf|![Ikona testu nové jednotky](../../extensibility/ux-guidelines/media/0405-17_newunittest.png "0405 17_NewUnitTest")<br />Nové testování částí|![Ikony nové položky seznamu](../../extensibility/ux-guidelines/media/0405-18_newlistitem.png "0405 18_NewListItem")<br />Nové položky seznamu|  
  
#### <a name="special-cases"></a>Zvláštní případy  
 Ve zvláštních případech modifikátor barevnou akce lze nezávisle jako samostatná ikona. Barva použitá pro ikonu odráží akce, které je na ikonu přidružena. Toto použití je omezeno na malou podmnožinu ikony, včetně:  
  
||||||  
|-|-|-|-|-|  
|![Spustit ikonu](../../extensibility/ux-guidelines/media/0405-03_actionmodifierrun.png "0405 03_ActionModifierRun")<br />Spustit|![Ikona zastavení](../../extensibility/ux-guidelines/media/0405-19_stop.png "0405 19_Stop")<br />Zastavit|![Odstranit ikonu](../../extensibility/ux-guidelines/media/0405-20_delete.png "0405 20_Delete")<br />Odstranit|![Ikonu Uložit](../../extensibility/ux-guidelines/media/0405-21_save.png "0405 21_Save")<br />Uložit|![Přejděte zpět ikonu](../../extensibility/ux-guidelines/media/0405-22_navigateback.png "0405 22_NavigateBack")<br />Přejděte zpět|  
  
### <a name="code-hierarchy-palette"></a>Kód hierarchie palety  
  
#### <a name="folder"></a>Folder  
  
|Použití|Název|Hodnota (všechny motivy)|Vzorníku|Příklad|  
|-----------|----------|--------------------------|------------|-------------|  
|Složky|Folder|DCB67A / 220,182,122|![Vzorníku DCB67A](../../extensibility/ux-guidelines/media/0405_dcb67a.png "0405_DCB67A")|![Barva ikonou složky](../../extensibility/ux-guidelines/media/0405-23_foldercolor.png "0405 23_FolderColor")|  
  
#### <a name="visual-studio-languages"></a>Jazyky Visual Studio  
 Každý běžné jazyky nebo platformy, které jsou k dispozici v sadě Visual Studio má přidružené barev. Tyto barvy se používají na ikonu základní nebo na modifikátory jazyk, které se zobrazují v pravém horním rohu složené ikony.  
  
|Použití|Název|Hodnota (všechny motivy)|Vzorníku|  
|-----------|----------|--------------------------|------------|  
|ASP, HTML, WPF|Modrá ASP HTML WPF|0095D 7 / 0,149,215|![Vzorníku 0095 D 7](../../extensibility/ux-guidelines/media/0405_0096d7.png "0405_0096D7")|  
|C++|CPP Fialová|9B4F96 / 155,79,150|![Vzorníku 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|C#|CS zelený (zelený VS akce)|388A34 / 56,138,52|![Vzorníku 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|CSS|Red šablon stylů CSS|BD1E2D / 189,30,45|![Vzorníku BD1E2D](../../extensibility/ux-guidelines/media/0405_bd1e2d.png "0405_BD1E2D")|  
|F#|Fialová služby FS|672878 / 103,40,120|![Vzorníku 672878](../../extensibility/ux-guidelines/media/0405_672878.png "0405_672878")|  
|JavaScript|JS oranžová|F16421 / 241,100,33|![Vzorníku F16421](../../extensibility/ux-guidelines/media/0405_f16421.png "0405_F16421")|  
|JAZYKA VISUAL BASIC|VB Blue (modrá VS akce)|00539C / 0,83,156|![Vzorníku 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|TypeScript|Oranžová TS|E04C06 / 224,76,6|![Vzorníku E04C06](../../extensibility/ux-guidelines/media/0405_e04c06.png "0405_E04C06")|  
|Python|PY zelená|879636 / 135,150,54|![Vzorníku 879636](../../extensibility/ux-guidelines/media/0405_879636.png "0405_879636")|  
  
##### <a name="examples-of-icons-with-language-modifiers"></a>Příklady ikony s modifikátory jazyk  
  
|||||||  
|-|-|-|-|-|-|  
|![Ikona jazyka Visual Basic](../../extensibility/ux-guidelines/media/0405-25_vb.png "0405 25_VB")<br />JAZYKA VISUAL BASIC|![C &#35; ikona](../../extensibility/ux-guidelines/media/0405-26_csharp.png "0405 26_CSharp")<br />C#|![C & č. 43; & č. 43; ikona](../../extensibility/ux-guidelines/media/0405-27_cplusplus.png "0405 27_CPlusPlus")<br />C++|![Př &#35; ikona](../../extensibility/ux-guidelines/media/0405-28_fsharp.png "0405 28_FSharp")<br />F#|![Ikona JavaScript](../../extensibility/ux-guidelines/media/0405-29_javascript.png "0405 29_JavaScript")<br />JavaScript|![Ikona Python](../../extensibility/ux-guidelines/media/0405-30_python.png "0405 30_Python")<br />Python|  
|![Ikona HTML](../../extensibility/ux-guidelines/media/0405-31_html.png "0405 31_HTML")<br />HTML|![Ikona WPF](../../extensibility/ux-guidelines/media/0405-32_wpf.png "0405 32_WPF")<br />WPF|![Ikona ASP](../../extensibility/ux-guidelines/media/0405-33_asp.png "0405 33_ASP")<br />ASP|![Ikona šablon stylů CSS](../../extensibility/ux-guidelines/media/0405-34_css.png "0405 34_CSS")<br />CSS|![Ikona typeScript](../../extensibility/ux-guidelines/media/0405-35_typescript.png "0405 35_TypeScript")<br />TypeScript||  
  
#### <a name="intellisense"></a>IntelliSense  
 IntelliSense ikony použít výhradní (barevná paleta). Tyto barvy se používají k pomáhají uživatelům rychle rozlišit mezi různé položky v seznamu místní IntelliSense.  
  
|Použití|Název|Hodnota (všechny motivy)|Vzorníku|  
|-----------|----------|--------------------------|------------|  
|Třída, události|Oranžová akce VS|C27D1A / 194,125,26|![Vzorníku C27D1A](../../extensibility/ux-guidelines/media/0405_c27d1a.png "0405_C27D1A")|  
|Metody rozšíření, metoda, modul, delegát|Akce Fialová VS|652D 90 / 101,45,144|![Vzorníku 652D 90](../../extensibility/ux-guidelines/media/0405_652d90.png "0405_652D90")|  
|Pole, položka výčtu, makro, struktura, typ Union hodnoty, operátor, rozhraní|Modrá akce VS|00539C / 0,83,156|![Vzorníku 00539C](../../extensibility/ux-guidelines/media/0405_00539c.png "0405_00539C")|  
|Objekt|Zelená akce VS|388A34 / 56,138,52|![Vzorníku 388A34](../../extensibility/ux-guidelines/media/0405_388a34.png "0405_388A34")|  
|Konstantní, výjimky, položka výčtu, Map, položka mapování, Namespace, šablony, definice typu|Pozadí (VS BG)|424242 / 66,66,66|![Vzorníku 424242](../../extensibility/ux-guidelines/media/0405_424242.png "0405_424242")|  
  
##### <a name="examples-of-intellisense-icons"></a>Příklady ikony IntelliSense  
  
||||||  
|-|-|-|-|-|  
|![Ikonu třídy IntelliSense](../../extensibility/ux-guidelines/media/0405-36_intellisenseclass.png "0405 36_IntelliSenseClass")<br />Třída|![Ikona Soukromá událost IntelliSense](../../extensibility/ux-guidelines/media/0405-37_intellisenseprivateevent.png "0405 37_IntelliSensePrivateEvent")<br />Privátní událostí|![Ikona delegáta IntelliSense](../../extensibility/ux-guidelines/media/0405-38_intellisensedelegate.png "0405 38_IntelliSenseDelegate")<br />Delegát|![Ikona friend metoda IntelliSense](../../extensibility/ux-guidelines/media/0405-39_intellisensemethodfriend.png "0405 39_IntelliSenseMethodFriend")<br />Friend – metoda|![Ikona pole](../../extensibility/ux-guidelines/media/0405-40_field.png "0405 40_Field")<br />Pole|  
|![IntelliSense chráněné ikony položky výčtu](../../extensibility/ux-guidelines/media/0405-41_intellisenseprotectedenumitem.png "0405 41_IntelliSenseProtectedEnumItem")<br />Chráněné položky výčtu|![Ikona objektů IntelliSense](../../extensibility/ux-guidelines/media/0405-42_intellisenseobject.png "0405 42_IntelliSenseObject")<br />Objekt|![Ikona šablony IntelliSense](../../extensibility/ux-guidelines/media/0405-43_intellisensetemplate.png "0405 43_IntelliSenseTemplate")<br />Šablony|![Ikona zástupce výjimka IntelliSense](../../extensibility/ux-guidelines/media/0405-44_intellisenseexceptionshortcut.png "0405 44_IntelliSenseExceptionShortcut")<br />Zástupce výjimky||  
  
### <a name="notifications"></a>Oznámení  
 Oznámení v sadě Visual Studio jsou slouží k určení stavu. Palety oznámení používá následující čtyři barvy, jakož i možností výplně černé nebo bílé popředí, můžete definovat oznámení s následujícími úrovněmi stavu.  
  
|Použití|Název|Hodnota (všechny motivy)|Vzorníku|  
|-----------|----------|--------------------------|------------|  
|Stav: neutrální|Oznámení Blue (modrá VS)|1BA1E2 / 27,161,226|![Vzorníku 1BA1E2](../../extensibility/ux-guidelines/media/0405_1ba1e2.png "0405_1BA1E2")|  
|Stav: kladné|Oznámení zelený (VS zelený)|339933 / 51,153,51|![Vzorníku 339933](../../extensibility/ux-guidelines/media/0405_339933.png "0405_339933")|  
|Stav: záporná|Oznámení červený (VS červený)|E51400 / 229,20,0|![Vzorníku E51400](../../extensibility/ux-guidelines/media/0405_e51400.png "0405_E51400")|  
|Stav: upozornění|Oznámení žlutý (VS oranžová)|FFCC00 / 255,204,0|![Vzorníku FFCC00](../../extensibility/ux-guidelines/media/0405_ffcc00.png "0405_FFCC00")|  
|Výplně popředí|Oznámení černé (černé)|000000 / 0,0,0|![Vzorníku &#35; 000000](../../extensibility/ux-guidelines/media/0405_000000.png "0405_000000")|  
|Výplně popředí|Oznámení prázdné (prázdný)|FFFFFF / 255,255,255|![Vzorníku FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
  
#### <a name="examples-of-notification-icons"></a>Příklady ikony oznámení  
  
|||||  
|-|-|-|-|  
|![Ikona upozornění](../../extensibility/ux-guidelines/media/0405-45_alert.png "0405 45_Alert")<br />Výstrahy|![Ikona upozornění](../../extensibility/ux-guidelines/media/0405-48_warning.png "0405 48_Warning")<br />Upozornění|![Dokončení ikonu](../../extensibility/ux-guidelines/media/0405-46_complete.png "0405 46_Complete")<br />Dokončení|![Ikona zastavení](../../extensibility/ux-guidelines/media/0405-47_stop.png "0405 47_Stop")<br />Zastavit|  
  
### <a name="visual-studio-online"></a>Visual Studio Online  
 Obecně platí Visual Studio Online se skládá z funkcí, které jsou hostované v prohlížeči. Barva se liší v různých prostředích, ale styl zůstává stejná.  
  
|Skupina|Použití|Název|Hodnota (všechny motivy)|Vzorníku|  
|-----------|-----------|----------|--------------------------|------------|  
|SADY TFS|Pozadí|TFSO BG|656565/ 101, 101, 101|![Vzorníku 656565](../../extensibility/ux-guidelines/media/0405_656565.png "0405_656565")|  
|SADY TFS|Obrys|TFSO OUT|FFFFFF / 255, 255, 255|![Vzorníku FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Napa|Pozadí|prázdné|FFFFFF / 255, 255, 255|![Vzorníku FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|Monaco|Pozadí|prázdné|FFFFFF / 255, 255, 255|![Vzorníku FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|Pozadí|prázdné|FFFFFF / 255, 255, 255|![Vzorníku FFFFFF](../../extensibility/ux-guidelines/media/0405_ffffff.png "0405_FFFFFF")|  
|F12|Normální|F12 Grey_Primary|555555 / 85, 85, 85|![Vzorníku 555555](../../extensibility/ux-guidelines/media/0405_555555.png "0405_555555")|  
|F12|Pozastavte ukazatel myši|F12 Blue_Hover|2279BF / 34,121,191|![Vzorníku 2279BF](../../extensibility/ux-guidelines/media/0405_2279bf.png "0405_2279BF")|  
|F12|zakázáno|F12 LtGrey_Disabled|ABABAC / 171,171,172|![Vzorníku ABABAC](../../extensibility/ux-guidelines/media/0405_ababac.png "0405_ABABAC")|  
|F12|Najeďte pozadí|Najeďte bg|D9EBF7 / 217,235,247|![Vzorníku D9EBF7](../../extensibility/ux-guidelines/media/0405_d9ebf7.png "0405_D9EBF7")|  
|F12|Při stisknutí tlačítka pozadí|Při stisknutí tlačítka bg|B2D7F0 / 178,215,240|![Vzorníku B2D7F0](../../extensibility/ux-guidelines/media/0405_b2d7f0.png "0405_B2D7F0")|  
|F12|Obrys|VS OUT|F6F6F6 / 246,246,246|![Vzorníku F6F6F6](../../extensibility/ux-guidelines/media/0405_f6f6f6.png "0405_F6F6F6")|  
|F12|Informace o|Informace o|00BCF2 / 0,188,242|![Vzorníku 00BCF2](../../extensibility/ux-guidelines/media/0405_00bcf2.png "0405_00BCF2")|  
|F12|Upozornění|Upozornění|F28300 / 242,131,0|![Vzorníku F28300](../../extensibility/ux-guidelines/media/0405_f28300.png "0405_F28300")|  
|F12|Chyba / záporná|Error_Negative|E81123 / 232,17,35|![Vzorníku E81123](../../extensibility/ux-guidelines/media/0405_e81123.png "0405_E81123")|  
|F12|Start / kladné|Start_Positive|009E49 / 0,158,73|![Vzorníku 009E49](../../extensibility/ux-guidelines/media/0405_009e49.png "0405_009E49")|  
|F12|Typ ukončení|Typ ukončení|9B4F96 / 155,79,150|![Vzorníku 9B4F96](../../extensibility/ux-guidelines/media/0405_9b4f96.png "0405_9B4F96")|  
|F12|Označit událostí|Označit událostí|A51F00 / 165,31,0|![Vzorníku A51F00](../../extensibility/ux-guidelines/media/0405_a51f00.png "0405_A51F00")|  
|F12|Značky uživatele|Značky uživatele|F16220 / 241,98,32|![Vzorníku F16220](../../extensibility/ux-guidelines/media/0405_f16220.png "0405_F16220")|  
  
#### <a name="examples-of-visual-studio-online-icons"></a>Příklady Visual Studio Online ikony  
  
|Online sady TFS||||  
|----------------|-|-|-|  
|![Ikona sady TFS Online team](../../extensibility/ux-guidelines/media/0405-49_tfsonlineteam.png "0405 49_TFSOnlineTeam")<br />Tým online|![Informační ikona, která TFS](../../extensibility/ux-guidelines/media/0405-50_tfsinformation.png "0405 50_TFSInformation")<br />Informace o|![Ikona historie TFS](../../extensibility/ux-guidelines/media/0405-51_tfshistory.png "0405 51_TFSHistory")<br />Historie|![Ikona větve sady TFS](../../extensibility/ux-guidelines/media/0405-52_tfsbranch.png "0405 52_TFSBranch")<br />Větvení.|  
  
|Napa||||  
|----------|-|-|-|  
|![Ikona obsahu Napa](../../extensibility/ux-guidelines/media/0405-53_napacontent.png "0405 53_NapaContent")<br />Obsah|![Ikona e-mailu office Napa](../../extensibility/ux-guidelines/media/0405-54_napaofficemail.png "0405 54_NapaOfficeMail")<br />Office e-mailu|![Ikona Sharepointu Napa](../../extensibility/ux-guidelines/media/0405-55_napasharepoint.png "0405 55_NapaSharePoint")<br />SharePoint|![Ikona podokno úlohy Napa](../../extensibility/ux-guidelines/media/0405-56_napataskpane.png "0405 56_NapaTaskPane")<br />Podokna úloh|  
  
|Monaco||||  
|------------|-|-|-|  
|![Ikona Soubory Monaco](../../extensibility/ux-guidelines/media/0405-57_monacofiles.png "0405 57_MonacoFiles")<br />Soubory|![Ikona Monaco Git](../../extensibility/ux-guidelines/media/0405-58_monacogit.png "0405 58_MonacoGit")<br />Git|![Ikona vyhledávání Monaco](../../extensibility/ux-guidelines/media/0405-59_monacosearch.png "0405 59_MonacoSearch")<br />Hledat|![Ikona textu Monaco](../../extensibility/ux-guidelines/media/0405-60_monacotext.png "0405 60_MonacoText")<br />Text|  
  
|F12|||  
|---------|-|-|  
|![Ikona velmi kód F12](../../extensibility/ux-guidelines/media/0405-61_f12prettycode.png "0405 61_F12PrettyCode")<br />Velmi kódu|![Ikona upozornění F12](../../extensibility/ux-guidelines/media/0405-62_f12warning.png "0405 62_F12Warning")<br />Upozornění|![Ikona F12 emulovat](../../extensibility/ux-guidelines/media/0405-63_f12emulate.png "0405 63_F12Emulate")<br />Emulovat|