---
title: Aplikace vzory pro sadu Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 04/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ed68602-4e28-46fe-b39f-f41979b308a2
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 139b51fbf0ede7ea439d2308a0d03afe7ba617ec
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="application-patterns-for-visual-studio"></a>Aplikace vzory pro sadu Visual Studio
##  <a name="BKMK_WindowInteractions"></a>Okno interakce  
  
### <a name="overview"></a>Přehled  
Existují dva typy hlavní okno používá v sadě Visual Studio jsou editory dokumentu a nástroje systému windows. Rare, ale možná, jsou velké nemodální dialogová okna. I když jsou tyto všechny nemodální v prostředí, jejich vzory se zásadně liší. Tato část obsahuje rozdíl mezi dokumentu windows, nástroj windows a nemodální dialogová okna. Modální dialogové okno vzory jsou popsané v [v dialogových oknech](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Dialogs).  
  
### <a name="comparing-window-usage-patterns"></a>Porovnávání vzorce používání oken  
**Zdokumentujte windows** téměř vždy zobrazují v tomto dokumentu dobře. Díky tomu editoru dokumentu "center fáze" uspořádat dodatečná nástroji windows kolem.  
  
A **okno nástroje** se nejčastěji používá zobrazí jako samostatné, menší okna sbalené proti hrany rozhraní IDE. To může být viditelné, skrytá nebo skrytý automaticky. Ale někdy nástroje systému windows jsou uvedené v tomto dokumentu dobře, zrušením zaškrtnutí políčka **stabilní okno nebo umístění** vlastnost v okně. To vede k více nemovitosti, ale také běžné rozhodnutí: Při pokusu o integrovat do sady Visual Studio, musíte rozhodnout, zda má vaše funkce Zobrazit okno nástroje nebo okna dokumentu.  
  
**Nemodální dialogová okna** se nedoporučuje v sadě Visual Studio. Většina nemodální dialogová okna se podle definice plovoucí nástroje systému windows a by měla být implementována tímto způsobem. Nemodální dialogová okna jsou povoleny v případech, kdy by příliš omezení velikosti okna normální nástroj ukotvené na straně prostředí. Také mohou v případech, kdy uživatel by pravděpodobně přesunout dialogu sekundární monitorování.  
  
Vezměte v úvahu pečlivě o jaký typ kontejneru potřebujete. Častá rozhodnutí při použití vzoru pro návrh uživatelského rozhraní jsou v následující tabulce.  
  
||Okna dokumentu.|Okno nástroje|Dialogového okna bez režimu|  
|-|---------------------|-----------------|---------------------|  
| **Pozice** | Vždy umístěný v tomto dokumentu dobře a není ukotvení okrajů rozhraní IDE. Je může být "vyžádána" uvolnit samostatně z hlavní prostředí. | Obecně karta ukotven okrajů integrovaného vývojového prostředí, ale může být vlastní jako plovoucí, skrytý automaticky (odepnuté) nebo dobře ukotven v tomto dokumentu.|Velké plovoucího okna odděleně od rozhraní IDE. |  
| **Potvrdit modelu** | *Zpožděné potvrzení*<br /><br /> Chcete-li uložit data v dokumentu, musí uživatel vydávat **soubor &gt; Uložit**, **uložit jako**, nebo **Uložit vše** příkaz. Okna dokumentu obsahuje koncepci data v něm se "dirtied" pak zapsána do jednoho z uložení příkazy. Při zavírání okna dokumentu, veškerý obsah jsou uloženy na disk nebo ztráty. | *Okamžitou potvrzení*<br /><br /> Neexistuje žádné uložit model. Pro windows nástroj inspector, které pomáhají při úpravě souboru soubor musí být otevřen v editoru aktivní nebo designer a editor nebo designer vlastní uložení. | *Zpožděné nebo okamžitou potvrzení*<br /><br /> Nejčastěji velké dialogového okna bez režimu vyžaduje akce k provedení změn a umožňuje operace "Zrušení", který vrátí zpět všechny změny provedené v rámci relace dialogu.  To odlišuje dialogového okna bez režimu z okna nástroj v tom, že nástroj windows mají vždycky model okamžitou potvrzení. |  
| **Viditelnost** | *Otevřít/vytvořit (soubor) a zavřít*<br /><br /> Otevření okna dokumentu se provádí prostřednictvím otevřením existujícího dokumentu nebo pomocí šablony vytvoříte nový textový dokument. Neexistuje žádné "otevřete \<konkrétní editor >" příkazu. | *Skrýt a zobrazit*<br /><br /> Jednou instancí nástroje systému windows můžete skrytý nebo vidět. Obsah a stavy v rámci okno nástroje zachovat, jestli v zobrazení nebo skrytý. Nástroje systému windows s více instancemi může být uzavřen, stejně jako skrytý. Při zavření okna nástroj s více instancemi se zahodí obsahu a stavu v rámci okno nástroje. | *Spuštění příkazu*<br /><br /> Dialogová okna jsou spouštěny z příkazu založeného na úlohách. |  
| **Instance** | *S více instancemi*<br /><br /> Může být několik editory otevřete ve stejnou dobu a úpravy různých souborů, zatímco některé editory také povolit byl stejný soubor otevřete v editoru více než jeden (pomocí **okno &gt; nové okno** příkaz).<br /><br /> Jeden editor může být úpravy jeden nebo více souborů ve stejnou dobu (Návrhář projektu). | *Jeden nebo více instance*<br /><br /> Obsah změnit podle kontextu (jako vlastnost prohlížeče) nebo nabízená fokus nebo kontextu jiných windows (seznam úkolů, Průzkumník řešení).<br /><br /> Pokud není přesvědčivý důvod k, by měly být přidruženy aktivního okna dokumentu jedné instance a víc instancí nástroje systému windows. | *Jednou instancí* |  
| **Příklady** | **Textové editory**, jako například editor kódu<br /><br /> **Návrh povrchy**, jako jsou formuláře designer nebo prostor pro modelování<br /><br /> **Řízení rozložení podobná dialogová okna**, jako například návrháře manifestu | **Průzkumníku řešení** poskytuje řešení a projekty, které jsou obsažené v řešení<br /><br /> **Průzkumníka serveru** poskytuje hierarchické zobrazení servery a datové připojení, které uživatel vybere možnost otevření v okně. Otevřením objekt z databáze hierarchii, jako je dotaz, otevře se okno dokumentu a umožňuje uživateli upravit dotaz.<br /><br /> **Prohlížeč vlastností** zobrazí vlastnosti pro objekt vybraný buď v okně dokumentu nebo jiné okno nástroje. Vlastnosti jsou uvedené v zobrazení hierarchické tabulky nebo v ovládacích prvcích komplexní jako dialogové okno a umožnit uživatelům nastavit hodnoty pro tyto vlastnosti. | |  
  
##  <a name="BKMK_ToolWindows"></a>Nástroje systému windows  
  
### <a name="overview"></a>Přehled  
Nástroje systému windows podporují pracovní uživatele, které dochází v dokumentu systému windows. Jejich slouží k zobrazení hierarchie, která představuje základní kořenový objekt, který Visual Studio poskytuje a můžete upravit.  
  
Při určování nové okno nástroj v prostředí IDE, měli Autoři:  
  
-   Použijte příslušné úlohy existující okna nástrojů a vytvořit nové s podobnými funkcemi. Nový nástroj windows by se vytvořit pouze, pokud nabízejí výrazně odlišné "tool" nebo funkce, které nelze integrovat do okno podobné nebo vypnutím existujícího okna do přesouvání rozbočovače.  
  
-   Standardní řádku nabídek, použijte v případě potřeby v horní části okna nástroje.  
  
-   Být v souladu s vzory již existuje v jiné nástroje systému windows pro ovládací prvek navigace prezentace a klávesnice.  
  
-   Bylo v souladu s prezentace ovládací prvek v jiné nástroje systému windows.  
  
-   Zviditelníte specifické pro dokument nástroje systému windows automaticky – pokud je to možné, tak, aby se objeví jenom když se aktivuje nadřazené dokumentu.  
  
