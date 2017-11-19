---
title: "Návrh tabulky příkaz XML (. Soubory Vsct) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: VSCT files, designing
ms.assetid: bb87a322-bac4-4258-92bc-9a876f05d653
caps.latest.revision: "27"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ca277abe07ffe843ed3f4106615796340f5367a4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="designing-xml-command-table-vsct-files"></a>Návrh tabulky příkaz XML (. Soubory Vsct)
Soubor XML příkaz tabulky (.vsct) popisuje rozložení a vzhled příkaz položky pro VSPackage. Příkaz položky zahrnují tlačítka, pole se seznamem, nabídek, panely nástrojů a skupiny příkaz položek. Toto téma popisuje XML příkaz tabulky souborů, jejich vlivu příkaz položek a nabídek a postup jejich vytvoření.  
  
## <a name="commands-menus-groups-and-the-vsct-file"></a>Příkazy, nabídek, skupiny a soubor .vsct  
 .vsct soubory jsou uspořádány podle příkazy nabídek a příkaz skupiny. Značky XML v souboru .vsct představují těchto položek spolu s další přidružené položky například příkazová tlačítka, příkaz umístění a rastrové obrázky.  
  
 Při vytváření nové VSPackage spuštěním [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] balíček šablony, Šablona generuje soubor .vsct nezbytné elementy pro příkaz nabídky, okno nástroje nebo vlastní editor, v závislosti na vybrané položky. Tento soubor .vsct můžete pak upravit tak, aby vyhověli požadavkům konkrétní VSPackage. Příklady, jak upravit soubor .vsct najdete v tématu příklady v [rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md).  
  
 Pokud chcete vytvořit nový, prázdný .vsct soubor, najdete v části [postupy: vytvoření. Soubor Vsct](../../extensibility/internals/how-to-create-a-dot-vsct-file.md). Po vytvoření přidáte prvky, atributy a hodnoty XML do souboru k popisu rozložení položky příkaz. Podrobné schématu XML, najdete v článku [referenční dokumentace schématu XML VSCT](../../extensibility/vsct-xml-schema-reference.md).  
  
## <a name="differences-between-ctc-and-vsct-files"></a>Rozdíly mezi soubory .ctc a .vsct  
 Význam za značky XML v souboru .vsct jsou stejné jako ty, teď zastaralé .ctc formát souboru, i když je trochu liší jejich provádění.  
  
-   Nové  **\<extern >** značka je, kde odkazujete jiných souborů .h sestavují, například [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] panelu nástrojů.  
  
-   Při .vsct soubory podpory **/ include** prohlášení, stejně jako soubory .ctc, zahrnuje také novou \< **import >** element. Rozdíl je, **/ include** přináší **všechny** informací, ale \< **import >** přináší v pouze názvy.  
  
-   Zatímco soubory .ctc vyžadují soubor hlaviček, ve kterém můžete definovat preprocesor – direktivy, jedna není požadované pro .vsct soubory. Místo toho umístěte do tabulky symbolů, umístěný ve vaší direktivy  **\<Symbol >** prvky, které jsou umístěné v dolní části souboru .vsct.  
  
-   Funkce souborů .vsct  **\<Poznámky >** značku, která umožňuje vložit jakékoli informace, jako například poznámky nebo i obrázky.  
  
-   Hodnoty se uloží jako atributy položky.  
  
-   Příkaz příznaky můžete uložené jednotlivě nebo skládaný.  IntelliSense, ale na skládaný příkaz příznaky nefunguje. Další informace o příkazu příznaky najdete v tématu [Element Command příznak](../../extensibility/command-flag-element.md).  
  
-   Můžete určit více typy, jako je například rozdělení rozevíracích seznamů, kláves atd.  
  
-   Identifikátory GUID nemáte ověřit.  
  
-   Každý prvek uživatelského rozhraní obsahuje řetězec, který reprezentuje text, který se zobrazí s ním.  
  
