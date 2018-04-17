---
title: Nalezení změn kódu a další historie pomocí Codelensu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e20081320109e5334360d0cc1f38b187f05d574
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="find-code-changes-and-other-history-with-codelens"></a>Nalezení změn kódu a další historie pomocí CodeLensu

Soustředit na svou práci při můžete zjistit, co se stalo s kódu – bez opuštění editoru. Najděte odkazy a změn kódu, propojené chyby, pracovní položky, kód recenze a testování částí.

> [!NOTE]
> Codelensu je k dispozici pouze v edicích Visual Studio Enterprise a Visual Studio Professional. Není k dispozici v aplikaci Visual Studio Community edition.  

V tématu, kde a jak jednotlivé části kódu se používají ve vašem řešení:  

![Indikátory Codelensu v editoru kódu](../ide/media/codelensoverview.png "CodeLensOverview")  

Kontaktujte tým o změnách kódu bez opuštění editoru:  

![Codelensu &#45; kontaktujte tým](../ide/media/codelensovervew2.png "CodeLensOvervew2")  

Chcete-li zvolit indikátory, které chcete zobrazit, nebo k Codelensu vypnutí a zapnutí, přejděte na **nástroje** > **možnosti** > **textového editoru**  >  **Všechny jazyky** > **Codelensu**.  

## <a name="FindReferences"></a> Najít odkazy na váš kód

Budete potřebovat:

-  Visual Studio Enterprise nebo Visual Studio Professional

-  Kód jazyka C# nebo Visual Basic

Vyberte **odkazy** ukazatele (**Alt + 2**). Pokud se zobrazí **0 odkazy**, budete mít žádné odkazy z kódu jazyka C# nebo Visual Basic. To neobsahuje odkazy z jiných položek, jako **XAML** a **.aspx** soubory.

![Codelensu &#45; zvolte odkazy na ukazatele](../ide/media/codelensviewreferenceslist.png "CodeLensViewReferencesList")  

Chcete-li zobrazit odkazující kód, přesuňte ukazatel myši nad odkaz.  

![Codelensu &#45; prohlížet odkaz](../ide/media/codelensviewreferencespeekreference.png "CodeLensViewReferencesPeekReference")  

Chcete-li otevřít soubor obsahující odkaz, dvakrát klikněte na odkaz.  

Zobrazit vztahy mezi tento kód a jeho odkazy [vytvoření mapy kódu](../modeling/map-dependencies-across-your-solutions.md) a zvolte **zobrazit všechny odkazy** v místní nabídce map kódu.

![Codelensu &#45; odkazy na mapě kódu](../ide/media/codelensmappedreferences.png "CodeLensMappedReferences")  

## <a name="FindCodeHistory"></a> Najít váš kód historie a propojené položky

Zkontrolujte historii vašeho kódu a zjistěte, co se stalo s vašeho kódu. Nebo můžete zkontrolovat změny, než jste sloučeny do kódu, proto můžete lépe pochopit, jak změny v ostatní větve zůstanou mohou ovlivnit váš kód.

Budete potřebovat:

- Visual Studio Enterprise nebo Visual Studio Professional

- Team Foundation Server 2013 nebo novější, Visual Studio Team Services nebo Git

- [Lync 2010 nebo novější nebo Skype pro firmy](https://technet.microsoft.com/office/dn788773), kontaktujte tým z editoru kódu

Pro C# nebo Visual Basic kód, který je uložen s verzí Team Foundation (TFVC) nebo Git, získat Codelensu podrobnosti na úrovni třídy a metody (*kód. element úrovni* indikátory). Pokud je úložiště Git hostovaná v TfGit, také získáte odkazy na pracovní položky sady TFS.  

![Element kódu&#45;úrovně indikátory](../ide/media/codelenselementlevelindicators.png "CodeLensElementLevelIndicators")  

Pro všechny ostatní typy souborů, které lze otevřít v editoru Visual Studio se zobrazí podrobnosti o Codelensu pro celý soubor na jednom místě v dolní části okna (*souborů* indikátory).

![Soubor&#45;úrovně indikátory Codelensu](../ide/media/almcodelensfilelevelindicators.png "ALMCodeLensFileLevelIndicators")  

Chcete-li vybrat indikátory pomocí klávesnice, stiskněte a podržte **Alt** klíč k zobrazení souvisejících číslicemi.  

![Stiskněte klávesu Alt čísla přístup klávesnice](../ide/media/codelensaltkeyindicators.png "CodeLensAltKeyIndicators")  

### <a name="find-changes-in-your-code"></a>Najít změny v kódu

Zjistí, kdo změnili C# nebo kód jazyka Visual Basic a změny, které budou provedeny v úrovni kódu elementu indikátory. Je to, co vidíte, že použijete verzí Team Foundation (TFVC) v Team Foundation Server nebo Visual Studio Team Services.  

![Codelensu: Get změnit historie kódu v TFVC](../ide/media/codelenscodechanges.png "CodeLensCodeChanges")  

Výchozí hodnota je časové období posledních 12 měsíců. Pokud váš kód je uložený na serveru Team Foundation Server, můžete to změnit spuštěním [TFSConfig příkaz](/vsts/tfs-server/command-line/tfsconfig-cmd) s [codeindex – příkaz](../ide/codeindex-command.md) a **/indexHistoryPeriod** příznak.

Chcete-li zobrazit podrobné historie všechny změny, včetně těch, které z více než rokem, zvolte **zobrazit všechny změny souboru**.  

![Zobrazit všechny změny kódu](../ide/media/codelensshowsallchanges.png "CodeLensShowsAllChanges")  

Tím se otevře **historie** okna pro změn.  

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

![Codelensu &#45; sloučit změny mezi větví](../ide/media/codelensbranchmergedconceptual.png "CodeLensBranchMergedConceptual")  

Například kódu v hlavní pobočce má nyní oprava chyby z větve Dev:  

![Codelensu &#45; sloučit změny mezi větví](../ide/media/codelensbranchmergedscreenshot.png "CodeLensBranchMergedScreenshot")  

#### <a name="compare-an-incoming-change-with-your-local-version-shift--f10"></a>Porovnání s vaší místní verze (Shift + F10) příchozí změnit

![Codelensu: Porovnání příchozí změny s místní](../ide/media/codelensbranchincomingchangemenu.png "CodeLensBranchIncomingChangeMenu")  

Klikněte dvakrát na sadu změn.

#### <a name="what-do-the-icons-mean"></a>Co znamenají ikony?

|**Ikona**|**Pokud tato změna pocházejí z?**|  
|--------------|-----------------------------------------|  
|![Codelensu: Změnit z aktuální větve ikonu](../ide/media/codelensbranchcurrenticon.png "CodeLensBranchCurrentIcon")|Aktuální větve|  
|![Codelensu &#45; změnit z nadřazené větve ikonu](../ide/media/codelensbranchparenticon.png "CodeLensBranchParentIcon")|Nadřazené větve|  
|![Codelensu: Změna z podřízené větve ikonu](../ide/media/codelensbranchchildicon.png "CodeLensBranchChildIcon")|Podřízené větve|  
|![Codelensu &#45; změnit z větve ikona sdílené](../ide/media/codelensbranchpeericon.png "CodeLensBranchPeerIcon")|Větev peer|  
|![Codelensu &#45; změnit z větve další tokeny ikonu](../ide/media/codelensbranchfurtherawayicon.png "CodeLensBranchFurtherAwayIcon")|Větev další rychle než nadřazené, podřízené nebo partnera|  
|![Codelensu: Sloučení z nadřazené ikonu](../ide/media/codelensbranchmergefromparenticon.png "CodeLensBranchMergeFromParentIcon")|Sloučení z větve nadřazené do podřízené větve|
|![Codelensu: Sloučení z podřízené větve ikonu](../ide/media/codelensbranchmergefromchildicon.png "CodeLensBranchMergeFromChildIcon")|Sloučení z podřízené větve do nadřazené větve|  
|![Codelensu: Sloučení z nesouvisejících větve ikonu](../ide/media/codelensbranchmergefromunrelatedicon.png "CodeLensBranchMergeFromUnrelatedIcon")|Sloučení z nesouvisejících firemní pobočky (bez základu sloučení)|  

### <a name="find-linked-work-items"></a>Najít propojené pracovní položky

![Codelensu &#45; najít pracovních položek pro konkrétního kódu](../ide/media/codelensworkitems.png "CodeLensWorkItems")  

### <a name="find-linked-code-reviews"></a>Najít recenze propojené kódu

![Codelensu &#45; zobrazit žádosti revize kódu](../ide/media/codelenscodereviews.png "CodeLensCodeReviews")  

### <a name="find-linked-bugs"></a>Najít odkazovaný chyby

![Codelensu &#45; nalézt chyby propojené s změn](../ide/media/codelensbugschangesets.png "CodeLensBugsChangesets")  

### <a name="contact-the-owner-of-an-item"></a>Obraťte se na vlastníka položky

![Obraťte se na vlastníka položky](../ide/media/codelenscontactitemowner.png "CodeLensContactItemOwner")  

Otevřete místní nabídku pro položku, kterou chcete zobrazit kontaktní možnosti. Pokud máte Lync nebo Skype pro firmy nainstalovaná, zobrazí se tyto možnosti:  

![Obraťte se na možnosti pro položku](../ide/media/codelensitemcontactmenu.png "CodeLensItemContactMenu")  

##  <a name="FindRunUnitTests"></a> Najít testování částí kódu

Další informace o testování částí, které existují kódu bez otevírání **Průzkumníka testů**. Budete potřebovat:  

-   Visual Studio Enterprise nebo Visual Studio Professional  
  
-   Kód jazyka C# nebo Visual Basic  
  
-   A [projektu testování částí](../test/unit-test-your-code.md) má testů částí kódu aplikace  
  
1.  Přejděte ke kódu aplikace, který má testování částí.  
  
2.  Zkontrolujte testy pro tento kód (**Alt + 3**).  
  
     ![Codelensu &#45; stav testu zvolte v editoru kódu](../ide/media/codelenschoosetestindicator.png "CodeLensChooseTestIndicator")  
  
3.  Pokud se zobrazí ikona upozornění ![Codelensu &#45; testování částí ještě nebyl spuštěn upozornění](../ide/media/codelenstestwarningicon.png "CodeLensTestWarningIcon"), spusťte testy.  
  
     ![Codelensu &#45; testování částí zobrazení nejde spustit ještě](../ide/media/codelenstestsnotyetrun.png "CodeLensTestsNotYetRun")  
  
4.  Ke kontrole testovací definice, dvakrát klikněte na položku testu v okně Codelensu ukazatele k otevření souboru kódu v editoru.  
  
     ![Codelensu &#45; přechod na definici test jednotky](../ide/media/codelensunittestdefinition.png "CodeLensUnitTestDefinition")  
  
5.  Zkontrolujte výsledky test. Zvolte indikátor stavu testu (![Codelensu &#45; testování částí se nezdařilo ikonu](../ide/media/codelenstestfailedicon.png "CodeLensTestFailedIcon") nebo ![Codelensu &#45; jednotky test proběhl úspěšně. ikona] (../ide/media/codelenstestpassedicon.png "CodeLensTestPassedIcon")), nebo stiskněte klávesu **Alt + 1**.  
  
     ![Codelensu &#45; najdete v části výsledků testů jednotek](../ide/media/codelensunittestresult.png "CodeLensUnitTestResult")  
  
6.  Pokud chcete zobrazit, kolik lidí změnit tento test, který změnil tento test nebo byly provedeny změny kolik tento test [najít váš kód historie a propojené položky](#FindCodeHistory).

##  <a name="QA"></a> Q & A

###  <a name="ChangeOrTurnOff"></a> Otázka: jak lze zapnout Codelensu nebo vypnout? Nebo zvolte které indikátory zobrazíte?

**Odpověď:** můžete zapnout indikátory nebo vypnout, s výjimkou odkazy na ukazatele. Přejděte na **nástroje** > **možnosti** > **textového editoru** > **všechny jazyky**  >  **Codelensu**.  
  
 Když na značky jsou zapnuté, můžete také otevřít možnosti Codelensu z ukazatele.  
  
 ![Codelensu &#45; zapnutí indikátory nebo vypnutí](../ide/media/codelensturnoffonindicatorsfromcode.png "CodeLensTurnOffOnIndicatorsFromCode")  
  
 Zapněte Codelensu souborů indikátory zapnout a vypnout pomocí ikony dvojitou v dolní části okna editoru.  
  
 ![Zapnout souboru&#45;úrovně indikátory zapnout a vypnout](../ide/media/codelensfilelevelonandoff.png "CodeLensFileLevelOnAndOff")  
  
###  <a name="NoIndicators"></a> Otázka: kde je Codelensu?

**Odpověď:** Codelensu se zobrazí v kódu jazyka C# a Visual Basic na úrovni metodu, třídu, indexer a vlastnost. Codelensu se zobrazí na úrovni souborů pro všechny ostatní typy souborů.

- Ujistěte se, že je zapnutý Codelensu. Přejděte na **nástroje**, **možnosti**, **textového editoru**, **všechny jazyky**, **Codelensu**.  

- Pokud váš kód je uložený v sadě TFS, ujistěte se, že kód indexování zapnutá pomocí [codeindex – příkaz](../ide/codeindex-command.md) s [příkazu TFS Config](/vsts/tfs-server/command-line/tfsconfig-cmd).

- Indikátory související s aplikací TFS se zobrazí pouze v případě, že jsou pracovní položky propojeny s kódem a máte oprávnění otevírat propojené pracovní položky. [Zkontrolujte, zda máte oprávnění členů týmu](/vsts/work/scale/multiple-teams).

- Indikátory test jednotky se nezobrazí, když kód aplikace nemá testování částí. Indikátory stavu testu se automaticky zobrazí v projektech testů. Pokud znáte kód aplikace má testování částí, že testovací indikátory nezobrazí, zkuste jej sestavit řešení (**Ctrl + Shift + B**).

### <a name="q-why-dont-i-see-the-work-item-details-for-a-commit"></a>Otázka: Proč nevidím v pracovní položce. podrobnosti pro potvrzení?

**Odpověď:** této situaci může dojít, protože Codelensu nelze nalézt pracovních položek v sadě TFS. Zkontrolujte, že jste připojení k týmovému projektu, který má těch, které pracovní položky a zda máte oprávnění k zobrazení těch, které pracovní položky. To může také dojít, pokud popis potvrzení má nesprávné informace o ID pracovní položky v sadě TFS.  

###  <a name="NoLync"></a> Otázka: Proč nevidím indikátory Lync nebo Skype?

**Odpověď:** se nezobrazí, pokud nejsou přihlášeni Lync nebo Skype pro firmy, není k dispozici jednu z těchto nainstalován nebo nemáte podporovanou konfiguraci. Ale může i dál posílat e-mailu:  

![Codelensu &#45; obraťte se na vlastníka změn prostřednictvím e-mailu](../ide/media/codelenscodesendmailchangesetnolync1.png "CodeLensCodeSendMailChangesetNoLync1")  

 **Které aplikace Lync a Skype konfigurace jsou podporovány?**

-   Skype pro firmy (32bitová nebo 64bitová verze)  

-   Aplikace Lync 2010 nebo novější samostatně (32bitová nebo 64bitová verze), ale aplikace Lync 2013 Basic není s Windows 8.1  

Codelensu nepodporuje s různými verzemi aplikace Lync nebo nainstalovat Skype. Nemusí být lokalizovaný pro všechny její lokalizované verze sady Visual Studio.  

### <a name="q-how-do-i-change-the-font-and-color-for-codelens"></a>Otázka: jak změnit písmo a barvy u Codelensu?

**Odpověď:** přejít na **nástroje** > **možnosti** > **prostředí** > **písma a barev**.  

![Codelensu &#45; změnit nastavení písma a barvy](../ide/media/codelensoptionsfontscolorssettings.png "CodeLensOptionsFontsColorsSettings")  

Použití klávesnice:

1.  Stiskněte klávesu **Alt + T + O** otevřete **možnosti** pole.  

2.  Stiskněte klávesu **šipka nahoru** nebo **šipka dolů** přejít na **prostředí** uzlu, stiskněte **šipka doleva** rozbalte uzel.  

3.  Stiskněte klávesu **šipka dolů** přejít na **písma a barev**.  

4.  Stiskněte klávesu **kartě** přejít na **zobrazit nastavení pro** seznamu a potom stiskněte klávesu **šipka dolů** vyberte **Codelensu**.  

### <a name="q-can-i-move-the-codelens-heads-up-display"></a>Otázka: Lze přesunout pohotové zobrazení funkce CodeLens?

**Odpověď:** Ano, zvolte ![Codelensu &#45; ukotvení jako okna](../ide/media/codelensdockwindow.png "CodeLensDockWindow") chcete ukotvit Codelensu jako okna.  

![Ukotvení okna indikátor Codelensu](../ide/media/codelensselectdockwindow.png "CodeLensSelectDockWindow")  

![Okno ukotveného odkazy Codelensu](../ide/media/codelensreferencesdockedwindow.png "CodeLensReferencesDockedWindow")  

### <a name="q-how-do-i-refresh-the-indicators"></a>Otázka: Jak mohu aktualizovat indikátory?

**Odpověď:** to závisí na ukazatele:  

-   **Odkazy na**: Tento ukazatel se automaticky aktualizuje, když se změní kód. Pokud je tento ukazatel ukotven jako samostatné okno, obnovte indikátoru ručně tady:  

     ![Codelensu &#45; ukotvení jako okno](../ide/media/codelensviewreferencesdocked.png "CodeLensViewReferencesDocked")  

-   **Tým**: Obnovte tyto ukazatele ručně tady:  

     ![Codelensu &#45; aktualizovat indikátory](../ide/media/codelensrefreshindicatorsfromcode.png "CodeLensRefreshIndicatorsFromCode")  

-   **Test**: [najít testování částí kódu](#FindRunUnitTests) aktualizovat tento ukazatel.  

###  <a name="LocalVersion"></a> Otázka: co je "Místní verze"?

**Odpověď:** **místní verze** šipku odkazuje na poslední sadu změn ve vaší místní verzi tohoto souboru. Pokud je serveru novější změn, se objeví nad nebo pod **místní verze** šipku, v závislosti na pořadí slouží k řazení změn.

### <a name="q-can-i-manage-how-codelens-processes-code-to-show-history-and-linked-items"></a>Otázka: je možné spravovat, jak Codelensu zpracuje kód pro zobrazení historie a propojené položky?

**Odpověď:** Ano, pokud kód v sadě TFS, použijte [codeindex – příkaz](../ide/codeindex-command.md) s [příkazu TFS Config](/vsts/tfs-server/command-line/tfsconfig-cmd).

## <a name="see-also"></a>Viz také

[Psaní kódu v editoru](../ide/writing-code-in-the-code-and-text-editor.md)