-   Zkontrolujte, zda obsah okno navigaci pomocí klávesnice (klávesy se šipkami podporu).  
  
#### <a name="tool-window-states"></a>Nástroj okno stavy  
Okna nástrojů Visual Studio mají různé stavy, z nichž některé jsou aktivované uživatele (např. funkce automatického skrytí). Jiné stavy, jako automatické viditelné, povolí nástroj windows, které jsou uvedeny v správný kontext a skrýt, když není potřeba. Celkový počet neobsahuje pět stavy okno nástroje.  
  
-   **Ukotveno připnutý** nástroje systému windows je možné připojit k všechny čtyři strany oblasti dokumentu. V záhlaví okna nástroje se zobrazí ikona připínáčku. Panel nástrojů lze ukotvit vodorovně nebo svisle podél okraje prostředí a jiné nástroje systému windows a může být také propojit kartě.  
  
-   **Skrytý automaticky** jsou Odepnout nástroje systému windows. Okno můžete Vysuňte ze zobrazení, a na kartě (s názvem okno nástroje a jeho ikonu) na okraji oblasti dokumentu. Panel nástrojů snímky se při nastavení ukazatele myši na kartu.  
  
-   **Automaticky viditelná** nástroje systému windows automaticky zobrazí, když jinou částí uživatelského rozhraní, jako je editor, spuštění nebo získá fokus.  
  
-   **Plovoucí** nástroj windows najeďte mimo prostředí IDE. To je užitečné pro více monitorování konfigurace.  
  
-   **Dokumentů s kartami** nástroje systému windows můžete v tomto dokumentu dobře ukotven. To je užitečné pro velké nástrojů, jako je objekt prohlížečem, které potřebují další nemovitosti, než ukotvení hrany rámeček umožňuje.  
  
![Nástroj stavy oken v sadě Visual Studio](../../extensibility/ux-guidelines/media/0702-01_toolwindowstates.png "0702 01_ToolWindowStates")<br />Stavy okno nástroje v sadě Visual Studio
  
#### <a name="single-instance-and-multi-instance"></a>Jednou instancí a s více instancemi  
Nástroje systému windows jsou jednou instancí nebo s více instancemi. Některé jednou instancí nástroje systému windows může být přidružen k okno aktivní dokument při s více instancemi nástroje systému windows není možná. Nástroje systému windows s více instancemi reagovat na **okno &gt; nové okno** příkaz tak, že vytvoříte novou instanci třídy okna. Následující obrázek ukazuje nástroj okno, v němž příkaz nové okno, když je aktivní instance okna:  
  
