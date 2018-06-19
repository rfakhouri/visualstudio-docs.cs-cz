---
title: Textu uživatelského rozhraní a nápovědu pro sadu Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: e8747d07-6c90-46cc-b425-55b589f7e9e4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 697c794d17f3004b0f37e668ff67afb703490e18
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31148363"
---
# <a name="ui-text-and-help-for-visual-studio"></a>Textu uživatelského rozhraní a nápovědu pro sadu Visual Studio
##  <a name="BKMK_UITextAndTerminology"></a> Textu uživatelského rozhraní a přehled terminologie  
 Srozumitelné text je zásadní význam pro efektivní uživatelského rozhraní. Software uživatelé mohou číst popisků nejprve, konkrétně ty nejdůležitější dokončení úlohy po ruce. Statický text je pro čtení s nižší četností. Plán pro uživatele a jejich relace pracovní začněte rychlé prověřování zaměřené na okna celý, za nímž následuje čtení uživatelského rozhraní v tomto přibližnou pořadí:  
  
1.  Interaktivní ovládacích prvků v Centru  
  
2.  Potvrdit tlačítka  
  
3.  Interaktivní ovládacích prvků jinde  
  
4.  Hlavní pokyny  
  
5.  Další vysvětlení  
  
6.  Název okna  
  
7.  Další statický text v hlavní  
  
### <a name="usage-patterns-for-ui-text"></a>Vzorce pro textu uživatelského rozhraní  
  
#### <a name="title-bar-text"></a>Text záhlaví  
 Text záhlaví musí odpovídat příkaz, který vytvořený uživatelského rozhraní.  
  
#### <a name="instructional-text-helper-text"></a>Pokyny (textu Pomocník)  
 V některých dialogová okna je užitečné jako viditelného hlavní pokyny vysvětlit, co dělat v okně nebo na stránce. To se někdy označuje jako "textu Pomocník."  
  
##### <a name="writing-style-rules-for-helper-text"></a>Zápis pravidla stylu textu Pomocník  
  
-   Nemáte popisují zřejmé. Pokud je nezbytně nutné, nezahrnujte podle požadavků.  
  
-   Podle požadavků vždy uvedeny v horní části dialogového okna a by měla odkazovat na během provádění úlohy.  
  
-   Přesněji můžete uživatelům vysvětlit, co je potřeba udělat. Vyhněte se nadměrné komunikace a redundance.  
  
-   Zkontrolujte každé okno a eliminovat duplicitní slova a příkazy.  
  
-   Zachovat instruktážní text krátké. Pokud Další informace jsou nezbytné pro určité uživatele nebo scénářů, zadejte odkaz na podrobné koncepční téma online.  
  
-   Zadejte text tak, aby každý word obsahuje váhy a je nutné.  
  
-   Využijte existující Microsoft vodítka pro [Text v uživatelském rozhraní](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) a [Style a styl podání](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx).  
  
#### <a name="supplemental-instructions"></a>Další pokyny  
 Další pokyny poskytují další informace, které pomáhá uživatelům pochopit ovládací prvky nebo řízení seskupení. To může zahrnovat text nápovědy potřeba pochopit, jaké formátu očekává vstupního ovládacího prvku. Nepoužívejte další pokyny. Je vyhradit pro případech, kdy je pravděpodobné, že uživatel nebude plně znají důsledky možnost, kterou jejich provedení.  
  
 ![Další text v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-b_supplementaltext1.png "0601 b_SupplementalText1")  
  
 **Další text v sadě Visual Studio**  
  
 ![Další text v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-c_supplementaltext2.png "0601 c_SupplementalText2")  
  
 **Další text v sadě Visual Studio**  
  