-   Nadřazené je volitelný. Pokud tento parametr vynechán, se používá hodnota "Skupina neznámý".  
  
-   Ikona argument je volitelný.  
  
-   V části rastrový obrázek – stejně jako .ctc souboru, s tím rozdílem, že nyní můžete určit název souboru prostřednictvím href, který bude mít vyžádat kompilátoru vsct.exe v době kompilace.  
  
-   ResID – původní ID prostředku bitové mapy lze použít a přesto funguje stejně jako soubory .ctc.  
  
-   HRef – nové metodu, která vám umožní určit název souboru pro daný prostředek rastrového obrázku. Předpokládá všechny používají, tak používané části, můžete vynechat. Kompilátor vyhledá první místní prostředky pro soubor, pak na net sdílených složkách a všechny prostředky definované přepínač /I.  
  
-   Keybinding – Už musíte zadat emulátor. Pokud určíte jednu, kompilátor bude předpokládat, že editoru a emulátoru jsou stejné.  
  
-   Keychord – byla vyřazena. Nový formát je Key1, Mod1, Key2, Mod2.  Můžete zadat znak, šestnáctkové nebo VK konstanta.  
  
 Nové kompilátoru, vsct.exe, zkompiluje .ctc i .vsct soubory. Původní ctc.exe kompilátoru, ale bude rozpoznat ani kompilaci .vsct souborů.  
  
 Kompilátor vsct.exe můžete převést existující soubor .cto do souboru .vsct. Další informace o tom najdete v tématu [postupy: vytvoření. Soubor Vsct z existující. Soubor technického ředitele](../../extensibility/internals/how-to-create-a-dot-vsct-file.md#how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file).  
  
## <a name="the-vsct-file-elements"></a>Elementy .vsct souboru  
 Příkaz Tabulka obsahuje následující hierarchie a prvky:  
  
 [CommandTable Element](../../extensibility/commandtable-element.md) – reprezentuje všechny příkazy, skupiny nabídek a přidružené VSPackage nabídky.  
  
 [Extern Element](../../extensibility/extern-element.md) – odkazuje na externí .h soubory můžete sloučit s .vsct souboru.  
  
 [Zahrňte prvek](../../extensibility/include-element.md) – odkazuje na všechny soubory další hlavičky (), které chcete zkompilovat společně s your.vsct souboru. Soubor .vsct může zahrnovat souborů .h obsahující konstanty, které definují příkazy, skupiny nabídek a nabídek, které poskytuje rozhraní IDE nebo jiné VSPackage.  
  
 [Příkazy Element](../../extensibility/commands-element.md) – reprezentuje všechny jednotlivé příkazy, které mohou být provedeny. Každý příkaz obsahuje následující čtyři podřízené prvky:  
  
 [Element nabídky](../../extensibility/menus-element.md) – reprezentuje všechny nabídek a panelů nástrojů v VSPackage. Nabídky jsou kontejnery pro skupiny příkazů.  
  
 [Groups – Element](../../extensibility/groups-element.md) – reprezentuje všechny skupiny v VSPackage. Skupiny jsou kolekce položek jednotlivé příkazy.  
  
 [Tlačítka Element](../../extensibility/buttons-element.md) – reprezentuje všechny příkazová tlačítka a položek nabídky v VSPackage. Tlačítka jsou visual ovládací prvky, které může být spojeno s příkazy.  
  
 [Rastrové obrázky Element](../../extensibility/bitmaps-element.md) – reprezentuje všechny bitmap pro všechny tlačítek v VSPackage. Rastrové obrázky jsou obrázky, které zobrazují vedle nebo na příkazových tlačítkách, v závislosti na kontextu.  
  
 [CommandPlacements Element](../../extensibility/commandplacements-element.md) – označuje dalších místech, kde jednotlivé příkazy by měl být umístěný v nabídkách vaší VSPackage.  
  
 [VisibilityConstraints Element](../../extensibility/visibilityconstraints-element.md) – Určuje, zda příkaz zobrazí na všech dobu, nebo pouze v určitých kontextech, například když se zobrazí dialogové okno konkrétní nebo okna. Nabídek a příkazů, které mají hodnotu pro tento element se zobrazí jenom v případě, že zadaný kontext je aktivní. Výchozí chování je zobrazit příkaz za všech okolností.  
  
 [Element klíčových vazeb](../../extensibility/keybindings-element.md) – určuje žádné vazeb klíče pro příkazy. To znamená, jeden nebo více klíčů kombinace, které musí být stisknutí ke spuštění příkazu, jako například **CTRL + S**.  
  
 [UsedCommands Element](../../extensibility/usedcommands-element.md) – Informs [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí, i když zadaný příkaz je implementována jiným kódem, pokud je aktuální VSPackage aktivní, poskytuje implementaci příkazu.  
  
 `Symbols Element`– Obsahuje názvy symbolů a identifikátory GUID pro všechny vaše příkazy v balíčku.  
  
## <a name="vsct-file-design-guidelines"></a>. Pokyny pro návrh Vsct souboru  
 Úspěšně navrhovat soubor .vsct, postupujte podle následujících pokynů.  
  
-   Příkazy lze umístit pouze do skupin, skupiny lze umístit pouze do nabídky a nabídky lze umístit pouze do skupin. V prostředí IDE, skupiny nejsou zobrazena pouze nabídek a příkazů nejsou.  
  
-   Dílčích nelze přiřadit přímo k nabídce, ale musí být přiřazen ke skupině, která je zase přiřazená k nabídce.  
  
-   Příkazy, dílčích a skupiny lze přiřadit k jedné skupině vztahy k nadřazeným položkám nebo nabídky pomocí pole nadřazené jejich definující – direktiva.  
  
-   Uspořádání tabulku příkaz výhradně prostřednictvím nadřazené polí v direktivy má důležité omezení. Direktivy jazyka, které definují objektů může trvat argument jen jednu nadřazenou položku.  
  
-   Opětovné použití příkazů, skupiny nebo dílčích vyžaduje použití nové direktiva k vytvoření nové instance objektu s vlastní `GUID:ID` pár.  
  
-   Každý `GUID:ID` pár musí být jedinečný. Opětovné použití příkaz, který má, například byly umístěny v nabídce, panel nástrojů, nebo v místní nabídce jsou zpracována <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní.  
  
-   Příkazy a dílčích můžete také zařadit do několika skupin a skupin lze přiřadit k více nabídek pomocí [příkazy Element](../../extensibility/commands-element.md).  
  
## <a name="vsct-file-notes"></a>. Poznámky k Vsct souboru  
 Pokud provedete změny do souboru .vsct po jak jej zkompilovat a jeho následné uložení do nativní satelitní knihovny DLL, byste měli spustit **devenv.exe/Setup /nosetupvstemplates**. Díky tomuto vynutí VSPackage prostředky zadané v experimentální registru, aby se znovu načíst a interní databáze, která popisuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] znovu sestavit.  
  
 Během vývoje je možné pro více projektů VSPackage vytvořen a zaregistrován v experimentální podregistru, který může vést k matoucí zbytečné soubory v prostředí IDE. Chcete-li odstranit tento problém, můžete obnovit podregistr experimentální výchozí nastavení k odebrání všech registrovaných VSPackages a veškeré změny, které může provedli k prostředí IDE. Pokud chcete resetovat experimentální hive, použijte nástroj CreateExpInstance.exe, která se dodává s Visual Studio SDK. Najdete ho v  
  
 **% PROGRAMFILES (x 86) %\Visual Studio \<verze > SDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe**  
  
 Spusťte nástroj pomocí příkazového řádku **/reset CreateExpInstance**. Mějte na paměti, že tento nástroj odebere z podregistru experimentální všechny registrované VSPackages nejsou obvykle nainstalovány s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření nabídek a příkazů](../../extensibility/extending-menus-and-commands.md)