![Je aktivní okno nástroje povolení příkaz 'nové okno, pokud instance okna](../../extensibility/ux-guidelines/media/0702-02_toolwindowenablingcommand.png "0702 02_ToolWindowEnablingCommand")<br />Povolení příkazu 'nové okno, když je aktivní instance okna okno nástroje  
  
Jednou instancí nástroje systému windows můžete skrytý nebo zobrazený, zatímco s více instancemi nástroje systému windows může být uzavřen, stejně jako skrytý. Všechny systémy windows nástroj lze ukotvit, karta propojené, plovoucí nebo nastavte jako podřízeného okna rozhraní více dokumentů (MDI) (podobně jako do okna dokumentu). Všechny systémy windows nástroj má odpovědět na příslušné okno správy příkazy v nabídce okno:  
  
![Příkazy pro správu v nabídce Visual Studio okna](../../extensibility/ux-guidelines/media/0702-03_windowmanagementcontrols.png "0702 03_WindowManagementControls")<br />Příkazy pro správu v nabídce okna Visual Studio
  
#### <a name="document-specific-tool-windows"></a>Okna nástrojů specifické pro dokument  
Některé nástroje systému windows jsou navrženy pro měnit v závislosti na daný typ souboru. Tyto windows průběžně aktualizovat tak, aby odrážela funkce pro aktivní dokument okna v prostředí IDE.  
  
Příkladem nástroje systému windows, jejichž obsah změnit tak, aby odrážela editoru vybrané jsou sady nástrojů a Osnova dokumentu. Tyto windows zobrazit vodoznak, když je editor má právě fokus, který neposkytuje kontext do okna.  
  
#### <a name="navigable-list-tool-windows"></a>Okna nástrojů navigaci seznamu  
Některé nástroje systému windows zobrazit seznam navigaci položky, které může uživatel zasahovat. V tomto typu časového období by měl vždy existovat zpětnou vazbu pro aktuální položky v seznamu, i když okna je neaktivní. V seznamu má odpovědět na **GoToNextLocation** a **GoToPrevLocation** příkazy také změnou aktuálně vybrané položky v okně  
  
Příkladem navigaci seznamu nástroj windows jsou Průzkumníka řešení a okně Výsledky hledání.  
  
### <a name="tool-window-types"></a>Typy oken nástroj  
  
#### <a name="common-tool-windows-and-their-functions"></a>Běžné nástroje systému windows a jejich funkce

**Hierarchická nástroje systému windows**
| Okno nástroje | Funkce | 
| --- | --- | 
| Průzkumník řešení | Hierarchický strom, který zobrazí seznam dokumenty, které jsou obsažené v projektech, ostatní soubory a položky řešení. Zobrazení položek v rámci projekty je definována balíček, který vlastní typ projektu (například na základě odkaz, na základě adresáře nebo ve smíšeném režimu typy). | 
| zobrazení tříd | Stromové struktuře hierarchie tříd a různé prvky v pracovní sady dokumentů, nezávisle na soubory sami. | 
| Průzkumník serveru | Hierarchická stromové struktury, která zobrazí všechna připojení serverů a dat v řešení. | 
| Osnova dokumentu | Hierarchická struktura aktivní dokument. | 

**Okna nástrojů mřížky**
| Okno nástroje | Funkce | 
| --- | --- | 
| Vlastnosti | Tabulku, která zobrazuje seznam vlastností pro vybraný objekt, spolu s hodnotou výběr upravit tyto vlastnosti. | 
| Seznam úloh | Mřížky, která umožňuje uživatelům vytváření, úpravy nebo odstranění úlohy a komentáře. | 

**Obsahu nástroje systému windows**
| Okno nástroje | Funkce | 
| --- | --- | 
| Nápověda | Okno, které umožňuje uživatelům přístup k různých metod nápovědy z "Jak se dá?" videa, která fórech MSDN. | 
| Dynamické nápovědy | Okno nástroje, který zobrazuje odkazy na témata pro aktuální výběr nápovědy. | 
| prohlížeč objektů | Dva sloupce rámců seznam hierarchické objekt součásti v levém podokně a objektu, vlastnosti a metody v pravém sloupci. | 

**Dialogové okno nástroje systému windows**
| Okno nástroje | Funkce | 
| --- | --- | 
| Najít | Dialogové okno, která umožňuje uživatelům najít nebo najít a nahradit v různých souborů v rámci řešení. |
| Rozšířené hledání | Dialogové okno, která umožňuje uživatelům najít nebo najít a nahradit v různých souborů v rámci řešení. | 

**Jiné nástroje systému windows**
| Okno nástroje | Funkce | 
| --- | --- | 
| Sada nástrojů | Panel nástrojů používaných k ukládání elementy, které budou umístěny na návrhové ploše, zajištění konzistentní zdroje operace přetažení pro všechny návrháře. |
| Úvodní stránka | Uživatele portál pro Visual Studio, s přístupem k informační kanály Novinky pro vývojáře, nápovědy sady Visual Studio a nejnovější projekty. Uživatelé mohou také vytvářet vlastní spuštění stránky tak, že zkopírujete soubor StartPage.xaml z "Common7\IDE\StartPages\" adresář programových souborů sady Visual Studio ke složce StartPages v sadě Visual Studio dokumenty adresář a potom buď upravovat XAML ručně nebo ho otevřít v sadě Visual Studio nebo jiný editor kódu. | 

**Ladicí program nástroje systému windows**
| Okno nástroje | Funkce | 
| --- | --- |
| Automatické hodnoty ||  
| Okamžitou ||  
| Výstup | Ve výstupním okně lze vždy, když máte textovou události nebo stav deklarovat. |  
| Paměť ||  
| Zarážky ||  
| Spuštění ||  
| Dokumenty ||  
| Zásobník volání ||  
| Lokální proměnné ||  
| Sleduje ||  
| Zpětný překlad ||  
| Zaregistruje ||  
| Vlákna ||  
  
##  <a name="BKMK_DocumentEditorConventions"></a>Konvence pro dokumenty editoru  
  
### <a name="document-interactions"></a>Interakce dokumentu  
"Dokumentu také" je největší místa v prostředí IDE a je, kde uživatel obecně se soustředili jejich pozornost dokončení úloh nápomocen dodatečné nástroje systému windows. Editory dokumentu představují základní jednotky práce, kterou uživatel otevře a uloží v sadě Visual Studio. Zachovávají silné představu o výběr vázaný na Průzkumníka řešení nebo jiné windows active hierarchie. Uživatel by mohli a přejděte na jednu z těchto hierarchie windows vědět, kde je obsažena v dokumentu a jeho relace řešení, projekt nebo jiné kořenový objekt poskytovaný balíček Visual Studio.  
  
Úpravy dokumentu vyžaduje konzistentní uživatelské prostředí. Povolit uživatelům zaměřit se na na prováděné úloze místo na okno správy a hledání příkazy, vyberte strategie zobrazení dokumentů, které bude nejlépe vyhovovat uživatelských úloh pro úpravy tohoto typu dokumentu.  
  
#### <a name="common-interactions-for-the-document-well"></a>Běžné interakce dobře dokumentu  
  
-   Udržovat konzistentní interakce model v nejběžnější **nový soubor** a **otevření souboru** dojde.  
  
-   Aktualizujte související funkce v relaci windows a nabídek po otevření okna dokumentu.  
  
-   Příkazy nabídky jsou správně integrovány běžné nabídky jako **upravit**, **formátu**, a **zobrazení** nabídky. Pokud vyžadovat značné množství specializované příkazy jsou k dispozici, můžete vytvořit nové nabídky. Toto nové nabídky by měly jít vidět jenom v případě, že dokument má právě fokus.  
  
-   Možné umístit embedded panelu nástrojů v horní části editoru. Je to vhodnější než nutnosti samostatných nástrojů, který se zobrazí mimo editoru.  
  
-   Vždy udržovat výběr v Průzkumníku řešení nebo podobné aktivní okno hierarchie.  
  
-   Dvojitým kliknutím na dokument v Průzkumníku řešení proveďte stejnou akci, jako **otevřete**.  
  
-   Pokud se dá použít více než jeden editor na typ dokumentu, uživatel byste měli mít k přepsání nebo obnovit výchozí akci na typ daného dokumentu pomocí **otevřít v** dialogové okno kliknutím pravým tlačítkem myši na soubor a výběrem **otevřete S** z místní nabídky.  
  
-   Není dobře sestavení průvodce v dokumentu.  
  
### <a name="user-expectations-for-specific-document-types"></a>Očekávání uživatelů pro určité typy dokumentů  
Existuje několik různých typů základní editory dokumentu a každý má sadu interakce, které jsou konzistentní s ostatními stejného typu.  
  
-   **Textový editor:** editoru kódu, soubory protokolu  
  
-   **Návrhové ploše:** WPF forms návrháře, Windows forms  
  
-   **Dialogové okno stylu editor:** Manifest Návrhář vlastnosti projektu  
  
-   **Návrhář modelů EDM model:** návrháře pracovních postupů, codemap, diagram architektury, postupu  
  
Existují také několik typů jiný editor, které taky používat dokumentu. Při jejich nemáte upravit samotné dokumenty, budou muset postupovat podle standardní interakce pro okna dokumentu.  
  
-   **Sestavy:** IntelliTrace sestavy, technologie Hyper-V sestavě sestav profileru  
  
-   **Řídicí panel:** centrum diagnostiky  
  
#### <a name="text-based-editors"></a>Textové editory  
  
-   Dokument se účastní karta model preview, povolení pro náhled dokumentu bez ho otevřít.  
  
-   Struktura dokument může být reprezentován v rámci časového období doprovodné nástroje, jako je například Osnova dokumentu.  
  
-   IntelliSense (v případě potřeby) budou chovat konzistentně s další editory kódu.  
  
-   Automaticky otevíraná okna nebo usnadnění uživatelského rozhraní postupujte podobné styly a vzory pro existující podobné uživatelské rozhraní, jako je například Codelensu.  
  
-   Zprávy o stavu dokument zobrazí v ovládacím prvku informačním panelu v horní části dokumentu nebo ve stavovém řádku.  
  
-   Uživatel musí být možné přizpůsobit vzhled písma a barev pomocí **nástroje > Možnosti** stránka sdílené písma a barev stránky nebo jeden konkrétní do editoru.  
  
#### <a name="design-surfaces"></a>Návrhové ploše  
  
-   Prázdný Návrhář by měl mít vodoznak na plochu, která určuje, jak začít pracovat.  
  
-   Přepnutí zobrazení mechanismy bude postupovat podle existujících vzory, třeba dvojitým kliknutím otevřete editor kódu nebo karty v rámci okna dokumentu umožňuje interakci s obě podokna.  
  
-   Přidávání elementů na návrhovou plochu, která se má provést pomocí sady nástrojů, pokud okno vysoce konkrétní nástroje, není nutné.  
  
-   Položky na ploše bude postupovat podle modelu konzistentní výběr.  
  
-   Vložené panely nástrojů obsahovat dokumentu specifické příkazy pouze, není běžné příkazy, jako například **Uložit**.  
  
#### <a name="dialog-style-editors"></a>Editory stylu dialogového okna  
  
-   Rozložení ovládacích prvků postupujte podle konvence rozložení normální dialogové okno.  
  
-   Karty v editoru by neměly odpovídat vzhled karty dokumentů, se musí shodovat s jedním z dvě povolené vnitřních karta styly.  
  
-   Uživatelé musí být schopen komunikovat s ovládacích prvků pomocí klávesnice pouze; buď pomocí editoru aktivace a použití tabulátoru prostřednictvím ovládací prvky nebo pomocí standardní klávesové zkratky.  
  
-   Návrhář měli používat běžné uložit model. Žádné celkové uložit nebo tlačítek potvrzení musí být umístěny na povrchu, i když může být vhodné ostatní tlačítka.  
  
#### <a name="model-designers"></a>Model Designer  
  
-   Prázdný Návrhář by měl mít vodoznak na plochu, která určuje, jak začít pracovat.  
  
-   Přidávání elementů na návrhovou plochu, která se má provést pomocí sady nástrojů.  
  
-   Položky na ploše bude postupovat podle modelu konzistentní výběr.  
  
-   Vložené panely nástrojů obsahovat dokumentu specifické příkazy pouze, není běžné příkazy, jako například **Uložit**.  
  
-   Legendy se mohou objevit na povrchu, buď naznačuje výslednou nebo vodoznak.  
  
-   Uživatel musí být možné přizpůsobit vzhled písma/barev pomocí **nástroje > Možnosti** stránka sdílené písma a barev stránky nebo jeden konkrétní do editoru.  
  
#### <a name="reports"></a>Sestavy  
  
-   Sestavy jsou obvykle jen informace a není součástí modelu uložit. Však mohou zahrnovat například odkazy na další relevantní informace nebo oddíly, které rozbalení a sbalení interakce.  
  
-   Většina příkazů na ploše by měl být hypertextové odkazy, není tlačítka.  
  
-   Rozložení by měl obsahovat hlavičku a postupujte podle pokynů rozložení standardní sestavy.  
  
#### <a name="dashboards"></a>Řídicí panely  
  
-   Řídicí panely nemají model interakce sami, ale sloužit jako prostředek k nabízí celou řadu jiných nástrojů.  
  
-   Není součástí modelu uložit.  
  
-   Uživatelé musí být schopen komunikovat s ovládacími prvky pomocí klávesnice, buď pomocí editoru aktivace a stisknutím klávesy tabulátor procházíte ovládací prvky, nebo pomocí standardní klávesové zkratky.  
  
##  <a name="BKMK_Dialogs"></a>Dialogová okna  
  
### <a name="introduction"></a>Úvod  
Dialogová okna v sadě Visual Studio by měl obvykle podporují jedné diskrétní jednotky práce uživatele a potom zrušit.  
  
Pokud zjistíte, je nutné, zobrazí se dialogové okno, máte tři možnosti, v pořadí podle priority:  
  
1.  Integrate váš funkce do jedné sdílené dialogových oken v sadě Visual Studio.  
  
2.  Vlastní dialogové okno pomocí vzoru najít v existující podobné dialogové okno vytvořte.  
  
3.  Vytvořte nový dialog, následující interakce a pokyny pro rozložení.  
  
Tato část popisuje, jak vybrat správný dialogu vzor v rámci pracovních postupů sady Visual Studio a běžné konvence pro dialogové okno návrh.  
  
### <a name="themes"></a>Motivy  
Dialogová okna v sadě Visual Studio, použijte jednu z dvě základní styly:  
  
#### <a name="standard-unthemed"></a>Standard (unthemed)  
Většina dialogová okna jsou nástroj pro standardní dialogová okna a mělo by být unthemed. Nezadávejte běžné ovládací prvky znovu šablony nebo pokusí vytvořit stylizované "moderní" tlačítka nebo ovládací prvky. Ovládací prvky a vzhled chrome, postupujte podle [standardní pokyny pro interakci Windows Desktop pro dialogová okna](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742499\(v=vs.85\).aspx).  
  
#### <a name="themed"></a>Motivu  
Dialogová okna speciální "podpis" může být motivu. Dialogová okna motivu mají odlišné vzhled, který také obsahuje některé speciální interakce vzory přidružené styl. Motiv do dialogu pouze v případě, že splňuje tyto požadavky:  
  
-   Dialogové okno je běžné prostředí, které se vidět a použije často nebo mnoha uživateli (například **nový projekt** dialogové okno.  
  
-   Dialogové okno obsahuje prvky brand viditelného produktu (například **nastavení účtu** dialogové okno).  
  
-   Jako nedílnou součástí větší toku, který obsahuje jiné motivu dialogová okna se zobrazí dialogové okno (například **přidat připojení službě** dialogové okno).  
  
-   Dialogové okno je důležitou součástí prostředí, které hrají roli strategické v povýšení nebo rozlišení verzí produktu.  
  
Při vytváření motivu dialogové okno, použít příslušné prostředí barvy a postupujte podle správné rozložení a interakce vzory. (Viz [rozložení pro sadu Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md).)  
  
### <a name="dialog-design"></a>Dialogové okno návrhu  
Dialogová okna dobře navrženou vzít v úvahu následující prvky:  
  
-   Úlohy uživatele, které není podporována  
  
-   Dialogové okno Styl textu, jazyk a terminologie  
  
-   Ovládací prvek výběru a pravidla týkající se uživatelského rozhraní  
  
-   Zarovnání specifikaci a řízení Visual rozložení  
  
-   Použití klávesnice  
  
#### <a name="content-organization"></a>Uspořádání obsahu  
Zvažte rozdíly mezi tyto základní typy dialogová okna:  
  
-   [Jednoduché dialogová okna](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_SimpleDialogs) ovládacích prvků v jednom okně modální k dispozici. Prezentace mohou zahrnovat variace vzory komplexní ovládacích prvků, včetně výběru pole nebo zobrazí panel ikonu.  
  
-   [Dialogová okna na základě](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_LayeredDialogs) se používají k provádění nejvíce z obrazovky nemovitosti, když jediný uživatelského rozhraní se skládá z několika skupin ovládacích prvků. Dialogovém okně seskupení jsou "vrstvený" prostřednictvím ovládací prvky karet, ovládací prvky pro navigaci seznamu nebo tlačítka tak, aby uživatel může vybrat, které seskupení zobrazíte v každém okamžiku.  
  
-   [Průvodci](../../extensibility/ux-guidelines/application-patterns-for-visual-studio.md#BKMK_Wizards) jsou užitečné pro odkazovat uživatele prostřednictvím logické pořadí kroků směrem k dokončení úlohy. Volbami jsou nabízena v sekvenčních panelů, někdy představení různých pracovních ("větví") závisí na volby provedené v předchozí panelu.  
  
####  <a name="BKMK_SimpleDialogs"></a>Jednoduché dialogová okna  
Jednoduché dialogové okno je prezentace ovládacích prvků do jediného modální okna. Tato prezentace mohou zahrnovat variace vzory komplexní ovládacích prvků, jako je výběr pole. Jednoduché dialogová okna postupujte podle standardní Obecné rozložení a také všechny konkrétní rozložení požadované pro seskupení komplexního ovládacího prvku.
  
![> vytvořit silná název klíče je příklad jednoduchého dialogového okna v sadě Visual Studio. ] (../../extensibility/ux-guidelines/media/0704-01_createstrongnamekey.png "0704 01_CreateStrongNameKey")<br />Vytvořit silná název klíče je příklad jednoduchého dialogového okna v sadě Visual Studio.
  
####  <a name="BKMK_LayeredDialogs"></a>Vrstvený dialogová okna  
Vrstvený dialogová okna zahrnují karty, řídicí panely a embedded stromy. Používají se k maximalizaci nemovitosti, pokud existuje více skupin ovládacích prvků nenabízí jediný uživatelského rozhraní. Seskupování se vrstvu tak, aby uživatel může vybrat, které seskupení zobrazíte v daném okamžiku.  
  
V případě nejjednodušší je mechanismus pro přepínání mezi seskupení ovládacího prvku karta. Nejsou k dispozici několik alternativy. Zobrazit Upřednostňování pořadí a rozvrstvení jak zvolit styl nejvhodnější.  
  
**Nástroje &gt; možnosti** dialogové okno je příkladem vrstveného dialogové okno pomocí vložených stromové struktury:  
  
![Nástroje > Možnosti je příklad vrstveného dialogového okna v sadě Visual Studio. ] (../../extensibility/ux-guidelines/media/0704-02_toolsoptions.png "0704 02_ToolsOptions")<br />Nástroje > Možnosti je příklad vrstveného dialogového okna v sadě Visual Studio.
  
####  <a name="BKMK_Wizards"></a>Průvodci  
Průvodci jsou užitečné pro odkazovat uživatele prostřednictvím logické pořadí kroků v dokončení úlohy. Nabízí řadu možností v sekvenčních panelů a uživatel musí pokračovat prostřednictvím každý krok před pokračováním na další. Jakmile jsou k dispozici dostatečná výchozí hodnoty **Dokončit** tlačítko je k dispozici.  
  
 Modální průvodců se používají pro úlohy, které:  
  
-   Vytvoření větve, kde jsou různé cesty nabízena podle volby uživatele obsahovat  
  
-   Obsahuje závislosti mezi kroky, kde následné kroky jsou závislé na vstup uživatele z předchozích kroků  
  
-   Jsou dostatečně složité, že uživatelské rozhraní se má použít k popisují volby, které nabízí a možné výsledky v jednotlivých kroků  
  
-   Jsou transakcí, vyžadování sadu postup provést v celé jeho šíři potvrzeny všechny změny  
  
### <a name="common-conventions"></a>Běžné konvence  
K dosažení optimálního návrhu a funkce s vaší dialogová okna, postupujte podle těchto konvence na dialogové okno, pozice, standardy, konfigurace ovládacího prvku a zarovnání, uživatelského rozhraní text, záhlaví, ovládací tlačítka a přístupové klíče.  
  
Specifické pro rozložení, naleznete na adrese [rozložení pro sadu Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  
  
#### <a name="size"></a>Velikost  
Dialogová okna měli nevejde se do minimální rozlišení obrazovky 1024 × 768 a počáteční dialogové okno velikost nesmí přesahovat 900 x 700 pixelů. Dialogová okna může být s možností změny velikosti, ale není povinné.  
  
Existují dvě doporučení pro dialogová okna s možností změny velikosti:  
  
1.  Že minimální velikost je definovaný pro dialogové okno, které bude optimalizovat pro ovládací prvek nastavit bez výstřižek a upravte pro přizpůsobení přiměřené lokalizace růstu.  
  
2.  Že velikost škálovat uživatele trvá pro relaci. Například pokud uživatel škáluje dialogové okno pro 150 %, pak dalším spuštění dialogového okna se zobrazí na 150 %.  
  
#### <a name="position"></a>Pozice  
Dialogová okna musí být uvedena na střed v prostředí IDE při prvním spuštění. Poslední pozice bez umožňující změnu velikosti dialogová okna nemusí být jako trvalé, takže se zobrazí zarovnaný na následné spustí. 

Dialogová okna s možností změny velikosti by měla velikost trvalé na následné spustí. S možností změny velikosti modální dialogová okna pozici nepotřebuje natrvalo. Zobrazení je umístěn na střed v prostředí IDE eliminuje možnost zobrazovaných v nepředvídatelným nebo nepoužitelná pozici, pokud došlo ke změně konfigurace uživatele zobrazení dialogového okna. 

Nemodální dialogová okna, které můžete změnit jejich umístění pozici uživatele by se měl zachovat na následné spustí jako dialogové okno může být často použít jako součást rozsáhlejšího pracovního postupu.  
  
Při dialogů musíte vytvořit další dialogová okna, by měl dialogu nejhornější přeneseny napravo a dolů z nadřazeného objektu, které je zřejmé uživateli, který jste přešli na nové místo.  
  
#### <a name="modality"></a>Způsob  
Probíhá modální znamená, že uživatelé jsou potřeba dokončit nebo zrušit dialogu než budete pokračovat. Vzhledem k tomu, že modální dialogová okna blokovat uživateli interakci s dalšími částmi prostředí, tok úkolů vaší funkce jejich použití jako opatrně. Když modální operaci je nutné, Visual Studio má sdílené dialogy, kterou můžete integrovat do vaší funkce. Pokud je nutné vytvořit nový dialog, postupujte podle vzoru interakce existující dialogového okna s podobnými funkcemi.  
  
Když uživatelé musí provést dvě aktivity najednou, jako například **najít** a **nahradit** při zápisu nový kód, by měla být nemodálního dialogu tak, aby uživatel můžete snadno přepínat mezi nimi. Okna nástrojů Visual Studio obecně používá pro tento typ podporuje editor propojené úlohy.  
  
#### <a name="control-configuration"></a>Konfigurace ovládacího prvku  
Bylo v souladu s existující ovládacího prvku konfigurace, které totéž v sadě Visual Studio provést.  
  
#### <a name="title-bars"></a>Záhlaví  
  
-   Text v záhlaví musí podle názvu příkaz, který je spuštěn.  
  
-   V dialogovém okně záhlaví je třeba použít žádná ikona. V případech, kde systém vyžaduje jednu použijte logo sady Visual Studio.  
  
-   Dialogová okna by neměl mít minimalizovat nebo maximalizovat tlačítka.  
  
-   Tlačítka nápovědy v záhlaví okna jsou zastaralé. Nepřidávejte je do nové dialogová okna. Pokud existují, by se zobrazit téma nápovědy, které je koncepčně relevantní pro úlohu.  
  
 ![Specifikace platí pro záhlaví v sadě Visual Studio dialogy](../../extensibility/ux-guidelines/media/0704-03_titlebarspecs.png "0704 03_TitleBarSpecs")<br />Specifikace platí pro záhlaví v sadě Visual Studio dialogová okna
  
#### <a name="control-buttons"></a>Ovládací tlačítka  
Obecně platí **OK**, **zrušit**, a **pomoci** vodorovně uspořádání tlačítek v pravém dolním rohu dialogu. Alternativní nad sebou je povolená, pokud se zobrazí se dialogové okno má několik tlačítek v dolní části dialog, který bude k dispozici visual záměně se ovládací tlačítka.  
  
![Přijatelné konfigurace pro ovládací prvek tlačítka v sadě Visual Studio dialogová okna](../../extensibility/ux-guidelines/media/0704-04_controlbuttonconfig.png "0704 04_ControlButtonConfig")<br />Přijatelné konfigurace pro ovládací prvek tlačítka v sadě Visual Studio dialogová okna
  
Dialogové okno musí obsahovat výchozí ovládací prvek tlačítko. Pokud chcete určit nejlepší příkaz použil jako výchozí, vyberte z následujících možností (uvedené v pořadí podle priority):  
  
-   Vyberte příkaz co možná nejbezpečnějším a nejbezpečnější jako výchozí. To znamená, zvolíte příkaz nejpravděpodobnější nedošlo ke ztrátě dat. a zamezit tak přístup k nezamýšleným systému.  
  
-   Nejsou-li ztrátě dat a zabezpečení faktory, potom vyberte příkaz výchozí podle pohodlí. Včetně nejpravděpodobnější příkaz jako výchozí zlepší pracovního postupu uživatele, pokud dialogu podporuje časté nebo opakovaných úloh.  
  
Vyhněte se trvale destruktivní akce pro příkaz výchozí výběr. Pokud se takový příkaz nachází, vyberte místo toho bezpečnější příkaz jako výchozí.  
  
#### <a name="access-keys"></a>Přístupové klávesy  
Nepoužívejte přístupové klíče pro **OK**, **zrušit**, nebo **pomoci** tlačítka. Tyto přepínače jsou namapované na klávesové zkratky ve výchozím nastavení:  
  
| Název tlačítka | Klávesová zkratka |  
| --- | --- |  
| OK | Enter |  
| Zrušit | Esc |  
| Nápověda | F1 |  
  
#### <a name="imagery"></a>Dokumentů  
Nepoužívejte bitové kopie v dialogových oknech. Nepoužívejte ikony. velké ikony v dialogových oknech jenom pro použití místo. Pomocí bitových kopií, pouze pokud jsou důležitou součástí zdůraznění zprávu pro uživatele, jako ikony upozornění nebo stavu animace.  
  
###  <a name="BKMK_PrioritizingAndLayering"></a>Určení priority a vrstvení  
  
#### <a name="prioritizing-your-ui"></a>Určení priority vašeho uživatelského rozhraní  
Může být potřeba převést některé prvky uživatelského rozhraní pro forefrontu a umístěte pokročilejší chování a možnosti (včetně skrytého příkazy) do dialogová okna. Běžně používané funkce uvede forefrontu tím, že místo pro něj a tím, že viditelné ve výchozím nastavení v uživatelském rozhraní s textový popisek když se zobrazí dialogové okno.  
  
#### <a name="layering-your-ui"></a>Vrstvení vašeho uživatelského rozhraní  
Pokud zjistíte, že dialogové okno je nezbytné, ale překročí související funkce, které má být k dispozici pro uživatele co lze zobrazit v dialogovém okně pro jednoduché, budete muset vrstvy uživatelské rozhraní. Nejčastější rozvrstvení metody, které se používá v sadě Visual Studio jsou karty a hallways nebo řídicí panely. V některých případech může být vhodné oblasti, které můžete rozbalit nebo sbalit. Adaptivní uživatelského rozhraní se obecně nedoporučuje v sadě Visual Studio.  
  
Existují výhody a nevýhody různých metod vrstvení prostřednictvím karty jako ovládací prvky uživatelského rozhraní. Prohlédněte si seznam níž, které zajistí, že vybíráte rozvrstvení technika, který je vhodný pro vaši situaci.  
  
##### <a name="tabbing"></a>Použití tabulátoru  
  
| Přepínání mechanismus | Výhody a odpovídající pomocí | Nevýhody a nevhodných použití |  
| --- | --- | --- |  
| Ovládací prvek karty | Stránky dialogového okna logicky seskupovat do související sady<br /><br />Užitečné pro méně než pět (nebo počet karet, které se vejdou do jeden řádek v dialogovém okně) stránky souvisejících ovládacích prvků v dialogovém okně<br /><br />Karta popisky musí být krátký: jedno nebo dvě slova, která lze snadno identifikovat obsah<br /><br />Běžné styl systému dialogové okno<br /><br />Příklad: **souboru Explorer &gt; položka vlastnosti** | Provedení krátké popisky může být složité<br /><br />Obecně nemá škálování za pět karty v jedné dialogové okno<br /><br />Nevhodný, pokud máte příliš mnoho karty pro jeden řádek (použijte technika alternativní rozvrstvení)<br /><br />Není extensible |  
| Navigace na bočním panelu | Jednoduché přepínání zařízení, které zvládne více kategorií než karty<br /><br />Plochý seznam kategorií (žádná hierarchie)<br /><br />Rozšiřitelné<br /><br />Příklad: **přizpůsobit... &gt;Přidat – příkaz** | Není vhodné využít vodorovný prostor, pokud máte méně než tři skupiny<br /><br />Úloha může být lépe hodí pro rozevírací seznam |  
| Ovládací prvek stromu | Umožňuje neomezený kategorií<br /><br />Umožňuje seskupení nebo hierarchie kategorií<br /><br />Rozšiřitelné<br /><br />Příklad: **nástroje &gt; možnosti** | Výraznou vnořené hierarchie může způsobit nadměrné vodorovného posouvání<br /><br />Visual Studio má overabundance stromové zobrazení |  
| Průvodce | Pomáhá s dokončení úkolů a provede uživatele provede kroky, založené na úlohách, sekvenční: Průvodce představuje úlohu vysoké úrovně a jednotlivé panely představují dílčí úkoly, které jsou potřebné k provedení celkové úlohy<br /><br />To užitečné, pokud úloha protne hranice uživatelského rozhraní, jako když uživatel byste jinak museli používat více editory a nástroje systému windows k dokončení úlohy<br /><br />To užitečné, pokud úloha vyžaduje vytvoření větve<br /><br />To užitečné, pokud úloha obsahuje závislosti mezi kroky<br /><br />To užitečné, pokud několik podobných úloh s jeden rozhodnutí rozvětvení lze zobrazit v dialogovém okně pro jeden a snížit počet jiné podobné dialogová okna | Nevhodná pro všechny úlohy, které nevyžaduje sekvenční pracovní postup<br /><br />Uživatelé se může stát obávat přílišné složitosti a zaměňovat průvodcem s příliš mnoho kroků<br /><br />Průvodci ze své podstaty omezenou nemovitosti obrazovky |  
  
##### <a name="hallways-or-dashboards"></a>Hallways nebo řídicích panelů  
Hallways a řídicí panely jsou dialogová okna nebo panelů, které slouží jako spouštění odkazuje na další dialogová okna a systému windows. Dobře navrženou "hallway" okamžitě zobrazí pouze nejběžnější možnosti, příkazy a nastavení, které uživateli umožňují snadno provádět běžné úlohy. Jako hallway reálného poskytuje umožňují získat přístup k přístup místnostmi za je, zde méně běžné uživatelské rozhraní se shromažďují do samostatných "prostorech" (často. Další dialogová okna) souvisejících funkcí, které jsou přístupné z hlavní hallway.  
  
Alternativně uživatelské rozhraní, které nabízí všechny funkce dostupné v jedné kolekci místo refaktoring méně běžné funkce do samostatných umístění je jednoduše řídicí panel.  
  
![Koncept hallway pro vystavení dalšího uživatelského rozhraní v aplikaci Outlook](../../extensibility/ux-guidelines/media/0704-08_hallway.png "0704 08_Hallway")<br />Koncept hallway pro vystavení dalšího uživatelského rozhraní v aplikaci Outlook
  
##### <a name="adaptive-ui"></a>Adaptivní uživatelského rozhraní  
Zobrazení nebo skrytí uživatelského rozhraní na základě využití nebo samoobslužné hlášené činnost koncového uživatele je jiný způsob prezentace potřeby uživatelského rozhraní při skrytí další části. V sadě Visual Studio, to se nedoporučuje, protože může být složité algoritmy pro rozhodování, kdy se mají zobrazit či skrýt uživatelské rozhraní a pravidla bude vždy nesprávný pro některé sadu případů.  
  
##  <a name="BKMK_Projects"></a>Projekty  
  
### <a name="projects-in-the-solution-explorer"></a>Projekty v Průzkumníku řešení  
Většina projekty jsou klasifikovány jako odkaz na základě, založené na adresář nebo smíšený. V Průzkumníku řešení se současně podporují všechny tři typy projektů. Kořenové činnost koncového uživatele při práci s projekty probíhá uvnitř toto okno. Přestože jsou uzly jiný projekt odkaz, adresáře nebo typu ve smíšeném režimu projekty, je běžné interakce vzor, který má být použita jako výchozí bod před Rozbíhající do projektu konkrétní uživatel vzory.  
  
Projekty měli vždy:  
  
-   Podporují možnost přidávat projektu složek a uspořádávat obsah projektu  
  
-   Zachovat konzistentní model trvalosti projektu  
  
Projekty musí také udržovat konzistentní interakce modely pro:  
  
-   Odebírání položek projektu  
  
-   Ukládání dokumentů  
  
-   Úpravy vlastností projektu  
  
-   Úpravy na projekt v alternativní zobrazení  
  
-   Operace přetažení myší  
  
### <a name="drag-and-drop-interaction-model"></a>Přetažení myší interakce modelu  
Projekty obvykle klasifikovat sami jako odkaz na základě (možné zachovat pouze odkazy na položky projektu v úložišti), adresář na základě (moct zachována pouze položky projektu fyzicky uložené v hierarchii projekt), nebo ve smíšeném (možné zachovat odkazy nebo fyzické položek). Prostředí IDE může vyrovnávat všechny tři typy projektů současně uvnitř **Průzkumníku řešení**.  
  
Z hlediska přetažení myší by se měly používat následující vlastnosti pro každý typ projektu v rámci **Průzkumníku řešení**:  
  
-   **Referenční dokumentace založené na projektu:** klíče bod je, že je přetáhnete projektu kolem odkaz na položku v úložišti. Když na projekt na základě referenční funguje jako zdroj pro operaci přesunutí, odstraňte pouze odkaz na položku z projektu. Položka nesmí ve skutečnosti odstranit z pevného disku. Při projektu na základě referenční funguje jako cíl pro operaci přesunutí (nebo kopii), ho měli přidat odkaz na původní zdrojová položka bez vytvoření privátní kopie položky.  
  
-   **Na základě adresář projektu:** ze zobrazení of bodu přetahování myší, je projekt přetahování kolem fyzické položky spíše než odkaz. Když projektu na základě directory funguje jako zdroj pro operace přesunutí, by měl ukončení se odstraňuje fyzické položku z pevného disku a také odebere ji z projektu. Když projektu na základě directory funguje jako cíl pro operaci přesunutí (nebo kopii), měli kopii Zdrojová položka do cílového umístění.  
  
-   **Ve smíšeném cílový projekt:** ze zobrazení of bodu přetahování myší, chování tento typ projektu je založena na povaze položky přetažen buď (odkaz na položku v úložišti), nebo samotnou položku. Správné chování odkazů a fyzické položky jsou popsané výše.  
  
Kdyby existovalo pouze jeden typ projektu v **Průzkumníku řešení**, pak by přehledné operací přetažení myší. Protože každý projekt systém má schopnost definovat vlastní chování přetahování myší, aby předvídatelné uživatelské prostředí vhodné dodržovat určité pokyny (podle chování přetažení myší Průzkumník Windows):  
  
-   Beze změny přetáhněte operaci **Průzkumníku řešení** (když Ctrl ani posunutí klíče jsou uložené) by měl mít za následek operaci přesunutí.  
  
-   Operaci přetažení posunutí by také způsobit operaci přesunutí.  
  
-   Operaci přetažení CTRL by měl mít za následek operace kopírování.  
  
-   Systémy založené na odkazu a smíšený projektu podporu znalost problematicky přidání odkazu (nebo reference) a zdrojová položka. Pokud nejsou tyto projekty cíl operace přetažení myší (když **kombinaci kláves Ctrl + Shift** trvá), výsledkem by měla odkaz na položku přidávanou do projektu  
  
Ne všechny operací přetažení myší jsou rozumný v rámci kombinace projekty založené na odkaz, na základě adresáře a smíšený. Konkrétně je problematické předstírají, že k povolení operace s přesunutí mezi projektu na základě directory zdrojový a cílový odkaz na základě projekt, protože zdroj na základě adresář projektu bude muset odstranit položku zdroj po dokončení přesunu. Cílový odkaz na základě projekt by pak skončili s odkazem na odstraněné položky.  
  
Je také zavádějící předstírají, že operace kopírování mezi těmito typy projektů povolit, protože cílový odkaz na základě projekt by neměl nezávislá kopie Zdrojová položka. Podobně kombinaci kláves Ctrl + Shift přetahování do projektu na základě directory cíl by neměl být povolena, protože projektu na základě adresáře nelze trvale uložit odkazy. V případech, kde není podporována operace přetahování myší by měl rozhraní IDE zakáže rozevíracího a zobrazit uživatele ne myší kurzor (zobrazené v následující tabulce ukazatel).  
  
Zdroj projektu přetahování správně implementovat chování přetahování myší, musí komunikovat jeho povaze do projektu cíl. (Například je na základě odkaz nebo adresáře?) Tyto informace je indikován formát schránky, které nabízí zdroji. Jako zdroj přetažení (nebo operace kopírování schránky) by měl nabízet projektu buď `CF_VSREFPROJECTITEMS` nebo `CF_VSSTGPROJECTITEMS` , podle toho, zda projektu na základě odkaz nebo na základě adresáře. Z těchto formátů mají stejný obsah dat, který je podobný Windows `CF_HDROP` formátu s tím rozdílem, že seznam řetězců, namísto názvů souborů, jsou dvojitou -`NULL` ukončena seznam `Projref` řetězce (vrácený z `IVsSolution::GetProjrefOfItem`nebo `::GetProjrefOfProject` podle potřeby).  
  
Cíl rozevírací (nebo operaci vložení schránky), projekt by měl přijmout `CF_VSREFPROJECTITEMS` a `CF_VSSTGPROJECTITEMS`, i když přesná zpracování operace přetažení myší se liší v závislosti na povaze cílový projekt a projekt zdroje. Zdroj projektu deklaruje jeho povaze podle jestli nabízí `CF_VSREFPROJECTITEMS` nebo `CF_VSSTGPROJECTITEMS`. Cílem rozevíracího rozumí vlastní povaze a proto má dostatek informací k rozhodnutí, aby zda přesunutí, kopírování, nebo by se měla provést odkaz. Uživatel také upraví, které operaci přetažení myší je nutné provést stisknutím kombinace kláves Ctrl, Shift, nebo jak kláves Ctrl a Shift. Je důležité pro cíle přetažení správně indikující, které operace se provede předem v jeho `DragEnter` a `DragOver` metody. **Průzkumníku řešení** automaticky určí, zda projekt zdroj a cíl projekt jsou stejné projektu.  
  
Přetahování položek projektu napříč instancemi sady Visual Studio (například z jedné instance devenv.exe do jiného) konkrétně není podporován. **Průzkumníku řešení** také přímo to zakáže.  
  
Uživatel by měl vždycky být schopní určit vliv operací přetažení myší vyberte položku, přetáhněte ji do cílového umístění a sledování, které následující ukazatele myši se zobrazí předtím, než položka byla vynechána:  
  
| Ukazatele myši | Příkaz | Popis |  
| :---: | --- | --- |  
| ![Myš "žádné rozevírací" ikonu](../../extensibility/ux-guidelines/media/0706-01_mousenodrop.png "0706 01_MouseNoDrop") | Žádné rozevírací | Položku nelze umístit do zadaného umístění. |  
| ![Ikona "kopie" myši](../../extensibility/ux-guidelines/media/0706-02_mousecopy.png "0706 02_MouseCopy") | Kopírovat | Bude položka zkopírována do cílového umístění. |  
| ![Myš "přesunout" ikonu](../../extensibility/ux-guidelines/media/0706-03_mousemove.png "0706 03_MouseMove") | Přesunutí | Položka bude přesunuta do cílového umístění. |  
| ![Ikona "Přidat odkaz na" myši](../../extensibility/ux-guidelines/media/0706-04_mouseaddref.png "0706 04_MouseAddRef") | Přidání odkazu | Odkaz na vybranou položku se zařadí do cílového umístění. |

#### <a name="reference-based-projects"></a>referenční dokumentace založené na projekty  
 Následující tabulka shrnuje operací přetažení myší (i Vyjmout/Kopírovat/vložit), které by se měla provést závislosti na povaze zdroj položky a modifikátor klíče stisknutí tlačítka pro projekty založené na odkazuje cílový:  
  
| Modifikátor | Kategorie | Zdrojová položka: nebo odkazem | Zdrojová položka: fyzické položky nebo systém souborů (`CF_HDROP`) |  
| --- | --- | --- | --- |  
| Žádné – modifikátor | Akce | Přesunutí | Odkaz |  
| Žádné – modifikátor | cíl | Přidá odkaz na původní položce | Přidá odkaz na původní položce |  
| Žádné – modifikátor | Zdroj | Odstranění odkaz k původní položce | Zachovává původní položce |  
| Žádné – modifikátor | Výsledek | `DROPEFFECT_MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_LINK`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |  
| SHIFT + přetažení | Akce | Přesunutí | Žádné rozevírací |  
| SHIFT + přetažení | cíl | Přidá odkaz na původní položce | Žádné rozevírací |  
| SHIFT + přetažení | Zdroj | Odstranění odkaz k původní položce | Žádné rozevírací |  
| SHIFT + přetažení | Výsledek | `DROPEFFECT_MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | Žádné rozevírací |  
| CTRL + přetažení | Akce | Kopírovat | Žádné rozevírací |  
| CTRL + přetažení | cíl | Přidá odkaz na původní položce | Žádné rozevírací |  
| CTRL + přetažení | Zdroj | Zachová odkaz k původní položce | Žádné rozevírací |  
| CTRL + přetažení | Výsledek | `DROPEFFECT_COPY`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | Žádné rozevírací |  
| Ctrl + Shift + přetažení | Akce | Odkaz | Odkaz |  
| Ctrl + Shift + přetažení | cíl | Přidá odkaz na původní položce | Přidá odkaz na původní položce |  
| Ctrl + Shift + přetažení | Zdroj | Zachová odkaz k původní položce | Zachovává původní položce |  
| Ctrl + Shift + přetažení | Výsledek | `DROPEFFECT_LINK`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_LINK`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |  
| Ctrl + Shift + přetažení | Poznámka | Stejné jako přetažení myší chování pro zkratky v Průzkumníku Windows. ||  
| Vyjímání a vkládání | Akce | Přesunutí | Odkaz |  
| Vyjímání a vkládání | cíl | Přidá odkaz na původní položce | Přidá odkaz na původní položce |  
| Vyjímání a vkládání | Zdroj | Zachová odkaz k původní položce|Zachovává původní položce |  
| Vyjímání a vkládání | Výsledek | Položka zůstane v původním umístění úložiště | Položka zůstane v původním umístění úložiště |  
| Kopírování a vkládání | Akce | Kopírovat | Odkaz |  
| Kopírování a vkládání | Zdroj | Přidá odkaz na původní položce | Přidá odkaz na původní položce |  
| Kopírování a vkládání | Výsledek | Zachová odkaz k původní položce | Zachovává původní položce |  
| Kopírování a vkládání | Akce | Položka zůstane v původním umístění úložiště | Položka zůstane v původním umístění úložiště |  
  
#### <a name="directory-based-projects"></a>Projekty založené na adresář  
Následující tabulka shrnuje operace přetažení myší (i Vyjmout/Kopírovat/vložit), které by se měla provést závislosti na povaze zdroj položky a modifikátor klíče stisknutí tlačítka pro projekty založené na službě directory cíl:  
  
| Modifikátor | Kategorie | Zdrojová položka: nebo odkazem | Zdrojová položka: fyzické položky nebo systém souborů (`CF_HDROP`) |  
| --- | --- | --- | --- |  
| Žádné – modifikátor | Akce | Přesunutí | Přesunutí |  
| Žádné – modifikátor | cíl | Položka kopie do cílového umístění | Položka kopie do cílového umístění |  
| Žádné – modifikátor | Zdroj | Odstranění odkaz k původní položce | Odstranění odkaz k původní položce | | Žádné – modifikátor | Výsledek | `DROPEFFECT_MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |  
| SHIFT + přetažení | Akce | Přesunutí | Přesunutí |  
| SHIFT + přetažení | cíl | Položka kopie do cílového umístění | Položka kopie do cílového umístění |  
| SHIFT + přetažení | Zdroj | Odstranění odkaz k původní položce | Odstraní položku z původního umístění |
| SHIFT + přetažení | Výsledek | `DROPEFFECT_MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |  
| CTRL + přetažení | Akce | Kopírovat | Kopírovat |  
| CTRL + přetažení | cíl | Položka kopie do cílového umístění | Položka kopie do cílového umístění |  
| CTRL + přetažení | Zdroj | Zachová odkaz k původní položce | Zachová odkaz k původní položce |  
| CTRL + přetažení | Výsledek | `DROPEFFECT_COPY`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_COPY`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |  
| Ctrl + Shift + přetažení | | Žádné rozevírací | Žádné rozevírací |  
| Vyjímání a vkládání | Akce | Přesunutí | Přesunutí |  
| Vyjímání a vkládání | cíl | Položka kopie do cílového umístění | Položka kopie do cílového umístění |  
| Vyjímání a vkládání | Zdroj | Odstranění odkaz k původní položce | Odstraní položku z původního umístění |  
| Vyjímání a vkládání | Výsledek | Položka zůstane v původním umístění úložiště | Položka odstraněna z původního umístění v úložišti |  
| Kopírování a vkládání | Akce | Kopírovat | Kopírovat |  
| Kopírování a vkládání | cíl | Přidá odkaz na původní položce | Položka kopie do cílového umístění |  
| Kopírování a vkládání | Zdroj | Zachovává původní položce | Zachovává původní položce |  
| Kopírování a vkládání | Výsledek | Položka zůstane v původním umístění úložiště | Položka zůstane v původní umístění in úložiště |
  
#### <a name="mixed-target-projects"></a>Ve smíšeném cíl projekty  
Následující tabulka shrnuje operace přetažení myší (i Vyjmout/Kopírovat/vložit), které by se měla provést závislosti na povaze zdroj položky a modifikátor klíče stisknutí tlačítka pro projekty ve smíšeném cíl:  
  
| Modifikátor | Kategorie | Zdrojová položka: nebo odkazem | Zdrojová položka: fyzické položky nebo systém souborů (`CF_HDROP`) |  
| --- | --- | --- | --- |
| Žádné – modifikátor | Akce | Přesunutí | Přesunutí |
| Žádné – modifikátor | cíl | Přidá odkaz na původní položce | Položka kopie do cílového umístění |
| Žádné – modifikátor | Zdroj | Odstranění odkaz k původní položce | Odstranění odkaz k původní položce |
| Žádné – modifikátor | Výsledek | `DROPEFFECT_ MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_ MOVE`se vrátí jako akce z `::Drop` a položky se odstraní z původního umístění v úložišti |
| SHIFT + přetažení | Akce | Přesunutí | Přesunutí |
| SHIFT + přetažení | cíl | Přidá odkaz na původní položce | Položka kopie do cílového umístění |
| SHIFT + přetažení | Zdroj | Odstranění odkaz k původní položce | Odstraní položku z původního umístění | 
| SHIFT + přetažení | Výsledek | `DROPEFFECT_ MOVE`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_ MOVE`se vrátí jako akce z `::Drop` a položky se odstraní z původního umístění v úložišti |
| CTRL + přetažení | Akce | Kopírovat | Kopírovat |
| CTRL + přetažení | cíl | Přidá odkaz na původní položce | Položka kopie do cílového umístění |
| CTRL + přetažení | Zdroj | Zachová odkaz k původní položce | Zachovává původní položce |
| CTRL + přetažení | Výsledek | `DROPEFFECT_ COPY`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_ COPY`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |
| Ctrl + Shift + přetažení | Akce | Odkaz | Odkaz |
| Ctrl + Shift + přetažení | cíl | Přidá odkaz na původní položce | Přidá odkaz na původní zdrojová položka |
| Ctrl + Shift + přetažení | Zdroj | Zachová odkaz k původní položce | Zachovává původní položce |
| Ctrl + Shift + přetažení | Výsledek | `DROPEFFECT_ LINK`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště | `DROPEFFECT_ LINK`se vrátí jako akce z `::Drop` a položka zůstane v původním umístění úložiště |
| Vyjímání a vkládání | Akce | Přesunutí | Přesunutí |
| Vyjímání a vkládání | cíl | Položka kopie do cílového umístění | Položka kopie do cílového umístění |
| Vyjímání a vkládání | Zdroj | Odstranění odkaz k původní položce | Odstraní položku z původního umístění |
| Vyjímání a vkládání | Výsledek | Položka zůstane v původním umístění úložiště | Položka odstraněna z původního umístění v úložišti |
| Kopírování a vkládání | Akce | Kopírovat | Kopírovat |
| Kopírování a vkládání | cíl | Přidá odkaz na původní položce | Položka kopie do cílového umístění |
| Kopírování a vkládání | Zdroj | Zachovává původní položce | Zachovává původní položce |
| Kopírování a vkládání | Výsledek | Položka zůstane v původním umístění úložiště | Položka zůstane v původním umístění úložiště |
  
Tyto podrobnosti by měly vzít v úvahu při implementaci přetahování **Průzkumníku řešení**:  
  
-   Návrh pro více scénářů výběr.  
  
-   Názvy souborů (úplná cesta) musí být jedinečný v rámci cílový projekt nebo rozevírací by nemělo být povoleno.  
  
-   Názvy složek musí být jedinečné (velká a malá písmena) na úrovni jsou vyřazována.  
  
-   Existují chování rozdíly mezi soubory, které jsou otevřené nebo uzavřené v době přetažení (není uveden ve scénářích výše).  
  
-   Soubory nejvyšší úrovně chovat trochu jinak než soubory ve složkách.  
  
Jiný problém zajímat je způsob zpracování operace přesunu na položky, které mají otevřené návrháře nebo editory. Očekávané chování je následujícím způsobem (to platí pro všechny typy projektů):  
  
1.  Pokud otevřete editor nebo Návrhář nemá veškeré neuložené změny, potom okně editor nebo designer by měly být bezobslužně ukončeny.  
  
2.  Pokud otevřete editor nebo Návrhář máte neuložené změny, potom zdroj přetahování čekat rozevíracího dojít, a poté požádat uživatele, aby před zavřením okno s výzvou podobný následujícímu uložit nepotvrzené změny v otevřené dokumenty :  
  
    ```  
    ==========================================================   
         One or more open documents have unsaved changes.  
    Do you want to save uncommitted changes before proceeding?   
                      [Yes]  [No]  [Cancel]   
    ==========================================================  
    ```  
  
To umožňuje uživateli možnost uložení probíhající práce předtím, než cílový vytváří jeho kopie. Nová metoda `IVsHierarchyDropDataSource2::OnBeforeDropNotify` byl přidán do povolit toto zpracování.  
  
Cíl pak zkopíruje stav položky, protože je v úložišti (bez zahrnutí neuložené změny v editoru, pokud se uživatel rozhodl **ne**). Po dokončení cíl jeho kopírování (v `IVsHierarchyDropDataSource::Drop`), zdroj je zadána možnost pro dokončení odstranění části operaci přesunutí (v `IVsHierarchyDropDataSource::OnDropNotify`).  
  
Musí být ponechány otevřené žádné editory s neuložené změny. Pro tyto dokumenty s neuložené změny to znamená, že provede kopírování část operaci přesunutí, ale část odstranění bude přerušena. V několika výběr scénář, když uživatel vybere **ne**, tyto dokumenty s neuložené změny by neměly být uzavřen nebo odebrat, ale bez neuložené změny by měl zavře a odebrat.