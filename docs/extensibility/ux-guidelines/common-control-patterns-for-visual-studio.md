---
title: "Běžné vzory ovládacích prvků pro sadu Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e893949-6398-42f1-9eab-a8d8c2b7f02d
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ded7ed6dd843a7879100704276766bfcb528b6f7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="common-control-patterns-for-visual-studio"></a>Běžné vzory ovládacích prvků pro sadu Visual Studio
##  <a name="BKMK_CommonControls"></a>Běžné ovládací prvky  
  
### <a name="overview"></a>Přehled  
Běžné ovládací prvky tvoří většinu uživatelského rozhraní v sadě Visual Studio. Postupujte podle většiny běžných ovládacích prvků používaná v sadě Visual Studio rozhraní [pokyny pro interakci Windows Desktop](https://msdn.microsoft.com/library/windows/desktop/dn742399.aspx). Toto téma je specifické pro Visual Studio a zahrnuje zvláštní situace nebo podrobnosti, které posílení tyto pokyny pro Windows.  
  
#### <a name="common-controls-in-this-topic"></a>Běžné ovládací prvky v tomto tématu  
  
-   [Posuvníky](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_Scrollbars)  
  
-   [Vstupní pole](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_InputFields)  
  
-   [Pole se seznamem a rozevírací seznamy](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ComboBoxesAndDropDowns)  
  
-   [Zaškrtávací políčka](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_CheckBoxes)  
  
-   [Přepínací tlačítka](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_RadioButtons)  
  
-   [Skupiny rámce](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_GroupFrames)  
  
-   [Ovládacích prvků textu](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TextControls)  
  
-   [Tlačítka a hypertextové odkazy](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_ButtonsAndHyperlinks)  
  
-   [Zobrazení stromu](../../extensibility/ux-guidelines/common-control-patterns-for-visual-studio.md#BKMK_TreeViews)  
  
#### <a name="visual-style"></a>Vizuální styl  
První věc vzít v úvahu při styly ovládacích prvků je, jestli ovládací prvky se použije v uživatelském rozhraní motivu. Ovládací prvky v standardní uživatelské rozhraní jsou – motivu uživatelského rozhraní a musí následovat [styl Normální Windows Desktop](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx), což znamená, že nejsou znovu použití šablon a by se měla objevit v jejich výchozí vzhled ovládacího prvku.  
  
-   **Dialogová okna Standard (Nástroje):** není motivu. Si šablonu znovu. Použijte výchozí styl základního ovládacího prvku.  
  
-   **Nástroje systému windows, editory dokumentu, návrhové ploše a motivu dialogová okna:** používat specializované vzhled a motivy pomocí služby barev.  
  
###  <a name="BKMK_Scrollbars"></a>Posuvníky  
 Postupujte podle posuvníky [obecné vzory interakce pro Windows posuvníky](https://msdn.microsoft.com/en-us/library/windows/desktop/bb787527\(v=vs.85\).aspx) Pokud jste se rozšířit o informace o obsahu, jako například v editoru kódu.  
  
###  <a name="BKMK_InputFields"></a>Vstupní pole  
 Chování typické interakce, postupujte podle [Windows Desktop pokyny pro textová pole](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742442\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Vizuální styl  
  
-   Vstupní pole nesmí být navržen tak v dialogových oknech nástroje. Použijte styl základní vnitřní do ovládacího prvku.  
  
-   Motivu vstupní pole by měl použít pouze v motivu dialogová okna a nástroje systému windows.  
  
#### <a name="specialized-interactions"></a>Specializované interakce  
  
-   Pole jen pro čtení budou mít šedé (zakázáno) pozadí ale popředí výchozí (aktivní).  
  
-   Požadované pole by měl mít  **\<požadované >** jako vodoznaky v nich. Nesmí změnit barvu pozadí s výjimkou na velmi zřídka.  
  
-   Chyba ověřování: najdete v části [oznámení a postup pro sadu Visual Studio](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)  
  
-   Vstupní pole by měly mít velikost podle obsahu, není na šířku okna, ve kterém se zobrazují, ani nahodile odpovídat délka dlouho pole, podobně jako cestu. Délka mohlo by to znamenat uživateli omezení, kolik znaků jsou povoleny v poli.  
  
     ![Nesprávný vstupní pole Délka: není pravděpodobné, že název bude tento dlouho. ] (../../extensibility/ux-guidelines/media/0707-01_incorrectinputfieldcontrol.png "0707 01_IncorrectInputFieldControl")<br />Nesprávný vstupní pole Délka: není pravděpodobné, že název bude tento dlouho.
  
     ![Opravte vstupní pole Délka: vstupní pole je možné logicky šířku pro očekávaný obsah. ] (../../extensibility/ux-guidelines/media/0707-02_correctinputfieldcontrol.png "0707 02_CorrectInputFieldControl")<br />Opravte vstupní pole Délka: vstupní pole je možné logicky šířku pro očekávaný obsah.
  
###  <a name="BKMK_ComboBoxesAndDropDowns"></a>Pole se seznamem a rozevírací seznamy  
Chování typické interakce, postupujte podle [Windows Desktop pokyny pro rozevírací seznamy a pole se seznamem](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742404\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Vizuální styl  
  
-   V dialogových oknech nástroj si znovu šablony ovládacího prvku. Použijte styl základní vnitřní do ovládacího prvku.  
  
-   V motivu uživatelského rozhraní, pole se seznamem a rozevírací seznamy podle standardní motivů ovládacích prvků.  
  
#### <a name="layout"></a>Rozložení  
Pole se seznamem a rozevírací seznamy by měly mít velikost podle obsahu, není na šířku okna, ve kterém se zobrazují, ani nahodile odpovídat délka dlouho pole, podobně jako cestu.  
  
![Nesprávný: šířka rozevíracího seznamu je příliš dlouhý pro obsah, který se zobrazí. ] (../../extensibility/ux-guidelines/media/0707-03_incorrectdropdownlayout.png "0707 03_IncorrectDropDownLayout")<br />Nesprávný: šířka rozevíracího seznamu je příliš dlouhý pro obsah, který se zobrazí.
  
![Správné: z rozevírací nabídky je velikost povolit pro překlad růst, ale není zbytečně dlouhé. ] (../../extensibility/ux-guidelines/media/0707-04_correctdropdownlayout.png "0707 04_CorrectDropDownLayout")<br />Správné: z rozevírací nabídky je velikost povolit pro překlad růst, ale není zbytečně dlouhé. 
  
###  <a name="BKMK_CheckBoxes"></a>Zaškrtávací políčka  
Chování typické interakce, postupujte podle [Windows Desktop pokyny pro zaškrtávací políčka](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742401\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Vizuální styl  
  
-   V dialogových oknech nástroj si znovu šablony ovládacího prvku. Použijte styl základní vnitřní do ovládacího prvku.  
  
-   Zaškrtávací políčka v motivu uživatelského rozhraní, postupujte podle standardní motivů ovládacích prvků.  
  
#### <a name="specialized-interactions"></a>Specializované interakce  
  
-   Interakce se zaškrtávacím políčkem musí nikdy pop – dialogové okno nebo přejděte do jiné oblasti.  
  
-   Zarovnává zaškrtávací políčka se standardními hodnotami prvního řádku textu.  
  
     ![Nesprávný: zaškrtávací políčko je na střed textu. ] (../../extensibility/ux-guidelines/media/0707-05_incorrectcheckboxalign.png "0707 05_IncorrectCheckBoxAlign")<br />Nesprávný: zaškrtávací políčko je na střed textu.
  
     ![Správné: políčko je zarovnán s prvním řádkem textu. ] (../../extensibility/ux-guidelines/media/0707-06_correctcheckboxalign.png "0707 06_CorrectCheckBoxAlign")<br />Správné: políčko je zarovnán s prvním řádkem textu.
  
###  <a name="BKMK_RadioButtons"></a>Přepínací tlačítka  
Chování typické interakce, postupujte podle [Windows Desktop pokyny pro přepínací tlačítka](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742436\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Vizuální styl  
V dialogových oknech nástroj to není styl přepínače. Použijte styl základní vnitřní do ovládacího prvku.  
  
#### <a name="specialized-interactions"></a>Specializované interakce  
Není nutné k použití rámečku skupiny zavřít přepínač volby, pokud je třeba spravovat skupiny rozdíl v úzkou rozložení.  
  
###  <a name="BKMK_GroupFrames"></a>Skupiny rámce  
Chování typické interakce, postupujte podle [Windows Desktop pokyny pro skupiny rámce](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742405\(v=vs.85\).aspx).  
  
#### <a name="visual-style"></a>Vizuální styl  
V dialogových oknech nástroj nemusíte stylů skupiny rámce. Použijte styl základní vnitřní do ovládacího prvku.  
  
#### <a name="layout"></a>Rozložení  
  
-   Není nutné k použití rámečku skupiny zavřít přepínač volby, pokud je třeba spravovat skupiny rozdíl v úzkou rozložení.  
  
-   Nikdy nepoužívejte rámečku skupiny pro jeden ovládací prvek.  
  
-   Někdy se dá použít vodorovné pravítko místo kontejner skupiny rámce.  
  
##  <a name="BKMK_TextControls"></a>Ovládacích prvků textu

### <a name="static-text-fields"></a>Statické textové pole

Statické textové pole prezentuje informace jen pro čtení a nelze ho vybrat uživatelem. Vyhněte se použití pro libovolný text, který uživatel může chtít zkopírujte do schránky. Jen pro čtení statický text však můžete změnit tak, aby odrážely změny ve stavu. V příkladu níže statický text název výstupu pod změny skupiny informace, aby se projevily změny provedené v textovém poli kořenové Namespace nad ním.

Existují dva způsoby, jak zobrazit informace o statický text.

Statický text může být na vlastní, v dialogovém okně bez žádné omezení Pokud nedojde ke konfliktu seskupení. Rozhodněte, pokud jsou navíc řádků pole nezbytně nutné. Příkladem je zobrazení cesty k adresáři části vytvořené skupiny řádku, jak je uvedeno níže:  

![Informace o statický text v ovládacích prvcích text](../../extensibility/ux-guidelines/media/DisplayingStaticText.png "DisplayingStaticText.png")<br />Informace o statický text v ovládacích prvků textu

V dialogovém okně, kde existují další seskupené oblasti a členství ve skupině informace pomohou čitelnost a když můžete oddíl skrytý nebo zobrazí (jako v **vlastnosti – okno** podokno s popisem) nebo chcete být v souladu s podobnou uživatelského rozhraní, Umístěte statický text v poli. Toto pole skupiny by měl být jedno pravidlo a barva `ButtonShadow`:

![Statický text v okně vlastností](../../extensibility/ux-guidelines/media/PropertiesWindow.png "PropertiesWindow.png")<br />Statický text v okně vlastností

### <a name="read-only-text-box"></a>Textového pole určeného jen pro čtení

To umožňuje uživateli vybrat text v rámci pole, ale nikoli pro úpravy. Tato textová pole jsou obrysy označující podle obvyklé 3D hranaté s `ButtonShadow` výplně.

V textovém poli se může stát active (upravovat), když uživatel změní přidruženého ovládacího prvku, jako je kontrola nebo zrušte zaškrtnutí zaškrtávacího políčka nebo výběrem nebo zrušením výběru přepínače. Například v **nástroje &gt; možnosti** stránky je uvedená níž, **domovskou stránku** textového pole stane aktivní, kdy **použít výchozí** zaškrtávací políčko je zaškrtnuté políčko.

![Jen pro čtení textového pole, zobrazující neaktivní a aktivní stavy](../../extensibility/ux-guidelines/media/ReadOnlyTextBox.png "ReadOnlyTextBox.png")<br />Jen pro čtení textového pole, zobrazující neaktivní a aktivní stavy

### <a name="using-text-in-dialogs"></a>Pomocí textu v dialogových oknech

Klíče pokyny pro text v dialogových oknech:

-   Štítky pro textová pole, seznamy a rámce v dialogových oknech unthemed začínat operaci, mají počáteční kapitálové na první slovo a končit dvojtečkou.

    > Postupujte podle ovládacích prvků textu v motivu dialogová okna [Windows desktop UX pokyny](https://msdn.microsoft.com/library/windows/desktop/dn742479.aspx) a nemusí provádět žádné koncové interpunkce, s výjimkou otazníky v odkazy na nápovědu.

-   Štítky pro možnost tlačítka a zaškrtávací políčka začínat se slovesem, počáteční kapitálové na první slovo a mít bez koncové interpunkce.

-   Popisky tlačítek, nabídek, položek nabídky a karty mít počátečních velkých písmen jednotlivých slov (první písmeno velké).

-   Popisek terminologie by měla být v souladu s podobné popisky v další dialogová okna.

-   Pokud je to možné mají zapisovače/editor, zápisu nebo schválit text předtím, než je pak nahlášena vývojáři pro implementaci.

-   Všechny ovládací prvky měli popisky s výjimkou zvláštní okolnosti v které použití tabulátoru je dostačující.
Pomocí textu Pomocník v případě nutnosti.

### <a name="helper-text"></a>Textu Pomocník

Součástí dialogová okna pomoct pochopit účel dialogovém okně uživateli nebo označíte, jakou akci chcete provést. Textu Pomocník měli použít pouze v případě potřeby předejdete zbytečného jednoduché dialogová okna. Dvě varianty textu Pomocník jsou dialogové okno a vodoznaku.

Postupujte podle společné umístění textu Pomocník a vyberete, Představujeme nové oblasti. Běžné scénáře textu Pomocník jsou:

-   Pomocník text v dialogových oknech poskytnout další směr o tom, jak pracovat s komplexní dialogové okno.

-   Vodoznakového textu v prázdný nástroje systému windows nebo dialogová okna vysvětlit, proč je viditelná žádný obsah.

-   Popis podokno, v dolní části, jako **vlastnosti – okno**.

-   Text v editoru prázdný vysvětlit, jakou akci uživatele má trvat Začínáme vodoznaku.
  
### <a name="dialog-helper-text"></a>Dialogové okno Pomocník textu

Návrhář činnost koncového uživatele mohou pomoci určit, kdy je vhodné textu Pomocník. Návrháře můžete definovat, kde se zobrazí textu Pomocník i jeho obecné obsah. Pomoc uživateli můžete zápisu nebo upravit vlastní text.

### <a name="watermarks"></a>Vodoznaky

Dialogová okna těžit z mírně odlišné vodoznak pokyny. Vzhledem k tomu, zobrazí se dialogové okno se může vyskytovat zaneprázdněn prováděním mnoho prvky uživatelského rozhraní (popisky, textu nápovědy, tlačítek a jiných ovládacích prvků kontejner s textem), zvláště když těch, které se zobrazí jako černé, vodoznaky výraznější tmavý šedě (VSColor: `ButtonShadow`). Obvykle se zobrazí vodoznak uvnitř ovládacího prvku jako seznam s bílým pozadím (VSColor: `Window`).

-   Text se zobrazí šedě Tmavý (VSColor: `ButtonShadow`). Ale pokud se zobrazí vodoznak na střední šedá nebo jiných stejné barvy (VSColor: `ButtonFace`) na pozadí a je o jeho čitelnost se týkají, přejděte černým textem (VSColor: `WindowText`).

-   Vodoznaky můžete zarovnaný na střed nebo Zarovnané vlevo. Standardní pravidla platí při rozhodování zarovnání. Vodoznak nelze vybrat na pozadí.

![Příklad vodoznakového textu](../../extensibility/ux-guidelines/media/WatermarkTextExample.gif)<br />Příklad vodoznakového textu

### <a name="context-specific-dynamic-text"></a>Konkrétní text (dynamické)

Dynamický text může být použít jeden ze dvou způsobů v dialogovém okně nebo nemodální uživatelského rozhraní: buď jako dynamické štítek, nebo jako dynamický obsah.

-   Dynamické popisek: běžně používá dynamický text je v popisný panely, které nabízejí další informace pro vybranou položku, například v dialogovém okně, který obsahuje seznam elementy a vlastnosti pro tyto elementy zobrazí v mřížce vpravo. Popisek pro mřížku vlastností může být dynamické, takže když je položka vybrána na levé straně, mřížky doprava obsahuje informace o této konkrétní položku.

-   Dynamický text: může být užitečná v případech, kdy je třeba zobrazit konkrétní informace a není obecné informace tímto způsobem, ale byste měli věnovat plánování.

Pokud chcete, aby uživatelé měli možnost Kopírovat informace, které, dynamické text by měl být v jen pro čtení textové pole.
  
##  <a name="BKMK_ButtonsAndHyperlinks"></a>Tlačítka a hypertextové odkazy  
  
### <a name="overview"></a>Přehled  
Ovládací prvky tlačítek a odkaz (hypertextové odkazy) byste měli postupovat podle [základní pokyny Windows Desktop na hypertextové odkazy](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742406\(v=vs.85\).aspx) pro použití, formulaci, změny velikosti a mezer.  
  
### <a name="choosing-between-buttons-and-links"></a>Volba mezi odkazy a tlačítka  
Obvyklým tlačítka byl použit pro akce a rezervováno hypertextové odkazy pro navigaci. Tlačítka lze ve všech případech, ale role odkazy rozšířila v sadě Visual Studio, aby odkazy a tlačítka více zaměňovat za některých podmínek.  
  
Kdy použít příkazová tlačítka:  
  
-   Primární příkazy  
  
-   Zobrazení systému windows slouží k shromažďování vstupu nebo volby, a to i v případě, že jsou sekundární příkazy  
  
-   Škodlivý nebo nevratná akce  
  
-   Tlačítka závazků v průvodci a toky stránky  
  
Vyhněte se příkazová tlačítka v panelech nástrojů, nebo pokud potřebujete více než dva slova pro popisek. Odkazy mohou mít delší popisky.  
  
 Kdy použít odkazy:  
  
-   Navigace do jiného okna, dokumentu nebo webové stránky  
  
-   Situace, které vyžadují delší popisek nebo krátkou větu k popisu záměr akce  
  
-   Úzkou prostory, kde by tlačítko zahlcovat uživatelského rozhraní, za předpokladu, že akce není škodlivý nebo nevratné  
  
-   Deaktivace zdroje, výrazná sekundární příkazy v situacích, kde existuje mnoho příkazů  
  
#### <a name="examples"></a>Příklady  
![Příkaz propojení použitých v informačním panelu následující stavovou zprávu](../../extensibility/ux-guidelines/media/070703-01_commandlinkinfobar.png "070703 01_CommandLinkInfobar")<br />Příkaz propojení použitých v informačním panelu následující stavovou zprávu
  
![Propojení použitých v automaticky otevřeném okně Codelensu](../../extensibility/ux-guidelines/media/070703-02_linksincodelens.png "070703 02_LinksInCodeLens")<br />Propojení použitých v automaticky otevřeném okně Codelensu
  
![Použít pro sekundární příkazy, kde by tlačítka přitahují pozornost příliš mnoho odkazů](../../extensibility/ux-guidelines/media/070703-03_linksassecondarycommands.png "070703 03_LinksAsSecondaryCommands")<br />Použít pro sekundární příkazy, kde by tlačítka přitahují pozornost příliš mnoho odkazů
  
### <a name="common-buttons"></a>Běžné tlačítka  
  
#### <a name="text"></a>Text  
Postupujte podle pokynů zápis v [uživatelského rozhraní text a terminologie](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology).  
  
#### <a name="visual-style"></a>Vizuální styl  
  
##### <a name="standard-unthemed"></a>Standard (unthemed)  
Většina tlačítek v sadě Visual Studio se zobrazí v dialogových oknech nástroje a by neměl být ve. Standardní vzhled tlačítka odrážejí podle operačního systému.  
  
##### <a name="themed"></a>Motivu  
V některých případech mohou být použity tlačítka v rámci stylem uživatelského rozhraní a tyto přepínače musí být ve správně. V tématu [v dialogových oknech](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs) informace o tematické ovládací prvky.  
  
### <a name="special-buttons"></a>Speciální tlačítka  
  
#### <a name="browse-buttons"></a>Procházet... tlačítka  
**[Procházet...]**  tlačítka se používají v mřížky, dialogová okna a nástroje systému windows a další nemodální elementy uživatelského rozhraní. Zobrazené výběr, který pomáhá uživatele při vyplňování hodnotu do ovládacího prvku. Existují dvě varianty toto tlačítko, dlouhé a krátké.  
  
![Tlačítko dlouhá [Procházet...]](../../extensibility/ux-guidelines/media/070703-04_browselong.gif "070703 04_BrowseLong")<br />Tlačítko dlouhá [Procházet...]
  
![Tlačítko jen třemi tečkami krátké [...]](../../extensibility/ux-guidelines/media/070703-05_browseshort.gif "070703 05_BrowseShort")<br />Tlačítko jen třemi tečkami krátké [...]
  
Kdy použít jen třemi tečkami krátké tlačítko:  
  
-   Pokud existuje více než jeden dlouhý **[Procházet...]**  tlačítka v dialogovém okně, jako když povolit několik polí pro procházení. Použít krátké **[...]**  tlačítko pro každou předejdete matoucí přístupové klíče vytvořené v této situaci (**& Procházet** a **B & ocházet** v dialogovém okně stejné).  
  
-   V dialogu úzkou, nebo když neexistuje žádné přiměřené místo, kam umístit tlačítko dlouho.  
  
-   Je-li na tlačítko se zobrazí v ovládacím prvku mřížky.  
  
Pokyny k používání tlačítko:  
  
-   Nepoužívejte přístupový klíč. K přístupu pomocí klávesnice, musí uživatel kartě z ovládacího prvku přiléhající. Zajistěte, aby pořadí tak, aby žádné tlačítko pro procházení spadá ihned po pole se vyplní. Nikdy nepoužívejte podtržítkem níže prvního období.  
  
-   Nastavte Microsoft Active Accessibility (MSAA) **název** vlastnost **Procházet...**  (včetně se třemi tečkami), který obrazovky budou uživatelé prohlížet ho jako "Browse" a není "tečkou teček" nebo "období období období." Pro spravované ovládací prvky, to znamená nastavení **AccessibleName** vlastnost.  
  
-   Nikdy nepoužívejte třemi tečkami **[...]**  tlačítko pro všechno, co s výjimkou procházení akce. Pokud potřebujete například **[nová...]**  tlačítko, ale nemáte dostatek místa pro text, potom dialogové okno musí být přepracovány.  
  
##### <a name="sizing-and-spacing"></a>Nastavení velikosti a mezery  
![Změna velikosti [Procházet...] tlačítka: standardní verzi je 75 x 23 pixelů, zkrácený je 26 x 23 pixelů](../../extensibility/ux-guidelines/media/070703-06_browsesizing.png "070703 06_BrowseSizing")<br />Změna velikosti tlačítka [Procházet...]
  
![Mezera [Procházet...] tlačítka: mezer mezi související ovládací prvek a standardní procházet tlačítko 7 pixelů, mezery mezi související ovládací prvek a krátký procházet tlačítko 5 pixelů](../../extensibility/ux-guidelines/media/070703-07_browsespacing.png "070703 07_BrowseSpacing")<br />Mezery mezi tlačítka [Procházet...]
  
#### <a name="graphical-buttons"></a>Grafické tlačítka  
Některé tlačítka měli vždy použít grafické bitovou kopii a nikdy obsahovat text úspoře místa a zamezit tak lokalizace problémy. To se často používají v jiných řazení seznamy a ovládacích prvků Výběr pole.  
  
> **Poznámka:** uživatelé mají na kartě na tato tlačítka (nejsou žádné přístupové klávesy), takže umístit je rozumný pořadí. Mapy `name` vlastnost tlačítko pro akci, která trvá tak, aby čtečky obrazovky správně interpretovat akce tlačítka.  
  
| Funkce | Tlačítko |  
| --- | --- |  
| Přidejte | ![Grafické tlačítko "Přidat"](../../extensibility/ux-guidelines/media/070703-08_buttonadd.png "070703 08_ButtonAdd") |
| Odebrat | ![Grafické tlačítko "Odebrat"](../../extensibility/ux-guidelines/media/070703-09_buttonremove.png "070703 09_ButtonRemove") |
| Přidejte všechny | ![Grafické tlačítko "Přidat všechny"](../../extensibility/ux-guidelines/media/070703-10_buttonaddall.png "070703 10_ButtonAddAll") |
| Odeberte všechny | ![Grafické "Odeberte všechny" tlačítko](../../extensibility/ux-guidelines/media/070703-11_buttonremoveall.png "070703 11_ButtonRemoveAll") |
| Přesunout nahoru | ![Grafické tlačítko "Nahoru"](../../extensibility/ux-guidelines/media/070703-12_buttonmoveup.png "070703 12_ButtonMoveUp") |
| Přesunout dolů | ![Grafické tlačítko "Dolů"](../../extensibility/ux-guidelines/media/070703-13_buttonmovedown.png "070703 13_ButtonMoveDown") |
| Odstranit | ![Grafické tlačítko "Odstranit"](../../extensibility/ux-guidelines/media/070703-14_buttondelete.png "070703 14_ButtonDelete") |
  
##### <a name="sizing-and-spacing"></a>Nastavení velikosti a mezery  
Změna velikosti pro grafické tlačítka je stejné jako u zkrácené **[Procházet...]**  tlačítko (26 x 23 pixelů):  
  
![Vzhled obrázek na tlačítko s i bez průhledná barva zobrazující](../../extensibility/ux-guidelines/media/070703-15_graphicalbuttonspacing.png "070703 15_GraphicalButtonSpacing")<br />Vzhled obrázek na tlačítko s i bez průhledná barva zobrazující
  
### <a name="hyperlinks"></a>Hypertextové odkazy  
Hypertextové odkazy jsou skvěle hodí pro akce na základě navigace, například otevření tématu nápovědy, modální dialogové okno nebo průvodce. Pokud hypertextový odkaz se používá pro příkaz, je vždy pro uživatelské rozhraní zobrazeno viditelné a výraznou změnu. Obecně platí akce, které potvrzení akce (jako jsou uložit, zrušit a odstranit) se lépe předávají pomocí tlačítka.  
  
#### <a name="writing-style"></a>Styl psaní  
Postupujte podle [Windows Desktop pokyny pro text v uživatelském rozhraní](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx). Nepoužívejte "Zjistěte více o," "Sdělte mi Další informace o" nebo "Get pomoc s to" frázového. Místo toho fráze text odkazu nápovědy z hlediska primární otázku odpověděli obsah nápovědy. Například "**jak přidat server do Průzkumníka serveru?**"  
  
#### <a name="visual-style"></a>Vizuální styl  
  
-   Hypertextové odkazy měli vždycky používat [služba VSColor Service](../../extensibility/ux-guidelines/colors-and-styling-for-visual-studio.md#BKMK_TheVSColorService). Pokud je navržen tak hypertextový odkaz, není správně, bliká red při active nebo ukazuje barvu po přístupu.  
  
-   Neobsahují podtržení v ovládacím prvku spočívající stavu, není-li odkaz fragment větu v rámci úplné věty, jako v vodoznak.  
  
-   Podtržení by se neměla při přechodu myší. Místo toho zpětnou vazbu pro uživatele, že odkaz je aktivní je změna mírné barvy a příslušný odkaz kurzor.  
  
##  <a name="BKMK_TreeViews"></a>Zobrazení stromu  
  
Zobrazení stromu poskytují způsob, jak uspořádat komplexní uvádí do nadřízených a podřízených skupin. Uživatele můžete rozbalit nebo sbalit nadřazené skupiny odhalit nebo skrytí základní podřízené položky. Poskytnout další akce lze vybrat každou položku v zobrazení stromu.  
  
###  <a name="BKMK_TreeViewVisualStyle"></a>Vizuální styl zobrazení stromu  
  
#### <a name="expanders"></a>Rozšíření, která jsou  
Ovládací prvky stromového zobrazení by měl odpovídat expander návrh používá systém Windows a Visual Studio. Každý uzel používá ovládací prvek expander odhalit nebo skryjete základní položky. Použití ovládacího prvku expander poskytuje konzistence pro uživatele, kteří setkat jiného stromu zobrazení v systému Windows Server a Visual Studio.  
  
![Správné: správné styl stromovém zobrazení pomocí ovládacího prvku expander](../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705 1_TreeViewCorrect")<br />Správné: správné styl stromovém zobrazení pomocí ovládacího prvku expander
  
![Nesprávný: nesprávné styl stromovém zobrazení](../../extensibility/ux-guidelines/media/070705-2_treeviewincorrect1.png "070705 2_TreeViewIncorrect1")<br />Nesprávný: nesprávné styl stromovém zobrazení
  
#### <a name="selection"></a>Výběr  
Pokud uzel je vybraný ve stromovém zobrazení, by měl zvýraznění rozšíření na celou šířku ovládacího prvku zobrazení stromu. Díky tomu mohou uživatelé jasně identifikovat které položku vyberou. Výběr barvy by měla odpovídat aktuální motiv sady Visual Studio.  
  
![Správné: zvýraznění vybraného uzlu vyhovuje celou šířku ovládacího prvku zobrazení stromu. ] (../../extensibility/ux-guidelines/media/070705-1_treeviewcorrect.png "070705 1_TreeViewCorrect")<br />Správné: zvýraznění vybraného uzlu vyhovuje celou šířku ovládacího prvku zobrazení stromu.
  
![Nesprávný: zvýraznění vybraného uzlu nevejde celou šířku ovládacího prvku zobrazení stromu. ] (../../extensibility/ux-guidelines/media/070705-3_treeviewincorrect2.png "070705 3_TreeViewIncorrect2")<br />Nesprávný: zvýraznění vybraného uzlu nevejde celou šířku ovládacího prvku zobrazení stromu.
  
#### <a name="icons"></a>Ikony  
Ikony by měl použít v ovládací prvky zobrazení stromu jen v případě jejich pomoci při identifikaci vizuálně rozdíly mezi položkami. Obecně platí ikony by měl použít pouze v heterogenní seznamy, ve kterých ikony přenosu informací k odlišení typů elementů. V seznamu homogenní pomocí ikony, často se dají považovat za šumu a je nutno. Ikona skupiny (nadřazené) v takovém případě můžete předání typu položky v něm. Výjimka, která má toto pravidlo by Pokud ikonu dynamické a slouží k označení stavu.  
  
#### <a name="scroll-bars"></a>Posuvníky  
Posuvníky by být vždy skrytý, pokud se obsah vejde do ovládacího prvku zobrazení stromu. Je přijatelné pro posuvníky být skrytý nebo poloprůhledné ve posuvného okna a zobrazí, když má právě fokus, okno se stromovým zobrazením a při přechodu stromu zobrazit sám sebe.  
  
![Protože obsah překročil omezení stromové zobrazení, zobrazí se i svislého a vodorovného posuvníky. ] (../../extensibility/ux-guidelines/media/070705-4_scrollbars.png "070705 4_Scrollbars")<br />Protože obsah překročil omezení stromové zobrazení, zobrazí se i svislého a vodorovného posuvníky.
  
###  <a name="BKMK_TreeViewInteractions"></a>Interakce zobrazení stromu  
  
#### <a name="context-menus"></a>Kontextové nabídky  
Zobrazení uzlu stromu může odhalit dílčí možnosti v kontextové nabídce. Obvykle k tomu dochází, když uživatel má klepli pravým tlačítkem myši položku nebo stisknutím klávesy nabídky na klávesnici Windows obsahující vybrané položky. Je důležité, aby uzlu získá fokus a je vybraná. To pomáhá identifikovat které položku podnabídky patří do uživatele.  
  
![Nebyla vybrána položka, která se má generovat zaměření kontextové nabídky zvýšení upozornit uživatele, která položka. ] (../../extensibility/ux-guidelines/media/070705-5_contextmenu.png "070705 5_ContextMenu")<br />Nebyla vybrána položka, která se má generovat zaměření kontextové nabídky zvýšení upozornit uživatele, která položka.
  
#### <a name="keyboard"></a>Klávesnice  
Zobrazení stromu by měl poskytovat možnost vybrat položky a rozbalit nebo sbalit uzly pomocí klávesnice. Tím se zajistí, že splňuje navigační naše požadavky na usnadnění přístupu.  
  
##### <a name="tree-view-control"></a>Ovládací prvek stromu  
Ovládací prvky stromů Visual Studio postupujte podle běžné navigační klávesové:  
  
-   **Šipku nahoru:** vyberte položky přesunutím do stromu  
  
-   **Šipku dolů:** přesunutím hlouběji ve stromové struktuře vyberte položky  
  
-   **Šipka doprava:** rozbalte uzel ve stromu  
  
-   **Šipka doleva:** Sbalit uzel ve stromu  
  
-   **Zadejte klíč:** iniciovat, načíst, spustit vybranou položku  
  
##### <a name="trid-tree-view-and-grid-view"></a>Trid (stromové zobrazení a zobrazení mřížky)  
Ovládací prvek trid je komplexní ovládací prvek, který obsahuje stromové zobrazení v mřížce. Rozbalení, sbalení a procházení stromu by měly dodržovat stejné příkazy klávesnice jako stromové zobrazení, s těmito přídavky:  
  
-   **Šipka doprava:** rozbalte uzel. Po rozbalení uzlu se by měly pokračovat, přejdete na nejbližší sloupec na pravé straně. Na konci řádku by se měla zastavit navigace.  
  
-   **Karta:** Navigates na buňku nejbližší na pravé straně.  Na konci řádku navigační pokračuje na další řádek.  
  
-   **Shift + Tab:** Navigates na buňku nejbližší na levé straně.  Na začátku řádku, i nadále navigační buňky nejvíce vpravo v předchozím řádku.  
  
![Ovládací prvek trid v sadě Visual Studio](../../extensibility/ux-guidelines/media/070705-6_trid.png "070705 6_Trid")<br />Ovládací prvek trid v sadě Visual Studio