#### <a name="infotips"></a>InfoTips  
 Pokyny často, může být příliš dlouhý na pozici na místě v uživatelském rozhraní nebo mohou být užitečné pouze pro nové uživatele, se úplně jako zbytečné soubory pro zkušené uživatele. V takovém případě musí být umístěny instruktážní nebo informační text jako popisek pod tip.  
  
 InfoTips musí být umístěny téměř ovládacích prvků, se vztahují k a musí používat konkrétní informační tip ikonu, která dosud nerušivý znatelné.  
  
 ![Informační tip v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601 d_InfoTip")  
  
 **Příklad tip v sadě Visual Studio**  
  
##### <a name="writing-style-rules-for-infotips"></a>Zápis pravidla pro InfoTips  
  
-   Zápis InfoTips jako dokončení věty. Vyžadují konkrétní příkazy, věty a koncové interpunkce.  
  
-   Použijte InfoTips doplníte hlavní pokyn nebo informace. Pokud právě používáte jiná slova přepočítat main nápad, nepotřebujete tip.  
  
-   Zachovat InfoTips krátké sladké. Použít krátká slova a prostý, každý den jazyk, který podporuje a vyzývá uživatele.  
  
-   Využijte existující Microsoft vodítka pro [Text v uživatelském rozhraní](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742478\(v=vs.85\).aspx) a [Style a styl podání](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742477\(v=vs.85\).aspx).  
  
#### <a name="control-labels"></a>Popisky ovládacího prvku  
 Popisky ovládacího prvku by měly být krátké a stručné a postupujte podle [Windows Desktop pokyny pro ovládací prvky](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742399\(v=vs.85\).aspx).  
  
 Další informace o řízení formát popisku a umístění v rámci uživatelského rozhraní, najdete v části [rozložení pro sadu Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md).  
  
#### <a name="help-links"></a>Odkazy na nápovědu  
 Odkazy na nápovědu můžete umístit buď v rámci pokyny nebo v textu uživatelského rozhraní. Dají se odkazy na nápovědu nebo spusťte interní dialogová okna.  
  
##### <a name="visual-style-rules-for-help-links"></a>Pravidla vizuální styl pro odkazy na nápovědu  
  
-   Použijte správný prostředí barvy pro hypertextové odkazy. Správně stylem hypertextový odkaz nebude flash stručně red při kliknutí na. Pokud se zobrazí, je to znamenat, že prostředí barvy nejsou používány.  
  
-   Podtržení lze používat pouze na hover nebo když je odkaz vložený do odstavec.  
  
-   Podrobnější informace o visual a interakce styly pro hypertextové odkazy najdete v části tlačítka a hypertextové odkazy.  
  
##### <a name="writing-style-rules-for-help-links"></a>Zápis pravidla pro odkazy na nápovědu  
  
-   Při spouštění dialogová okna, Udržovat standardy pro výpustky: žádné třemi tečkami pro navigaci, výpustky Pokud úloha vyžaduje další uživatelského rozhraní.  
  
     ![Odkaz Nápověda v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-e_helplink.png "0601 e_HelpLink")  
  
     **Třemi tečkami (...) v nápovědě propojení určuje, že úloha bude vyžadovat další uživatelského rozhraní.**  
  
-   Odkazy nesmí začínat "Informace", protože se nejedná o záměru uživatele. Chce uživatel zodpovědět konkrétní dotaz, není obdrží obecné vzdělávání.  
  
-   Nápověda frázi propojí tak, aby vyzvou na otázku, bude zodpovědět tématu.  
  
     Nesprávný:  
     "Další informace o cenách služby Windows Azure Mobile Services"  
  
     Opravte:  
     "Jaké cenovou možnosti jsou dostupné pro Windows Azure Mobile Services?"  
  
-   Nikdy nepoužívejte *klikněte na tlačítko...*  na text odkazu.  
  
-   Nikdy odkaz pouze slovo "sem". Toto je problematické pro některé čtečky obrazovky, které bude hlas pouze s hypertextovým odkazem aplikace word.  
  
     Nesprávný:  
     "Další informace týkající se systému Windows Azure Mobile Services **sem**"  
  
     Opravte:  
     "Jaké cenovou možnosti jsou dostupné pro Windows Azure Mobile Services?"  
  
-   Další informace o správné zápis styl pro odkazy na nápovědu najdete v tématu [Windows Desktop pokyny o pomoc](https://msdn.microsoft.com/en-us/library/windows/desktop/dn742494\(v=vs.85\).aspx).  
  
#### <a name="hint-text"></a>Text nápovědy  
 Pomocný parametr text se zobrazuje jako vodoznak v ovládacím prvku nebo pod ovládacího prvku. Pomocí příslušné VSColors token, uplatní správné formátování `Environment.GrayText`.  
  
 Může se objevit v různých formách.  
  
-   Místo štítků ovládacích prvků:  
  
     ![Pomocného parametru text v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-f_hinttext1.png "0601 f_HintText1")  
  
-   S operaci která poskytuje pokyny:  
  
     ![Pomocného parametru text v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-g_hinttext2.png "0601 g_HintText2")  
  
-   S textem označující požadovaná položka:  
  
     ![Pomocného parametru text v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-h_hinttext3.png "0601 h_HintText3")  
  
#### <a name="watermark-text"></a>Vodoznakového textu  
 Prázdný návrhové ploše by měl být uveden text co udělat a také poskytnout odkazy na otevřete jiné související windows, pokud příslušné:  
  
 ![Text v sadě Visual Studio vodoznaku](../../extensibility/ux-guidelines/media/0601-i_watermarktext.png "0601 i_WatermarkText")  
  
 **Příklad vodoznakového textu v sadě Visual Studio**  
  
### <a name="common-terminology"></a>Obvyklá terminologie  
  
|Termín|Vysvětlení|Komentář|  
|----------|-----------------|-------------|  
|Přihlášení / odhlášení|Příkazy používány jako synonyma webové služby se pro představující ověřování do webových vlastnosti. V rámci klientů používáme tento jednou jako nejvyšší úrovně hodnoty pro podepisování a deaktivovat připojení uživatele IDE, které představuje nejvyšší úrovně identitou, která poskytuje vyšší úrovně funkcí, jako je roaming a licencí, které nejsou k dispozici s jiných připojení.|Uživatel IDE, je pouze funkce, které by měla představovat přihlašovací Odhlásit se příkaz, jak představuje nejvyšší uživatelská rozhraní IDE.|  
|Připojit / Odpojit|Použijte v místech, kde funkci udržuje jednoho připojení ke službě online.|Průzkumník serveru, kde může mít pouze jeden aktivní Azure připojení současně, je příkladem připojení nebo odpojení.|  
|Přidat nebo odebrat|Bez destruktivní. Použijte v případě přidávání nebo odebírání něco ze seznamu.|Dialogové okno správce sady TFS připojení serveru seznamu je příkladem přidat nebo odebrat.|  
|Odstranit|Destruktivní. Používejte jenom v případě, že je element, který je právě odebírán bude trvale zrušených nebo odstraněn z disku.|"Odstranit" obecně vyžaduje výzvu, pokud výsledek je odstraňte soubor z disku.|  
  
## <a name="error-messages"></a>Chybové zprávy  
  
### <a name="overview"></a>Přehled  
 Chyby dojít. Nastavení omezení na co můžete dělat uživatele je rozumný prvním krokem při bránění kterému se lze vyhnout chybové zprávy. Pokud dojde k chybě, můžete přejít správně vytvořená chybová zpráva však daleko směrem k zmírnění problém. Chybové zprávy jsou pravděpodobně jedním z nejdůležitějších typy oznámení, že uživateli se zobrazí, protože jsou synchronní a indikují problém, který musí být vyřešeny. Chybně napsané chybové zprávy uživatelé ještě na svých vlastních rozhodnout příčinu chyby a jakýkoli možná řešení.  
  
 Uživatelé mohou zastavit důrazem Nepromyšlené nebo složitá chybových zpráv, tak dojít k zápisu jenom nezbytné zprávy, které přidejte hodnotu pro uživatele. Pokud zpráva je jednoduše oznámení, použijte alternativní prezentaci.  
  
### <a name="rules-for-creating-an-error-message"></a>Pravidla pro vytváření chybovou zprávu  
  
-   Při vytváření chybové zprávy, zvolte úroveň odpovídající chyb pro cílovou skupinu. Může trvat Formulujte text přehledné informace, které poskytují akce uživatele, pokud je k dispozici. Si stav všechno, co uživatel nemusí vědět.  
  
-   Konstruktivní pomoc. Je jednodušší ke čtení a fungují v chybovou zprávu, která obsahuje instrukce.  
  
-   Nepoužívejte negativy dvojitou hodnotu.  
  
-   Proveďte obě automatickou a ruční gramatika a pravopis zkontrolovat všechny chybovou zprávu, kterou píšete.  
  
-   Pro komplexní chybové zprávy nepoužívejte po sobě jdoucích komunikace. Nikdy nepoužívejte F1 spojení pro chybovou zprávu. Samotnou zprávu by mělo být dostatečné.  
  
-   Použijte na správný ikonu.  
  
-   Zajistit, aby dotazy snadno pochopit a používat tlačítka, které mají zrušte zaškrtnutí volby, například "Odstranit" a "Zrušit".  
  
-   Pro upozornění být jasno, co bude důsledků budete pokračovat. Tlačítka by měl být uveden na důsledek.  
  
-   Pro chyby popisují, co uživatel provést k vyřešení problému. Tlačítka by měla být akce nebo vyslovení "Zavřít." Nepoužívejte tlačítko "OK" pro chybovou zprávu.  
  
-   Některé dotazy položte si při vytváření chybová zpráva:  
  
    -   Může uživatel zjistit, jak vyřešit problém s touto chybou samostatně?  
  
    -   Uživatel použít stejné termínů jako tuto chybu?  
  
    -   Je tato chyba ambigious nebo sdílet v několika situacích? Pokud ano, jak jste Průvodce uživatelů řešení, které potřebují?  
  
#### <a name="build-errors"></a>Chyby sestavení  
 Vzhledem k tomu, že Visual Studio je nástroj pro vývoj softwaru, řadu jeho komponenty mají kompilace, převod nebo kódování kroku převést práce vývojáře binárního formátu. Tyto převody mohou způsobit chyby, pokud kompilátor nemůže zpracovat nesprávně vytvořené soubory nebo pokud – možnosti kompilátoru nebylo správně nastaveno.  
  
 Visual Studio uživatelé můžete věnovat značné počet hodin vývoj řešení chyb při sestavení. Tato doba řešení zvyšuje chyby žádné závislosti nebo při chybové zprávy jsou špatně zápisu, který může být obtížné k odhalení zdroji této chyby.  
  
 Nejlepší chyby sestavení jsou ty, které na prvním místě, což je důvod, proč nedojde Visual Studio poskytuje automatického dokončování a podtržení vlnovkou IntelliSense. Validátory schématu a podobné nástroje poskytují stejný druh zpětné vazby. Tyto mechanismy proaktivně Průvodce uživatelům vytvořit ve správném formátu kód, lessening riziko chyby sestavení.  
  
 Visual Studio poskytuje nástroj okno, kde uživatelé mohou číst a procházet chybách, ke kterým došlo v systému windows jejich dokumentu. Klávesové zkratky jsou uvedeny tak, aby uživatel můžete rychle přejděte velkých objemů kódu a přejít přímo na umístění problému. Visual Studio také umožňuje jednotlivé chyby sestavení vlastnit konkrétní ID – klíčové slovo nebo kontextové nápovědy tak, aby uživatel může přejít přímo na téma nápovědy, která poskytuje podrobnější informace o této chybě.  
  
 Chyby sestavení jasným a přesným metrikám zápisu:  
  
-   **Použít prostý jazyk** vysvětlující problém s minimální nebo žádnou žargonu kompilátoru. Text chyby sestavení by nemělo být moc technické.  
  
-   **Popisují možné příčiny.** Například "chybí dvojtečka mezi vlastností a hodnotou v" (vlastnost): (hodnota) "deklarace."  
  
-   Zadejte podrobnosti o potenciální opravy. Pokud není k dispozici dostatek místa, mohou být další podrobnosti uváděny do příslušné téma nápovědy.  
  
### <a name="components-of-a-well-written-error-message"></a>Součástí správně vytvořená chybová zpráva  
  
#### <a name="use-the-shell-dialog-service-for-error-messages"></a>Použijte službu prostředí dialogové okno pro chybové zprávy.  
 Pomocí dialogu služby prostředí umožňuje řídit vzhled zprávy, písem konkrétně bez hlavní změny na jednotlivé prvky. Použití **IErrorInfo** mechanismy a sestavy, je pomocí **IVsUIShell::SetErrorInfo/ReportErrorInfo**.  
  
#### <a name="choose-an-effective-and-appropriate-notification-presentation"></a>Vyberte z prezentace efektivní a příslušné oznámení.  
 Použijte modální dialogové okno s kritická upozornění, pokud nedošlo ke ztrátě dat (synchronní oznámení) nevyžaduje okamžitou akci. Kritických ikon jsou vyhrazené pro situace, při které zavírání zprávy bez čtení může vést k negativní důsledky. Ztráta dat je důležité situace vyžadující odpověď úroveň upozornění. Nadměrné využití kritické ikony desensitizes uživatelům její význam. Pokud chybová zpráva je informační ve své podstatě, zvažte alternativy modální dialogové okno (asynchronní oznámení).  
  
#### <a name="provide-a-clean-succinct-explanation-of-why-the-problem-occurred-rather-than-a-technical-explanation"></a>Zadejte čistá, stručné vysvětlení proč k problému došlo místo technické vysvětlení.  
 Uživatelé s technické podrobnosti v vysvětlení nadměrného zatížení budou tyto nejspíše ignorovat chybové zprávy. Příklady dobrý zasílání zpráv:  
  
-   "Nelze otevřít požadovaný soubor."  
  
-   "Nelze se připojit k Internetu."  
  
#### <a name="provide-information-about-how-to-fix-the-problem"></a>Zadejte informace o tom, jak problém opravte.  
 Nabízí návrhy uživatele o tom, jak problém opravte. Pokud neexistují žádné návrhy buďte pravdivé s uživatelem. Zadejte přímé odkazy na alternativní online zdrojů, například se na technickou podporu nebo podpora komunity. Pokuste se specifických online informací vztahujících se k problému přejděte na položku uživatelé. ID chyby zvažte připojení uživatelů k posloupnost diskuse o konkrétní chybu. Příklady dobrý zasílání zpráv:  
  
-   "Ujistěte se, že jste připojeni k Internetu a operaci opakujte."  
  
-   "Zkontrolujte, zda soubor existuje a zda máte oprávnění k jeho otevření."  
  
#### <a name="write-a-message-that-is-short-and-to-the-point"></a>Zpráva, že je krátký a bodem zápisu.  
 Chybová zpráva může upozornit, vysvětlují a nabízí řešení ale stále být ignorována, pokud je příliš rozvláčný. Jeden řešením je použití progresivní zpřístupnění s tlačítkem na podrobnosti. Například zadejte krátký popis nebo řešení a pak přesuňte další podrobnosti v části Podrobnosti o tlačítko. Pokud se uživatelé rozhodnou přečíst další informace o chybě, že to učinit.  
  
 Jazyk zprávy musí být:  
  
-   **Příslušné domény.** Použití jazyka uživatele pochopili. I když vývojáři našich zákazníků se často nemají kontextu a terminologií, které máme.  
  
-   **Konkrétní.** Vyhněte se nepřesných slov a poskytnout konkrétní názvy a umístění zahrnutých objektů. Například chybovou zprávu, jako je "znak není platný" není užitečné. Které znak? "Soubor nebyl nalezen." Který soubor?  
  
-   **Zdvořilý.** Nepřidávejte jedná se o výsledek uživatele nebo je působí stupid provést. Vyhněte se k tomuto účelu nebo urážlivé jazyk (ukončit, spuštění, ukončení, závažná, neplatný). Vyhněte se text velkými písmeny, což je často považovat za shouting a není jako čitelný. Nepoužívejte humor.  
  
-   **Opravte.** Použijte správný pravopisné a gramatické (i v alphas). Překlepům jsou sobě podáváte neprofesionální a to nepříjemné.  
  
-   **Kontextově vhodné.** Použijte příslušné tlačítko text. Vyhněte se tlačítko "OK". použijte raději "Pokračovat" nebo "Ano/Ne"  
  
### <a name="error-message-examples"></a>Příklady chybová zpráva  
  
|Dobré|Špatné|  
|----------|---------|  
|"Vytáčené číslo je již ve službě. Zkontrolujte číslo a opakujte vytočit nebo vytočit 0 pro operátor."|-"Chyba (449): Neplatné číslo"<br />– "Tato chyba neošetřené výjimky označuje, že operace úspěšně dokončena."<br /><br /> ![Chybný chybová zpráva v sadě Visual Studio](../../extensibility/ux-guidelines/media/0602-a_errordialog.png "0602 a_ErrorDialog")|  
  
## <a name="accessing-help"></a>Přístup k nápovědě  
  
### <a name="overview"></a>Přehled  
 Kromě dokumentace na webu MSDN Visual Studio uživatel má několik přístupových bodů, pomůže uživatele v uživatelském rozhraní. Zajistěte, aby tyto přístupové body konzistentně k dispozici, týmů funkce muset využít výhod systému nápovědy, které nabízí prostředí. Tyto přístupové body jsou:  
  
-   **Instruktážní a další text v dialogových oknech.** Statický text, který poskytuje směry a vysvětlení, buď v Uživatelském rozhraní prostor nebo dostupné při přechodu myší nad ikonu Informační tip.  
  
-   **Nápověda F1** (pouze editor). V editoru Visual Studio můžete uživatele důvěřovat, že kdykoli po stisknutí klávesy F1 zobrazíte specifické pro aktuální výběr tématu nápovědy. Zajistěte, aby témata související s F1 informativní a vhodná.  
  
-   **Hypertextové odkazy na témata nápovědy.** Hypertextový odkaz v dialogovém okně, okno nástroje nebo návrhovou plochu, který spouští téma pomoct uživatele dozvědět další informace o technologii, schopností nebo informace o tom, jak provádění různých úloh.  
  
-   **Pomocník mechanismů uživatelského rozhraní, například inteligentních značek a sestavování dialogová okna.** Tyto mechanismy pomůže uživatele porozumět prvku uživatelského rozhraní nebo usnadnění úlohy, jako je například inteligentní značky nebo Tvůrce dialogová okna.  
  
-   **Tlačítka nápovědy k uživatelskému rozhraní** (zastaralé). Viditelné indikátoru v záhlaví, která poskytuje přístup k souvisejícím tématu nápovědy F1.  
  
### <a name="text"></a>Text  
  
#### <a name="instructional-and-supplemental-text-in-dialogs"></a>Instruktážní a další text v dialogových oknech  
 V dialogových oknech, které podporují složité úlohy může být potřeba poskytnout pokyny v uživatelském rozhraní, často v horní části dialogového okna nebo téměř komplexní ovládací prvky. V tématu [uživatelského rozhraní text a terminologie](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) podrobnosti o zápis stylu.  
  
#### <a name="infotips"></a>InfoTips  
 Podle požadavků často, může být příliš dlouhý na pozici zavedené v uživatelském rozhraní nebo mohou být užitečné pouze pro nové uživatele, se úplně jako zbytečné soubory pro zkušené uživatele. V takovém případě musí být umístěny instruktážní nebo informační text jako popisek pod tip.  
  
 InfoTips musí být umístěny téměř ovládacích prvků, se vztahují k a musí používat konkrétní informační tip ikonu, která dosud nerušivý znatelné.  
  
 ![Informační tip v sadě Visual Studio](../../extensibility/ux-guidelines/media/0601-d_infotip.png "0601 d_InfoTip")  
  
 **Příklad tip v sadě Visual Studio**  
  
### <a name="interactive-help-mechanisms"></a>Interaktivní mechanismy nápovědy  
  
#### <a name="f1-help"></a>F1 – nápověda  
 Nápověda F1 je vyžadován v editoru nebo návrhovou plochu, ale není jinde v prostředí Visual Studio.  
  
#### <a name="hyperlinks-to-help-topics"></a>Hypertextové odkazy na témata nápovědy  
 Hypertextové odkazy můžete použít k provedení akce, přejděte v prostředí IDE nebo spuštění nápovědy v prohlížeči. V tématu [uživatelského rozhraní text a terminologie](../../extensibility/ux-guidelines/ui-text-and-help-for-visual-studio.md#BKMK_UITextAndTerminology) podrobnosti o jazyka a 07.10.01 tlačítka a hypertextové odkazy pokyny visual a rozložení.  
  
#### <a name="help--buttons-in-dialog-title-bars-deprecated"></a>Nápověda [?] tlačítka v dialogovém okně záhlaví (zastaralé)  
 Ve většině případů nápovědy [?] tlačítka v záhlaví okna dialogová okna jsou zastaralé. Témata uživatelského rozhraní jsou již součástí našeho modelu doc, a proto nemusí být k příslušné téma propojit s. V podstatě tlačítko panelu název byl totéž jako Nápověda F1 a která už není nutné v dialogových oknech. V některých případech to pořád můžou použít jako ukazatel se další koncepční a procedurální informace k dispozici, i když hypertextové odkazy se běžně používají v novější uživatelského rozhraní.  
  
##### <a name="dialogs-created-through-the-environment"></a>Dialogová okna vytvořena prostřednictvím prostředí  
 Dialogová okna mnoho prostředí jsou vytvořeny pomocí **VBDialogBoxParam** funkce. Tato sdílená funkce byla aktualizována jako pomoc při přesunu **pomoci** tlačítko z dialogového okna a **?** tlačítko při zachování architekturu, která je zpětně kompatibilní a rozšiřitelné.  
  
 Konkrétně **VBDialogBoxParam** funkce zjistí šablony dialogového okna pro tlačítko s ID **IDHELP** (9) nebo popisek je **pomoci** nebo **& pomoci**. Pokud je nalezen tlačítko Nápověda, je skrytá a **ws_ex_contexthelp –** styl je přidán do dialogového okna, které se umístí **?** tlačítka v dialogovém okně záhlaví.  
  
 Když je vytvořen dialogové okno, nabízených oznámení proc dialogu do zásobníku a vyvolá dialogové okno s předem zpracování proc dialogové okno s názvem **DialogPreProc**. Když **?** Po kliknutí na tlačítko, odešle **WM_SYSCOMMAND** z **SC_CONTEXTHELP** do dialogového okna. **DialogPreProc** zaznamená tento příkaz a změní jeho **WM_HELP** zpráva, což je předán původní proc. dialogové okno  
  
 Většina dialogová okna vytvořit prostředí mít v dialogovém okně tlačítko Nápověda. Po zobrazení dialogového okna na tlačítko Nápověda je skrytý automaticky a pouze **?** tlačítko funguje. Pokud **?** tlačítko někdy odebrané nebo změněné v systému Windows, toto řešení umožňuje rychle přesunout zpátky na původní tlačítka Nápověda.  
  
 Toto řešení umožňuje čtyři předpoklady, které by mohly způsobit chyby:  
  
-   Dialogovém okně tlačítko Nápověda se **IDHELP** (9).  
  
-   Dialogové okno vypadá správné, když je skrytý na tlačítko Nápověda.  
  
-   Dialogové okno není nahraďte jeho winproc.  
  
-   Dialogové okno není vložených uvnitř jiné dialogové okno.  
  
 Pokud do dialogu se nachází v rámci msenv a nepoužívá **VBDialogBoxParam**, prozkoumat využití **VBDialogBoxParam** před implementací vlastní obslužnou rutinu.  
  
##### <a name="dialogs-created-through-other-packages"></a>Dialogová okna vytvořena prostřednictvím dalších balíčků  
 Můžete implementovat vlastní řešení pro dialogová okna, které se nacházejí mimo msenv. Pro třídy sdílené dialogového okna v vaší VSPackage zvažte přechod na tlačítko v záhlaví nebo implementaci obslužné rutiny na každý dialogu. Následující kód je kostře implementace můžete začít:  
  
```  
struct DLGPROCITEM  
{  
    FARPROC proc; // The info used to create the dialog.  
    DLGPROCITEM* procPrev;  
};  
  
DLGPROCITEM* g_dlgProcStack = NULL;  
  
// A dialog starter/wrapper function is used to push the new  
// dialog proc to the top of our dialog proc stack.  
  
int SomeDialogStarterFunction(hinst, id, proc, etc)  
{  
    if (g_dlgProcStack == NULL)  
    {  
        g_dlgProcStack = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = NULL;  
    }  
    else  
    {  
        DLGPROCITEM* procItem = new DLGPROCITEM;  
        g_dlgProcStack->procPrev = g_dlgProcStack;  
        g_dlgProcStack = procItem;  
    }  
}  
  
// Pop this dialog proc off the dialog proc stack.  
  
DialogBoxIndirectParam...(...)  
{  
    DLGPROCITEM* procItem = g_dlgProcStack->procPrev;  
    delete g_dlgProcStack;  
    g_dlgProcStack = procItem;  
}  
  
// A wrapper dialog procedure will allow us to capture the  
// SC_CONTEXTHELP button on the title bar from Windows and  
// forward it as a simple WM_HELP message back to the dialog.  
  
INT_PTR CALLBACK DialogPreProc(HWND hwndDlg, UINT uMsg,  
    WPARAM wParam, LPARAM lParam)  
{  
    if (uMsg == WM_SYSCOMMAND && wParam == SC_CONTEXTHELP)  
    {  
        uMsg = WM_HELP;  
        wParam = 0;  
        lParam = 0;  
    }  
    return CallWindowProc((WNDPROC)g_dlgProcStack->proc,  
        hwndDlg, uMsg, wParam, lParam);  
}  
```  
  
##### <a name="help-buttons-in-managed-code"></a>Tlačítka Nápověda ve spravovaném kódu  
 Přepisování výchozího chování tlačítko okno nadpis panelu Nápověda je snadné ve spravovaném kódu. Níže je kompletní ukázkovou aplikaci, která demonstruje toto chování. V podstatě, je nutné přepsat svého formuláře **WndProc** metoda a pak ještě efektivněji vypnout F1 – Nápověda požadavky, kdy **SC_CONTEXTHELP** je zachycen zprávy.  
  
```  
using System;  
using System.Windows.Forms;  
  
public class HelpForm : Form  
{  
    private const int SC_CONTEXTHELP = 0xF180;  
    private const int WM_SYSCOMMAND = 0x0112;  
  
    public HelpForm()  
    {  
        this.ClientSize = new System.Drawing.Size(300, 250);  
        this.HelpButton = true;  
        this.MaximizeBox = false;  
        this.MinimizeBox = false;  
        this.Name = "HelpForm";  
        this.Text = "Help Form";  
    }  
  
    protected override void WndProc(ref Message m)  
    {  
        if (m.Msg == WM_SYSCOMMAND && SC_CONTEXTHELP == (int)m.WParam)  
            ShowHelp();  
        else  
            base.WndProc(ref m);  
    }  
  
    private void ShowHelp()  
    {  
        MessageBox.Show("F1 Help goes here.");  
    }  
  
     [STAThread]  
    static void Main()  
    {  
        Application.EnableVisualStyles();  
        Application.EnableRTLMirroring();  
        Application.Run(new HelpForm());  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Písma a formátování pro sadu Visual Studio](../../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md)   
 [Rozložení pro sadu Visual Studio](../../extensibility/ux-guidelines/layout-for-visual-studio.md)   
 [Oznámení a postup pro sadu Visual Studio](../../extensibility/ux-guidelines/notifications-and-progress-for-visual-studio.md)