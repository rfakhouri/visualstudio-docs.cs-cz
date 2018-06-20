---
title: Nalezení změn kódu a další historie pomocí CodeLensu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02f0c8dd142f9517dcaef3a40d613d43b8e650a3
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238337"
---
# <a name="find-code-changes-and-other-history-with-codelens"></a>Nalezení změn kódu a další historie pomocí CodeLensu

Codelensu umožňuje soustředit na svou práci při můžete zjistit, co se stalo s kódu&ndash;bez opuštění editoru. Můžete najít odkazy na kód, změny kódu, propojené chyby, pracovní položky, kód recenze a testování částí.

> [!NOTE]
> Codelensu je k dispozici pouze v edicích Visual Studio Enterprise a Visual Studio Professional. Není k dispozici v aplikaci Visual Studio Community edition.

V tématu, kde a jak jednotlivé části kódu se používají ve vašem řešení:

![Indikátory Codelensu v editoru kódu](../ide/media/codelens-overview.png)

Kontaktujte tým o změnách kódu bez opuštění editoru:

![Codelensu - kontaktujte tým](../ide/media/codelens-contact-info.png)

Chcete-li zvolit indikátory, které chcete zobrazit, nebo k Codelensu vypnutí a zapnutí, přejděte na **nástroje** > **možnosti** > **textového editoru**  >  **Všechny jazyky** > **Codelensu**.

## <a name="find-references-to-your-code"></a>Najít odkazy na váš kód

Odkazy můžete najít v C# nebo kód jazyka Visual Basic.

1. Vyberte **odkazy** indikátoru, nebo klikněte na tlačítko **Alt**+**2**.

   ![Odkazy na Codelensu](../ide/media/codelens-view-references.png)

   > [!NOTE]
   > Pokud se bude zobrazovat indikátoru **0 odkazy**, budete mít žádné odkazy z kódu jazyka C# nebo Visual Basic. Však může existovat odkazy v ostatních položkách, jako *XAML* a *.aspx* soubory.

2. Chcete-li zobrazit kód odkazující myši přes odkaz v seznamu.

   ![Codelensu – odkaz funkce Náhled](../ide/media/codelens-peek-reference.png)

3. Chcete-li otevřít soubor, který obsahuje odkaz na, dvakrát klikněte na odkaz.

### <a name="code-maps"></a>Mapy kódu

Zobrazit vztahy mezi kód a jeho odkazy [vytvoření mapy kódu](../modeling/map-dependencies-across-your-solutions.md). V místní nabídce Mapa kódu, vyberte **zobrazit všechny odkazy**.

![Codelensu – odkazy na mapě kódu](../ide/media/codelensmappedreferences.png)

## <a name="a-namefind-code-historyfind-changes-in-your-code"></a><a name="find-code-history"/>Najít změny v kódu

Zkontrolujte historii vašeho kódu a zjistěte, co se stalo s vašeho kódu. Nebo můžete zkontrolovat změny, než jste sloučeny do kódu, proto můžete lépe pochopit, jak změny v ostatní větve zůstanou mohou ovlivnit váš kód.

Potřebuješ:

- Visual Studio Enterprise nebo Visual Studio Professional

- Team Foundation Server 2013 nebo novější, Visual Studio Team Services nebo Git

- [Skype pro firmy](/skypeforbusiness/), nebo Lync 2010 nebo novější, kontaktujte tým z editoru kódu

Pro kód C# nebo Visual Basic, který je uložená se Team Foundation verze ovládacího prvku (TFVC) nebo Git, získat Codelensu podrobnosti na úrovni třídy a metody (*kód úrovni element* indikátory). Pokud je úložiště Git hostovaná v TfGit, také získáte odkazy na pracovní položky sady TFS.

![Kód úrovni elementu indikátory](../ide/media/codelens-element-level-indicators.png)

Pro soubor typy jiné než *.cs* nebo *VB*, získat podrobnosti o Codelensu pro celý soubor na jednom místě v dolní části okna (*souborů* indikátory).

![Indikátory Codelensu úrovni souborů](../ide/media/almcodelensfilelevelindicators.png)

### <a name="code-element-level-indicators"></a>Kód úrovni elementu indikátory

Kód úrovni elementu indikátory umožňuje sledovat, kdo změny kódu a jaké změny budou provedeny. Úroveň elementu indikátory kódu jsou k dispozici pro kód C# a Visual Basic.

Je to, co vidíte, že použijete Team Foundation verze ovládacího prvku (TFVC) v Team Foundation Server nebo Visual Studio Team Services:

![Codelensu: Get historie změn kódu v TFVC](../ide/media/codelens-code-changes.png)

Výchozí hodnota je časové období posledních 12 měsíců. Pokud váš kód je uložený na serveru Team Foundation Server, můžete změnit časové období spuštěním [TFSConfig příkaz](/tfs/server/ref/command-line/tfsconfig-cmd) s [codeindex – příkaz](../ide/codeindex-command.md) a **/indexHistoryPeriod**příznak.

Chcete-li zobrazit podrobné historie všechny změny, včetně těch, které z více než rokem, zvolte **zobrazit všechny změny souboru**:

![Zobrazit všechny změny kódu](../ide/media/codelens-show-all-file-changes.png)

**Historie** otevře se okno:

![Okno historie pro všechny změny kódu](../ide/media/codelenscodechangeshistory.png)

Když jsou vaše soubory v úložišti Git a zvolíte indikátor element úrovni změn kódu, je to, co se zobrazí:

![Codelensu: Get historie změn kódu v úložišti Git](../ide/media/codelens-code-changes-git.png)

### <a name="file-level-indicators"></a>Ukazatele na úrovni souborů

Najděte změny pro celý soubor na úrovni souborů značky v dolní části okna.

![Codelensu: Získání kódu podrobnosti souboru](../ide/media/codelens-file-level.png)

> [!NOTE]
> Indikátory úrovni souboru nejsou k dispozici pro soubory C# a Visual Basic.

Chcete-li získat další informace o změně, klikněte pravým tlačítkem na danou položku. V závislosti na tom, jestli používáte TFVC nebo Git existuje možnost porovnat verzích souboru, zobrazení podrobností a sledovat sadu změn, získat vybrané verzi souboru a e-mailu autora tato změna. Některé z těchto podrobnosti se zobrazují v **Team Explorer**.

Zobrazí se také, kdo časem změnit váš kód. To vám může pomoct najít vzory v změny vašeho týmu a vyhodnocení jejich dopad.

![Codelensu: Najdete v části historie změn kódu jako grafu.](../ide/media/codelens.png)

### <a name="find-changes-in-your-current-branch"></a>Najít změny v aktuální větvi

Váš tým může mít více větví, například hlavní větve a podřízené vývoj větev, abyste snížili riziko nejnovější stabilní kódu.

![Codelensu: Najít, když byla součástí vašeho kódu podmínky](../ide/media/codelensfirstbranchconceptual.png)

Můžete zjistit, kolik lidí změnit kódu a kolik změny byly provedeny v hlavní větve stisknutím **Alt**+**6**:

![Codelensu: Kolik změny v větev najít](../ide/media/codelens-branch-changes.png)

### <a name="find-when-your-code-was-branched"></a>Najít, když byla součástí vašeho kódu podmínky

Najít, když byla součástí vašeho kódu podmínky, přejděte do kódu v pobočce podřízené. Pak vyberte **změny** indikátoru nebo klikněte na tlačítko**Alt**+**6**:

![Codelensu: Najít, když byla součástí vašeho kódu podmínky](../ide/media/codelens-first-branch.png)

### <a name="find-incoming-changes-from-other-branches"></a>Najít příchozí změny od jiných poboček

![Codelensu: Změny kódu v ostatní větve zůstanou najít](../ide/media/codelensbranchchangecheckinconceptual.png)

Příchozí změny si můžete prohlédnout. Na následujícím snímku obrazovky oprava chyb byl proveden v pobočce "Dev":

![Codelensu: Změna zaškrtnutí do jiné větve](../ide/media/codelens-branch-changes-dev.png)

Změny můžete zkontrolovat aniž byste museli opustit váš aktuální větev ("hlavní"):

![Codelensu: Viz příchozí změnit z jiné větve](../ide/media/codelens-branch-changes-main.png)

### <a name="find-when-changes-got-merged"></a>Najít, když získali sloučit změny

Když získali sloučit změny, můžete zjistit, můžete určit, jaké změny jsou součástí větev:

![Codelensu - sloučené změny mezi větví](../ide/media/codelensbranchmergedconceptual.png)

Například kódu v hlavní pobočce má nyní oprava chyby z větve "Dev":

![Codelensu - sloučené změny mezi větví](../ide/media/codelens-branch-merged.png)

### <a name="compare-an-incoming-change-with-your-local-version"></a>Porovnání s místní verze příchozí změnit

Porovnání s místní verze příchozí změnit stisknutím **Shift**+**F10**, nebo dvojitým kliknutím na sadu změn.

