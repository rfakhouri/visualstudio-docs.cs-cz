---
title: "Návod: Identifikace problémy s výkonem | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profiling tools, walkthroughs
- performance tools, walkthroughs
- performance, analyzing
- profiling applications, walkthroughs
ms.assetid: 36f6f123-0c14-4763-99c3-bd60ecb95b87
caps.latest.revision: "53"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: da961d153713c996c6f057e7bb0366c747c87205
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-identifying-performance-problems"></a>Návod: Identifikace problémy s výkonem
Tento návod ukazuje, jak do profilu aplikace identifikovat problémy s výkonem.  
  
 V tomto návodu se projděte proces profilace spravované aplikaci a pomocí vzorkování a instrumentace k izolování a identifikovat problémy s výkonem v aplikaci.  
  
 V tomto návodu se postupujte takto:  
  
-   Profil aplikace pomocí metody vzorkování.  
  
-   Analýza jen Vzorkovaná profilování výsledků najděte a opravte problémy výkonem.  
  
-   Profil aplikace pomocí metody instrumentace.  
  
-   Analýza instrumentovaného profilování výsledků najděte a opravte problémy výkonem.  
  
## <a name="prerequisites"></a>Požadavky  
  
-   Zprostředkující znalosti jazyka C#.  
  
-   Kopii [peopletrax – ukázka](../profiling/peopletrax-sample-profiling-tools.md).  
  
 Při práci s informacemi poskytované profilace, je nejlepší mít ladění symbol informace, které jsou k dispozici.  
  
## <a name="profiling-by-using-the-sampling-method"></a>Profilace pomocí metody vzorkování  
 Vzorkování je profilování metoda, podle kterého procesu dotyčném pravidelně dotazování k určení active funkce. Výsledná data poskytuje počet jak často byl dotyčném funkce nad zásobníku volání při procesu byla vzorků.  
  
#### <a name="to-profile-an-application-by-using-the-sampling-method"></a>Do profilu aplikace pomocí metody vzorkování  
  
1.  Otevřete [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] s oprávněními správce. Je nutné profilace jako správce.  
  
2.  Otevřete PeopleTrax řešení.  
  
     Peopletrax – řešení teď naplní Průzkumníku řešení.  
  
3.  Nastavte na hodnotu konfigurace projektu **verze**.  
  
     Sestavení pro vydání byste měli používat ke zjištění problémy s výkonem v aplikaci. Sestavení pro vydání se doporučuje pro vytváření profilů, protože sestavení ladicí verze má další informace zkompilovány do ní, které může nepříznivě ovlivnit výkon a není ilustrují přesně problémy s výkonem.  
  
4.  Na **analyzovat** nabídce vyberte možnost **výkonu profileru**, pak vyberte **Průvodce výkonu**a potom vyberte **spustit**.  
  
     Zobrazí se Průvodce výkonu.  
  
5.  Zajistěte, aby **vzorkování procesoru (doporučeno)** je vybrána a potom klikněte na **Další**.  
  
6.  V **aplikaci, pro kterou chcete cílit pro profilace**vyberte PeopleTrax a pak klikněte na tlačítko **Další**.  
  
     [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]sestavení projektu a začne do profilu aplikace. **PeopleTrax** se zobrazí v okně aplikace.  
  
7.  Klikněte na tlačítko **získat osoby**.  
  
8.  Klikněte na tlačítko **ExportData**.  
  
     Otevře Poznámkový blok a zobrazí nový soubor, který obsahuje data exportovaná z **PeopleTrax**.  
  
