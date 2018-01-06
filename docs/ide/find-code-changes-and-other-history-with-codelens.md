---
title: "Nalezení změn kódu a další historie pomocí Codelensu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b454893c2d68b23d130d6ff38be493d988dfb1fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="find-code-changes-and-other-history-with-codelens"></a>Nalezení změn kódu a další historie pomocí CodeLensu

Soustředit na svou práci při můžete zjistit, co se stalo s kódu – bez opuštění editoru. Najděte odkazy a změn kódu, propojené chyby, pracovní položky, kód recenze a testování částí.

> [!NOTE]
> Codelensu je k dispozici pouze v edicích Visual Studio Enterprise a Visual Studio Professional. Není k dispozici v aplikaci Visual Studio Community edition.  

V tématu, kde a jak jednotlivé části kódu se používají ve vašem řešení:  

![Indikátory Codelensu v editoru kódu](../ide/media/codelensoverview.png "CodeLensOverview")  

Kontaktujte tým o změnách kódu bez opuštění editoru:  

![Codelensu & č. 45; Kontaktujte tým](../ide/media/codelensovervew2.png "CodeLensOvervew2")  

Chcete-li zvolit indikátory, které chcete zobrazit, nebo k Codelensu vypnutí a zapnutí, přejděte na **nástroje**, **možnosti**, **textového editoru**, **všechny jazyky** , **Codelensu**.  

## <a name="FindReferences"></a>Najít odkazy na váš kód

Budete potřebovat:

-  Visual Studio Enterprise nebo Visual Studio Professional

-  Kódu v jazyce Visual C# .NET nebo Visual Basic .NET

Vyberte **odkazy** ukazatele (**Alt + 2**). Pokud se zobrazí **0 odkazy**, budete mít žádné odkazy z kódu jazyka Visual C# nebo Visual Basic. To neobsahuje odkazy z jiných položek, jako jsou soubory XAML a ASPX.

![Codelensu & č. 45; Zvolte odkazy na ukazatele](../ide/media/codelensviewreferenceslist.png "CodeLensViewReferencesList")  

Chcete-li zobrazit odkazující kód, přesuňte ukazatel myši nad odkaz.  

![Codelensu & č. 45; Prohlížení odkaz](../ide/media/codelensviewreferencespeekreference.png "CodeLensViewReferencesPeekReference")  

Chcete-li otevřít soubor obsahující odkaz, dvakrát klikněte na odkaz.  

Zobrazit vztahy mezi tento kód a jeho odkazy [vytvoření mapy kódu](../modeling/map-dependencies-across-your-solutions.md) a zvolte **zobrazit všechny odkazy** v místní nabídce map kódu.

![Codelensu & č. 45; Odkazy na mapě kódu](../ide/media/codelensmappedreferences.png "CodeLensMappedReferences")  

## <a name="FindCodeHistory"></a>Najít váš kód historie a propojené položky

Zkontrolujte historii vašeho kódu a zjistěte, co se stalo s vašeho kódu. Nebo můžete zkontrolovat změny, než jste sloučeny do kódu, proto můžete lépe pochopit, jak změny v ostatní větve zůstanou mohou ovlivnit váš kód.

Budete potřebovat:

- Visual Studio Enterprise nebo Visual Studio Professional

- Team Foundation Server 2013 nebo novější, Visual Studio Team Services nebo Git