![Codelensu: Porovnání s místní příchozí změnit](../ide/media/codelens-branch-incoming-change-menu.png)

### <a name="branch-icons"></a>Větev ikony

Na ikonu v **větve** sloupec vám říká vztah větev do větve v práci.

|**Ikona**|**Tato změna pochází:**|
|--------------|-----------------------------------------|
|![Codelensu: Změnit z aktuální větve ikony](../ide/media/codelensbranchcurrenticon.png)|Aktuální větve|
|![Codelensu: Změna z nadřazené větve ikony](../ide/media/codelensbranchparenticon.png)|Nadřazené větve|
|![Codelensu: Změna z podřízené větve ikony](../ide/media/codelensbranchchildicon.png)|Podřízené větve|
|![Codelensu: Změny z větve ikona sdílené](../ide/media/codelensbranchpeericon.png)|Větev peer|
|![Codelensu: Změny z větve další tokeny ikony](../ide/media/codelensbranchfurtherawayicon.png)|Větev další rychle než nadřazené, podřízené nebo partnera|
|![Codelensu: Sloučení z nadřazené ikony](../ide/media/codelensbranchmergefromparenticon.png)|Sloučení z větve nadřazené do podřízené větve|
|![Codelensu: Sloučení z podřízené větve ikony](../ide/media/codelensbranchmergefromchildicon.png)|Sloučení z podřízené větve do nadřazené větve|
|![Codelensu: Sloučení z nesouvisejících větve ikony](../ide/media/codelensbranchmergefromunrelatedicon.png)|Sloučení z nesouvisejících firemní pobočky (bez základu sloučení)|

## <a name="linked-work-items"></a>Propojené pracovní položky

Hledání propojené pracovních položek výběrem **pracovní položky** indikátoru nebo stisknutím kombinace kláves **Alt**+**8**.

![Codelensu - najít pracovní položky pro konkrétního kódu](../ide/media/codelens-work-items.png)

## <a name="linked-code-reviews"></a>Zkontroluje propojené kódu

Najít odkazovaný kód recenze výběrem **zkontroluje** indikátoru. Chcete-li použít klávesnici, podržte klávesu **Alt** klíče a potom stiskněte klávesu **šipku vlevo** nebo **šipku vpravo** přejděte možnosti ukazatele.

![Zkontrolujte požadavky Codelensu - zobrazení kódu](../ide/media/codelens-code-reviews.png)

## <a name="linked-bugs"></a>Propojené chyby

Najít odkazovaný chyby výběrem **chyby** indikátoru nebo stisknutím kombinace kláves **Alt**+**7**.

![Codelensu - nalézt chyby propojené s změn](../ide/media/codelens-bugs-changesets.png)

## <a name="contact-the-owner-of-an-item"></a>Obraťte se na vlastníka položky

Najít Autor položky výběrem **autoři** indikátoru nebo stisknutím kombinace kláves **Alt**+**5**.

![Obraťte se na vlastníka položky](../ide/media/codelens-contact-item-owner.png)

Otevřete místní nabídku pro položku, kterou chcete zobrazit kontaktní možnosti. Pokud máte Lync nebo Skype pro firmy nainstalovaná, zobrazí se tyto možnosti:

![Obraťte se na možnosti pro položku](../ide/media/codelens-item-contact-menu.png)

## <a name="associated-unit-tests"></a>Testování částí přidružený

Testy jednotek, které existují můžete zjistit kódu C# nebo Visual Basic bez otevírání **Průzkumníka testů**.

1. Přejděte do kódu aplikace, který je spojen [jednotka testovacího kódu](../test/unit-test-your-code.md).