9. Zavřete poznámkový blok a pak zavřete **PeopleTrax** aplikace.  
  
     Profileru vytvoří data profilování (\*.vsp) souboru, jsou uvedené v části sestavy okno Prohlížeč výkonu název souboru a automaticky načte **Souhrn** zobrazení datového souboru v hlavním okně [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
#### <a name="to-analyze-sampled-profiling-results"></a>Analýza vzorků profilace výsledky  
  
1.  Souhrnné zobrazení zobrazí časová osa využití procesoru v průběhu vytváření profilů spustit, **aktivní trase** seznam, který představuje větev stromu volání aplikace, který byl nejvíce aktivní a seznam  **Funguje to nejvíce jednotlivé pracovní** který ukazuje funkce, které byly nejčastěji vzorkovat při provádění kódu ve svých vlastních tělo funkce.  
  
     Zkontrolujte **aktivní trase** seznamu a Všimněte si, že je metoda PeopleNS.People.GetNames nejbližší na konec seznamu peopletrax – funkce. Jeho pozice je vhodným kandidátem pro analýzu. Klikněte na název funkce zobrazíte podrobnosti o GetNames v **podrobností funkce** zobrazení.  
  
2.  **Podrobností funkce** zobrazení obsahuje dvě okna. Okna distribuční poskytuje grafické zobrazení práci funkcí, podle funkce, které ji volat a příspěvku funkcí, které volal funkci na počet instancí, které byly vzorků. Funkce, která je zaměření pro zobrazení kliknutím na název funkce, můžete změnit. Například můžete kliknout na PeopleNS.People.GetPeople aby GetPeople vybrané funkce.  
  
     **Zobrazení kódu funkce** okně se zobrazí zdrojového kódu pro funkce, pokud je k dispozici a zvýrazňuje nejnákladnější řádků v vybrané funkce. Pokud je vybraná GetNames, uvidíte, že tato funkce řetězec načteme prostředky aplikace a pak používá <xref:System.IO.StringReader> přidání každý řádek v řetězec, který má <xref:System.Collections.ArrayList>. Není jednoznačný způsob, jak optimalizovat tuto funkci.  
  
3.  Protože PeopleNS.People.GetPeople pouze volající GetNames, klikněte na tlačítko GetPeople v okně distribuční náklady a zkontrolujte jeho kód. Tato metoda vrátí <xref:System.Collections.ArrayList> PersonInformationNS.PersonInformation objektů z názvy osoby a vyprodukované GetNames společností. GetNames však nazývá dvakrát pokaždé, když je vytvořen objekt PersonInformation. Uvidíte, že metoda lze snadno optimalizovat vytvořením seznamy jenom jednou na začátku metodu a indexování do těchto seznamů během vytvoření smyčky PersonInformation.  
  
4.  Je k dispozici alternativní verze životního GetPeople s ukázkového kódu aplikace a můžete volat funkci optimalizované přidáním symbol Podmíněná kompilace pro vlastnosti sestavení. V okně Průzkumníku řešení klikněte pravým tlačítkem na projekt osoby a pak klikněte na tlačítko **vlastnosti**. Klikněte na tlačítko **sestavení** v nabídce stránku vlastností a pak zadejte **OPTIMIZED_GETPEOPLE** do textového pole symbol Podmíněná kompilace. Optimalizovaná verze GetPeople nahradí původní metody v další sestavení.  
  
5.  Znovu spusťte výkonnostní relace. Na panelu nástrojů výkonu Explorer, klikněte na tlačítko **spouštění profilování**. Klikněte na tlačítko **získat osoby** a pak klikněte na **Export dat**. Zavřete okno Poznámkový blok, který se zobrazí a zavřete aplikaci Trax osoby.  
  
     Vygenerování nového datového souboru profilování a **Souhrn** o nová data se zobrazí v zobrazení [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] hlavní okno.  
  
6.  K porovnání dvou profilování běží, vyberte dvě datové soubory v prohlížeč výkonu, pravým tlačítkem myši na a pak klikněte na tlačítko **porovnat sestavy pro zvýšení výkonu**. Zobrazí okno sestavy porovnání [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] hlavní okno. **Rozdílů** sloupci se zobrazuje změnu v hodnotě výkonu funkce z dříve **směrného plánu** hodnotu novější **porovnání** hodnotu. Můžete vybrat k porovnání z **sloupec** rozevíracím seznamu. Vyberte **včetně ukázky %**.  
  
     Všimněte si, že metody GetPeople a GetNames zobrazit zvýšení značnou část výkonu.  
  
## <a name="profiling-by-using-the-instrumentation-method"></a>Profilace pomocí metody instrumentace  
 Instrumentace je profilování metoda, ve kterém profileru vloží funkce testu do speciálně integrovaný verze PROFILOVANÉHO binárních souborů. Sondy shromažďovat informace o časování na vstupu a výstupu funkcí v instrumentovaného moduly a na všechny lokality volání v těchto funkcí. Instrumentace proces je užitečný pro zkoumání problémy související s vstupně výstupních operací, jako je například zápis na disk a komunikaci přes síť. Instrumentace poskytuje podrobnější informace než vzorkování, ale je rušivější v procesu spuštění a způsobuje větší objem režie. Instrumentované binární soubory jsou také větší než ladění nebo verzi binárních souborů a není určena pro nasazení.  
  
 V této části návodu použijeme metody instrumentace ke zjištění další kód, který jsme můžete optimalizovat v PeopleTrax aplikaci, kterou jsme profilovaným dříve. Pomocí filtru časová osa zobrazení se souhrnnými informacemi se zaměříme Naše analýzy na scénáři export dat v naší PROFILOVANÉHO aplikaci, ve kterém je seznam lidí, kteří zapisují do souboru poznámkového bloku.  
  
#### <a name="to-profile-an-existing-application-by-using-the-instrumentation-method"></a>Do profilu existující aplikace pomocí metody instrumentace  
  
1.  V případě potřeby otevřete PeopleTrax aplikaci v sadě Visual Studio.  
  
     Ujistěte se, že spustíte jako správce a že je konfigurace sestavení řešení je nastavená na **verze**.  
  
2.  V Průzkumníku výkonu, klikněte na tlačítko **instrumentace**.  
  
3.  Na panelu nástrojů Prohlížeč výkonu, klikněte na **spouštění profilování**.  
  
     Profileru sestavení projektu a začne do profilu aplikace. Zobrazí se okno aplikace PeopleTrax.  
  
4.  Klikněte na tlačítko **získat osoby**.  
  
     Datová mřížka PeopleTrax naplní s daty.  
  
5.  Počkejte asi 10 sekund a pak klikněte na tlačítko **Export dat**.  
  
     **Poznámkový blok** spustí a zobrazí nový soubor, který obsahuje seznam osoby z PeopleTrax. Čekání na umožňuje snadno identifikovat data exportovat postup pro filtrování.  
  
6.  Zavřete **Poznámkový blok**a pak zavřete **PeopleTrax** aplikace.  
  
     [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]vytváří sestavu relace výkonu (*.vsp).  
  
#### <a name="to-analyze-instrumented-profiling-results"></a>K analýze instrumentovány profilace výsledky  
  
1.  Časová osa grafu z **Souhrn** zobrazení sestavy uvádí využití procesoru programu za celou dobu vytváření profilů spuštění. Operace exportu dat musí být velké ve špičce nebo plató na pravé straně grafu. Jsme můžete filtrovat výkonnostní relace zobrazit a analyzovat pouze data, která nebyla shromážděna v exportu. Kliknutím vlevo bodu v grafu, kde začíná data exportu. Na pravé straně operace, klikněte na tlačítko znovu. Pak klikněte na tlačítko **filtrovat podle výběr** v seznamu odkazů na pravé straně časovou osu.  
  
     **Aktivní trase** stromu ukazují, že <xref:System.String.Concat%2A> metoda, která je volána metodou PeopleTrax.Form1.ExportData spotřebovává vysoké procento času. Protože **System.String.Concat** je také v horní části **funkce s nejvíce jednotlivé pracovní** seznamu zkrátil čas nutný ve funkci je pravděpodobně bod optimalizace.  
  
2.  Klikněte dvakrát na **System.String.Concat** v některém ze souhrnné tabulky zobrazíte další informace v zobrazení podrobností funkce.  
  
3.  Uvidíte, že PeopleTrax.Form1.ExportData je jedinou metodou, která volá Concat. Klikněte na tlačítko **PeopleTrax.Form1.ExportData** v **volání funkce** seznam pro výběr metody je jako cíl zobrazení podrobností funkce.  
  
4.  Zkontrolujte metodu v okně zobrazení Kód funkce. Všimněte si, že neexistují žádné literálu volání **System.String.Concat**. Místo toho jsou několika způsoby operand +=, který nahradí volání do kompilátoru **System.String.Concat**. Všechny změny na řetězec v rozhraní .NET Framework způsobit řetězec nové tak, aby se přidělit. Zahrnuje rozhraní .NET Framework <xref:System.Text.StringBuilder> třídu, která je optimalizovaná pro zřetězení řetězců  
  
5.  Pokud chcete tento problém oblasti nahradit optimalizovaný kód, přidejte do projektu PeopleTrax OPTIMIZED_EXPORTDATA jako symbol Podmíněná kompilace.  
  
6.  V Průzkumníku řešení klikněte pravým tlačítkem na projekt PeopleTrax a pak klikněte na tlačítko **vlastnosti**.  
  
     Se zobrazí vlastnosti formuláře PeopleTrax projektu.  
  
7.  Klikněte **sestavení** kartě.  
  
8.  V **podmíněné kompilace symboly** textového pole, typ **OPTIMIZED_EXPORTDATA**.  
  
9. Zavřete formulář vlastností projektu a zvolte **uložit všechny** po zobrazení výzvy.  
  
 Když spustíte aplikaci znovu, zobrazí se označený vylepšení výkonu. Spuštění relace profilování znovu, se doporučuje i v případě, že nejsou viditelné vylepšení výkonu uživatele. Kontrola data po vyřešení problému je důležité, protože první problém mohou skrývat jinému problému.  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../profiling/overviews-performance-tools.md)   
 [Začínáme](../profiling/getting-started-with-performance-tools.md)   
 [/ Z7, / zi, /ZI (formát ladicích informací)](/cpp/build/reference/z7-zi-zi-debug-information-format)