- [Lync 2010 nebo novější nebo Skype pro firmy](http://technet.microsoft.com/en-us/lync), kontaktujte tým z editoru kódu  

Pro Visual C# .NET nebo Visual Basic .NET kód, který je uložen s verzí Team Foundation (TFVC) nebo Git, získat Codelensu podrobnosti na úrovni třídy a metody (*kód. element úrovni* indikátory). Pokud je úložiště Git hostovaná v TfGit, také získáte odkazy na pracovní položky sady TFS.  

![Element kódu & č. 45; úrovně indikátory](../ide/media/codelenselementlevelindicators.png "CodeLensElementLevelIndicators")  

Pro všechny ostatní typy souborů, které lze otevřít v editoru Visual Studio se zobrazí podrobnosti o Codelensu pro celý soubor na jednom místě v dolní části okna (*souborů* indikátory).

![Soubor &#45; úrovně indikátory Codelensu](../ide/media/almcodelensfilelevelindicators.png "ALMCodeLensFileLevelIndicators")  

Chcete-li vybrat indikátory pomocí klávesnice, stiskněte a podržte **ALT** klíč k zobrazení souvisejících číslicemi.  

![Stiskněte klávesu ALT čísla přístup klávesnice](../ide/media/codelensaltkeyindicators.png "CodeLensAltKeyIndicators")  

### <a name="find-changes-in-your-code"></a>Najít změny v kódu

Zjistí, kdo změnili C# nebo kód jazyka Visual Basic a změny, které budou provedeny v úrovni kódu elementu indikátory. Je to, co vidíte, že použijete verzí Team Foundation (TFVC) v Team Foundation Server nebo Visual Studio Team Services.  

![Codelensu: Get změnit historie kódu v TFVC](../ide/media/codelenscodechanges.png "CodeLensCodeChanges")  

Výchozí hodnota je časové období posledních 12 měsíců. Pokud váš kód je uložený na serveru Team Foundation Server, můžete to změnit spuštěním [TFSConfig příkaz](http://msdn.microsoft.com/en-us/94424190-3b6b-4f33-a6b6-5807f4225b62) s [codeindex – příkaz](../ide/codeindex-command.md) a **/indexHistoryPeriod** příznak.  

Chcete-li zobrazit podrobné historie všechny změny, včetně těch, které z více než rokem, zvolte **zobrazit všechny změny souboru**.  

![Zobrazit všechny změny kódu](../ide/media/codelensshowsallchanges.png "CodeLensShowsAllChanges")  

Otevře se okno historie pro změn.  

![Okno historie pro všechny změny kódu](../ide/media/codelenscodechangeshistory.png "CodeLensCodeChangesHistory")  

Když jsou vaše soubory v úložišti Git a zvolte kód. element úrovni změny indikátoru, je to, co vidíte.  

![Codelensu: Get změnit historie kódu v úložišti Git](../ide/media/codelenscodechangesgit.png "CodeLensCodeChangesGit")  

V souboru úrovni indikátory v dolní části okna Najít změny pro celý soubor (s výjimkou soubory C# a Visual Basic).  

![Codelensu: Získání kódu podrobnosti souboru](../ide/media/codelensfilelevel.png "CodeLensFileLevel")  

Chcete-li získat další informace o změně, klikněte pravým tlačítkem na danou položku. V závislosti na tom, jestli používáte TFVC nebo Git získáte řadu možností porovnat verzích souboru, zobrazení podrobností a sledovat sadu změn, získat vybrané verzi souboru a e-mailu autora tato změna. Některé z těchto podrobností se zobrazí v Team Explorer.  

Zobrazí se také, kdo časem změnit váš kód. To vám může pomoct najít vzory v změny vašeho týmu a vyhodnocení jejich dopad.  

![Codelensu: Viz kód změní historie jako graf](../ide/media/codelens.png "Codelensu")  

#### <a name="find-changes-in-your-current-branch"></a>Najít změny v aktuální větvi

Předpokládejme, že má váš tým více větví – hlavní větve a vývoj podřízené - snížit riziko nejnovější stabilní kódu:  

![Codelensu: Najít, když byla součástí vašeho kódu podmínky](../ide/media/codelensfirstbranchconceptual.png "CodeLensFirstBranchConceptual")  

Najít, kolik lidí změnit kódu a kolik změny (**Alt + 6**) v hlavní větve:  

![Codelensu: Najít, kolik změny ve vaší firemní pobočky](../ide/media/codelensbranchchanges.png "CodeLensBranchChanges")  

#### <a name="find-when-your-code-was-branched"></a>Najít, když byla součástí vašeho kódu podmínky

Přejděte do kódu v podřízené větve, například na Dev větev. Zvolte indikátor změn (**Alt + 6**):  

![Codelensu: Najít, když byla součástí vašeho kódu podmínky](../ide/media/codelensfirstbranchscreenshot.png "CodeLensFirstBranchScreenshot")  

#### <a name="find-incoming-changes-from-other-branches"></a>Najít příchozí změny od jiných poboček

![Codelensu: Nalezení změn kódu v ostatní větve zůstanou](../ide/media/codelensbranchchangecheckinconceptual.png "CodeLensBranchChangeCheckinConceptual")  

.. Tato oprava chyb v Dev větev zde takto:

![Codelensu: Změny se změnami do jiné větvi](../ide/media/codelensbranchchangedevscreenshot.png "CodeLensBranchChangeDevScreenshot")  

Tato změna můžete zkontrolovat aniž byste museli opustit váš aktuální větev (hlavní):  

![Codelensu: Viz příchozí změnit z jiné větve](../ide/media/codelensbranchchangemainscreenshot.png "CodeLensBranchChangeMainScreenshot")  

#### <a name="find-when-changes-got-merged"></a>Najít, když získali sloučit změny

Proto můžete zjistit, jaké změny jsou součástí větev:  

![Codelensu & č. 45; Sloučit změny mezi větví](../ide/media/codelensbranchmergedconceptual.png "CodeLensBranchMergedConceptual")  

Například kódu v hlavní pobočce má nyní oprava chyby z větve Dev:  

![Codelensu & č. 45; Slučování chagnes mezi větví](../ide/media/codelensbranchmergedscreenshot.png "CodeLensBranchMergedScreenshot")  

#### <a name="compare-an-incoming-change-with-your-local-version-shift--f10"></a>Porovnání s vaší místní verze (Shift + F10) příchozí změnit

![Codelensu: Porovnání příchozí změny s místní](../ide/media/codelensbranchincomingchangemenu.png "CodeLensBranchIncomingChangeMenu")  

Klikněte dvakrát na sadu změn.

#### <a name="what-do-the-icons-mean"></a>Co znamenají ikony?

|**Ikona**|**Pokud tato změna pocházejí z?**|  
|--------------|-----------------------------------------|  
|![Codelensu: Změnit z aktuální větve ikonu](../ide/media/codelensbranchcurrenticon.png "CodeLensBranchCurrentIcon")|Aktuální větve|  
|![Codelensu & č. 45; Změnit z nadřazené větve ikonu](../ide/media/codelensbranchparenticon.png "CodeLensBranchParentIcon")|Nadřazené větve|  
|![Codelensu: Změna z podřízené větve ikonu](../ide/media/codelensbranchchildicon.png "CodeLensBranchChildIcon")|Podřízené větve|  
|![Codelensu & č. 45; Změní ze sdílené větve ikonu](../ide/media/codelensbranchpeericon.png "CodeLensBranchPeerIcon")|Větev peer|  
|![Codelensu & č. 45; Změnit z větve další tokeny ikonu](../ide/media/codelensbranchfurtherawayicon.png "CodeLensBranchFurtherAwayIcon")|Větev další rychle než nadřazené, podřízené nebo partnera|  
|![Codelensu: Sloučení z nadřazené ikonu](../ide/media/codelensbranchmergefromparenticon.png "CodeLensBranchMergeFromParentIcon")|Sloučení z větve nadřazené do podřízené větve|
|![Codelensu: Sloučení z podřízené větve ikonu](../ide/media/codelensbranchmergefromchildicon.png "CodeLensBranchMergeFromChildIcon")|Sloučení z podřízené větve do nadřazené větve|  
|![Codelensu: Sloučení z nesouvisejících větve ikonu](../ide/media/codelensbranchmergefromunrelatedicon.png "CodeLensBranchMergeFromUnrelatedIcon")|Sloučení z nesouvisejících firemní pobočky (bez základu sloučení)|  

### <a name="find-linked-work-items"></a>Najít propojené pracovní položky

![Codelensu & č. 45; Hledání pracovních položek pro konkrétní kód](../ide/media/codelensworkitems.png "CodeLensWorkItems")  

### <a name="find-linked-code-reviews"></a>Najít recenze propojené kódu

![Codelensu & č. 45; Zobrazit žádosti revize kódu](../ide/media/codelenscodereviews.png "CodeLensCodeReviews")  

### <a name="find-linked-bugs"></a>Najít odkazovaný chyby

![Codelensu & č. 45; Nalézt chyby propojené s změn](../ide/media/codelensbugschangesets.png "CodeLensBugsChangesets")  

### <a name="contact-the-owner-of-an-item"></a>Obraťte se na vlastníka položky

![Obraťte se na vlastníka položky](../ide/media/codelenscontactitemowner.png "CodeLensContactItemOwner")  

Otevřete místní nabídku pro položku, kterou chcete zobrazit kontaktní možnosti. Pokud máte Lync nebo Skype pro firmy nainstalovaná, zobrazí se tyto možnosti:  

![Obraťte se na možnosti pro položku](../ide/media/codelensitemcontactmenu.png "CodeLensItemContactMenu")  

##  <a name="FindRunUnitTests"></a>Najít testování částí kódu

Další informace o testování částí, které existují kódu bez otevření Průzkumníka testů. Budete potřebovat:  

-   Visual Studio Enterprise nebo Visual Studio Professional  
  
-   Kódu v jazyce Visual C# .NET nebo Visual Basic .NET  
  
-   A [projektu testování částí](../test/unit-test-your-code.md) má testů částí kódu aplikace  
  
1.  Přejděte ke kódu aplikace, který má testování částí.  
  
2.  Zkontrolujte testy pro tento kód (**Alt + 3**).  
  
     ![Codelensu & č. 45; Vyberte stav testu v editoru kódu](../ide/media/codelenschoosetestindicator.png "CodeLensChooseTestIndicator")  
  
3.  Pokud se zobrazí ikona upozornění ![Codelensu & č. 45; Testování částí ještě nebyl spuštěn upozornění](../ide/media/codelenstestwarningicon.png "CodeLensTestWarningIcon"), spusťte testy.  
  
     ![Codelensu & č. 45; Zobrazit testování částí ještě není spuštěna](../ide/media/codelenstestsnotyetrun.png "CodeLensTestsNotYetRun")  
  
4.  Ke kontrole testovací definice, dvakrát klikněte na položku testu v okně Codelensu ukazatele k otevření souboru kódu v editoru.  
  
     ![Codelensu & č. 45; Přejděte na jednotku testovací definice](../ide/media/codelensunittestdefinition.png "CodeLensUnitTestDefinition")  
  
5.  Zkontrolujte výsledky test. Zvolte indikátor stavu testu (![Codelensu & č. 45; Testování částí se nezdařilo ikonu](../ide/media/codelenstestfailedicon.png "CodeLensTestFailedIcon") nebo ![Codelensu & č. 45; Testování částí předán ikonu](../ide/media/codelenstestpassedicon.png "CodeLensTestPassedIcon")), nebo stiskněte klávesu **Alt + 1**.  
  
     ![Codelensu & č. 45; Najdete v části výsledků testů jednotek](../ide/media/codelensunittestresult.png "CodeLensUnitTestResult")  
  
6.  Pokud chcete zobrazit, kolik lidí změnit tento test, který změnil tento test nebo byly provedeny změny kolik tento test [najít váš kód historie a propojené položky](#FindCodeHistory).

##  <a name="QA"></a>MODUL OTÁZKY A ODPOVĚDI

###  <a name="ChangeOrTurnOff"></a>Otázka: jak lze zapnout Codelensu nebo vypnout? Nebo zvolte které indikátory zobrazíte?

**Odpověď:** můžete zapnout indikátory nebo vypnout, s výjimkou odkazy na ukazatele. Přejděte na **nástroje**, **možnosti**, **textového editoru**, **všechny jazyky**, **Codelensu**.  
  
 Když na značky jsou zapnuté, můžete také otevřít možnosti Codelensu z ukazatele.  
  
 ![Codelensu & č. 45; Zapnutí indikátory nebo vypnutí](../ide/media/codelensturnoffonindicatorsfromcode.png "CodeLensTurnOffOnIndicatorsFromCode")  
  
 Zapněte Codelensu souborů indikátory zapnout a vypnout pomocí ikony dvojitou v dolní části okna editoru.  
  
 ![& Zapnout souborů č. 45; úrovně indikátory zapnout a vypnout](../ide/media/codelensfilelevelonandoff.png "CodeLensFileLevelOnAndOff")  
  
###  <a name="NoIndicators"></a>Otázka: kde je Codelensu?

**Odpověď:** Codelensu se zobrazí v kódu Visual C# .NET a Visual Basic .NET na úrovni metodu, třídu, indexer a vlastnost. Codelensu se zobrazí na úrovni souborů pro všechny ostatní typy souborů.

- Ujistěte se, že je zapnutý Codelensu. Přejděte na **nástroje**, **možnosti**, **textového editoru**, **všechny jazyky**, **Codelensu**.  
  
- Pokud váš kód je uložený v sadě TFS, ujistěte se, že kód indexování zapnutá pomocí [codeindex – příkaz](../ide/codeindex-command.md) s [příkazu TFS Config](http://msdn.microsoft.com/en-us/94424190-3b6b-4f33-a6b6-5807f4225b62).  

- Indikátory související s aplikací TFS se zobrazí pouze v případě, že jsou pracovní položky propojeny s kódem a máte oprávnění otevírat propojené pracovní položky. [Zkontrolujte, zda máte oprávnění člen týmu.](http://msdn.microsoft.com/en-us/f58805de-ba61-4d09-8f2d-d3ab9662ecfd)  

- Indikátory test jednotky se nezobrazí, když kód aplikace nemá testování částí. Indikátory stavu testu se automaticky zobrazí v projektech testů. Pokud znáte kód aplikace má testování částí, že testovací indikátory nezobrazí, zkuste jej sestavit řešení (**Ctrl + Shift + B**).  

### <a name="q-why-dont-i-see-the-work-item-details-for-a-commit"></a>Otázka: Proč nevidím v pracovní položce. podrobnosti pro potvrzení?

**Odpověď:** této situaci může dojít, protože Codelensu nelze nalézt pracovních položek v sadě TFS. Zkontrolujte, že jste připojení k týmovému projektu, který má těch, které pracovní položky a zda máte oprávnění k zobrazení těch, které pracovní položky. To může také dojít, pokud popis potvrzení má nesprávné informace o ID pracovní položky v sadě TFS.  

###  <a name="NoLync"></a>Otázka: Proč nevidím indikátory Lync nebo Skype?

**Odpověď:** se nezobrazí, pokud nejsou přihlášeni Lync nebo Skype pro firmy, není k dispozici jednu z těchto nainstalován nebo nemáte podporovanou konfiguraci. Ale může i dál posílat e-mailu:  

![Codelensu & č. 45; Vlastník kontaktní změn prostřednictvím e-mailu](../ide/media/codelenscodesendmailchangesetnolync1.png "CodeLensCodeSendMailChangesetNoLync1")  

 **Které aplikace Lync a Skype konfigurace jsou podporovány?**

-   Skype pro firmy (32bitová nebo 64bitová verze)  

-   Aplikace Lync 2010 nebo novější samostatně (32bitová nebo 64bitová verze), ale aplikace Lync 2013 Basic není s Windows 8.1  

Codelensu nepodporuje s různými verzemi aplikace Lync nebo nainstalovat Skype. Nemusí být lokalizovaný pro všechny její lokalizované verze sady Visual Studio.  

### <a name="q-how-do-i-change-the-font-and-color-for-codelens"></a>Otázka: jak změnit písmo a barvy u Codelensu?

**Odpověď:** přejít na **nástroje**, **možnosti**, **prostředí**, **písma a barev**.  

![Codelensu & č. 45; Změňte nastavení písma a barvy](../ide/media/codelensoptionsfontscolorssettings.png "CodeLensOptionsFontsColorsSettings")  

Použití klávesnice:

1.  Stiskněte klávesu **Alt + T + O** otevřete **možnosti** pole.  

2.  Stiskněte klávesu **šipka nahoru** nebo **šipka dolů** přejít na **prostředí** uzlu, stiskněte **šipka doleva** rozbalte uzel.  

3.  Stiskněte klávesu **šipka dolů** přejít na **písma a barev**.  

4.  Stiskněte klávesu **KARTĚ** přejít na **zobrazit nastavení pro** seznamu a potom stiskněte klávesu **šipka dolů** vyberte **Codelensu**.  

### <a name="q-can-i-move-the-codelens-heads-up-display"></a>Otázka: Lze přesunout pohotové zobrazení funkce CodeLens?

**Odpověď:** Ano, zvolte ![Codelensu & č. 45; Ukotvení jako okno](../ide/media/codelensdockwindow.png "CodeLensDockWindow") chcete ukotvit Codelensu jako okna.  

![Ukotvení okna indikátor Codelensu](../ide/media/codelensselectdockwindow.png "CodeLensSelectDockWindow")  

![Okno ukotveného odkazy Codelensu](../ide/media/codelensreferencesdockedwindow.png "CodeLensReferencesDockedWindow")  

### <a name="q-how-do-i-refresh-the-indicators"></a>Otázka: Jak mohu aktualizovat indikátory?

**Odpověď:** to závisí na ukazatele:  

-   **Odkazy na**: Tento ukazatel se automaticky aktualizuje, když se změní kód. Pokud je tento ukazatel ukotven jako samostatné okno, obnovte indikátoru ručně tady:  

     ![Codelensu & č. 45; Ukotvení jako okno](../ide/media/codelensviewreferencesdocked.png "CodeLensViewReferencesDocked")  

-   **Tým**: Obnovte tyto ukazatele ručně tady:  

     ![Codelensu & č. 45; Aktualizujte indikátory](../ide/media/codelensrefreshindicatorsfromcode.png "CodeLensRefreshIndicatorsFromCode")  

-   **Test**: [najít testování částí kódu](#FindRunUnitTests) aktualizovat tento ukazatel.  

###  <a name="LocalVersion"></a>Otázka: co je "Místní verze"?

**Odpověď:** **místní verze** šipku odkazuje na poslední sadu změn ve vaší místní verzi tohoto souboru. Pokud je serveru novější změn, se objeví nad nebo pod **místní verze** šipku, v závislosti na pořadí slouží k řazení změn.  

### <a name="q-can-i-manage-how-codelens-processes-code-to-show-history-and-linked-items"></a>Otázka: je možné spravovat, jak Codelensu zpracuje kód pro zobrazení historie a propojené položky?

**Odpověď:** Ano, pokud kód v sadě TFS, použijte [codeindex – příkaz](../ide/codeindex-command.md) s [příkazu TFS Config](http://msdn.microsoft.com/en-us/94424190-3b6b-4f33-a6b6-5807f4225b62).

## <a name="see-also"></a>Viz také

[Psaní kódu v editoru](../ide/writing-code-in-the-code-and-text-editor.md)