2. Pokud máte ještě není, sestavte aplikaci načíst indikátory testovací Codelensu. Zajistěte, aby [zjišťování podle integrovaný sestavení](../test/test-explorer-faq.md#3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on) je zapnutý.

3. Zkontrolujte testy pro kód stisknutím **Alt**+**3**.

     ![Zvolte Codelensu - stav testu v editoru kódu](../ide/media/codelens-choose-test-indicator.png)

4. Pokud se zobrazí ikona upozornění ![Ikona upozornění](../ide/media/codelenstestwarningicon.png), testy nebyly spustit ještě je proto spustit.

     ![Codelensu – testování částí zobrazení není ještě spuštěna](../ide/media/codelens-tests-not-yet-run.png)

5. Ke kontrole testovací definice, dvakrát klikněte na položku testu v okně Codelensu ukazatele k otevření souboru kódu v editoru.

     ![Codelensu - přechod na definici testů jednotek](../ide/media/codelens-unit-test-definition.png)

6. A zkontrolovat výsledky test, zvolte indikátor stavu testu (![ikona selhání testu](../ide/media/codelenstestfailedicon.png) nebo ![test proběhl ikonu](../ide/media/codelenstestpassedicon.png)), nebo stiskněte klávesu **Alt**+**1**.

     ![Codelensu – viz výsledků testů jednotek](../ide/media/codelens-unit-test-result.png)

7. Pokud chcete zobrazit, kolik lidí změnit tento test, který změnil tento test nebo byly provedeny změny kolik tento test [najít váš kód historie](#find-code-history) a propojené položky.

## <a name="keyboard-shortcuts"></a>Klávesové zkratky

Chcete-li vybrat indikátory pomocí klávesnice, stiskněte a podržte **Alt** klíče zobrazit související číslo klíče a pak stiskněte klávesu číslo, které odpovídá indikátoru, kterou chcete vybrat.

![Čísla přístup klávesnice](../ide/media/codelens-alt-keys.png)

> [!NOTE]
> Chcete-li vybrat **zkontroluje** indikátoru, podržte stisknutou klávesu **Alt** při pomocí klávesy se šipkami vlevo a vpravo procházejte.

## <a name="q--a"></a>Dotazy a odpovědi

### <a name="q-how-do-i-turn-codelens-off-or-on-or-choose-which-indicators-to-see"></a>Otázka: jak zapnout Codelensu nebo vypnout, nebo zvolte které indikátory zobrazíte?

**Odpověď:** můžete zapnout indikátory nebo vypnout, s výjimkou odkazy na ukazatele. Přejděte na **nástroje** > **možnosti** > **textového editoru** > **všechny jazyky**  >  **Codelensu**.

Když na značky jsou zapnuté, můžete také otevřít možnosti Codelensu z ukazatele.

![Codelensu - indikátory zapnout nebo vypnout](../ide/media/codelensturnoffonindicatorsfromcode.png)

Zapněte Codelensu souborů indikátory zapnout a vypnout pomocí ikony dvojitou v dolní části okna editoru.

![Zapnout indikátory souborů zapnout a vypnout](../ide/media/codelensfilelevelonandoff.png)

### <a name="q-where-is-codelens"></a>Otázka: kde je Codelensu?

**Odpověď:** Codelensu se zobrazí v kódu jazyka C# a Visual Basic na úrovni metodu, třídu, indexer a vlastnost. Codelensu se zobrazí na úrovni souborů pro všechny ostatní typy souborů.

- Ujistěte se, že je zapnutý Codelensu. Přejděte na **nástroje** > **možnosti** > **textového editoru** > **všechny jazyky**  >  **Codelensu**.

- Pokud váš kód je uložený v sadě TFS, ujistěte se, že kód indexování zapnutá pomocí [codeindex – příkaz](../ide/codeindex-command.md) s [příkazu TFS Config](/tfs/server/ref/command-line/tfsconfig-cmd).

- Indikátory související s aplikací TFS se zobrazí pouze v případě, že jsou pracovní položky propojeny s kódem a máte oprávnění otevírat propojené pracovní položky. Potvrďte, že máte [team oprávnění členů](/vsts/work/scale/multiple-teams).

- Indikátory test jednotky se nezobrazí, když kód aplikace nemá testování částí. Indikátory stavu testu se automaticky zobrazí v projektech testů. Pokud znáte kód aplikace má testování částí, že testovací indikátory nezobrazí, zkuste jej sestavit řešení (**Ctrl**+**Shift**+**B**).

### <a name="q-why-dont-i-see-the-work-item-details-for-a-commit"></a>Otázka: Proč nevidím v pracovní položce. podrobnosti pro potvrzení?

**Odpověď:** této situaci může dojít, protože Codelensu nelze nalézt pracovních položek v sadě TFS. Zkontrolujte, že jste připojení k týmovému projektu, který má těch, které pracovní položky, a zda máte oprávnění k zobrazení těch, které pracovní položky. Podrobnosti o položkách pracovní nemusí také nezobrazovat Pokud popis potvrzení má nesprávné informace o ID pracovní položky v sadě TFS.

### <a name="q-why-dont-i-see-the-skype-indicators"></a>Otázka: Proč nevidím indikátory Skype?

**Odpověď:** indikátory Skype se nezobrazí, pokud nejste do Skype pro firmy, není k dispozici je nainstalována, nebo nemáte podporovanou konfiguraci. Však může i dál posílat e-mailu:

![Codelensu - obraťte se na vlastníka změn prostřednictvím e-mailu](../ide/media/codelenscodesendmailchangesetnolync1.png)

**Které Skype a Lync konfigurace jsou podporovány?**

- Skype pro firmy (32bitová nebo 64bitová verze)

- Aplikace Lync 2010 nebo novější samostatně (32bitová nebo 64bitová verze), ale aplikace Lync 2013 Basic není s Windows 8.1

Codelensu nepodporuje s různými verzemi aplikace Lync nebo nainstalovat Skype. Nemusí být lokalizovaný pro všechny její lokalizované verze sady Visual Studio.

### <a name="q-how-do-i-change-the-font-and-color-for-codelens"></a>Otázka: jak změnit písmo a barvy u Codelensu?

**Odpověď:** přejít na **nástroje** > **možnosti** > **prostředí** > **písma a barev**.

![Codelensu - změnit nastavení písma a barvy](../ide/media/codelensoptionsfontscolorssettings.png)

Použití klávesnice:

1. Stiskněte klávesu **Alt**+**T**+**O** otevřete **možnosti** dialogové okno.

2. Stiskněte klávesu **šipka nahoru** nebo **šipka dolů** přejít na **prostředí** uzlu, stiskněte **šipka doleva** rozbalte uzel.

3. Stiskněte klávesu **šipka dolů** přejít na **písma a barev**.

4. Stiskněte klávesu **kartě** přejít na **zobrazit nastavení pro** seznamu a potom stiskněte klávesu **šipka dolů** vyberte **Codelensu**.

### <a name="q-can-i-move-the-codelens-heads-up-display"></a>Otázka: Lze přesunout pohotové zobrazení funkce CodeLens?

**Odpověď:** Ano, zvolte ![ikonu ukotvení](../ide/media/codelensdockwindow.png) chcete ukotvit Codelensu jako okna.

![Ukotvení tlačítka v okně indikátor Codelensu](../ide/media/codelensselectdockwindow.png)

![Okno ukotveného Codelensu odkazy](../ide/media/codelensreferencesdockedwindow.png)

### <a name="q-how-do-i-refresh-the-indicators"></a>Otázka: Jak mohu aktualizovat indikátory?

**Odpověď:** to závisí na ukazatele:

- **Odkazy na**: Tento ukazatel se automaticky aktualizuje, když se změní kód. Pokud **odkazy** indikátor ukotven jako samostatné okno, obnovte indikátoru výběrem **aktualizovat**:

     ![Aktualizujte tlačítko v odkazech na Codelensu](../ide/media/codelensviewreferencesdocked.png)

- **Tým**: aktualizovat tyto ukazatele výběrem **aktualizovat indikátory Team Codelensu** v místní nabídce:

     ![Aktualizujte položku nabídky indikátory Team Codelensu](../ide/media/codelensrefreshindicatorsfromcode.png)

- **Test**: [najít testování částí kódu](#Find-unit-tests-for-your-code) aktualizace **Test** indikátoru.

### <a name="q-whats-local-version"></a>Otázka: co je "Místní verze"?

**Odpověď:** **místní verze** šipku odkazuje na poslední sadu změn ve vaší místní verzi souboru. Pokud je serveru novější změn, se objeví nad nebo pod **místní verze** šipku, v závislosti na pořadí slouží k řazení změn.

### <a name="q-can-i-manage-how-codelens-processes-code-to-show-history-and-linked-items"></a>Otázka: je možné spravovat, jak Codelensu zpracuje kód pro zobrazení historie a propojené položky?

**Odpověď:** Ano. Pokud váš kód v sadě TFS, použijte [codeindex – příkaz](../ide/codeindex-command.md) s [příkazu TFS Config](/tfs/server/ref/command-line/tfsconfig-cmd).

### <a name="q-my-codelens-test-indicators-no-longer-appear-in-my-file-when-i-first-open-my-solution-how-can-i-load-them"></a>Otázka: Moje ukazatele testovací Codelensu se nebude zobrazovat v souboru při prvním otevření mém řešení. Jak je můžete je načíst?

**Odpověď:** znovu sestavte projekt získat indikátory testovací Codelensu načíst v souboru. Zajistěte, aby [zjišťování podle integrovaný sestavení](../test/test-explorer-faq.md#3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on) je zapnutý. Pokud chcete zvýšit výkon, Visual Studio už načte informace o zdroji pro test indikátory při soubory kódu jsou načtena. Test indikátory jsou načtena po sestavení, nebo když přejdete k testu dvojitým kliknutím na něm v **testování Explorer**.

## <a name="see-also"></a>Viz také:

- [Funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)
