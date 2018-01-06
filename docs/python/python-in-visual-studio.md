---
title: "Python v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 09/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: hero-article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: f91fcfa7e0ea7247eb91a3512f7abd64d8684809
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="working-with-python-in-visual-studio"></a>Práce s Python v sadě Visual Studio

Python je oblíbených programovací jazyk, který je spolehlivá, flexibilní, usnadňuje další, bez použití na všech operačních systémech a nepodporuje komunity silné vývojářů a mnoho volné knihovny. Python podporuje všechny způsobů vývoje, včetně webových aplikací, webové služby, aplikace klasické pracovní plochy, skriptování a vědecké výpočty a používá mnoho vysoké školy, vědců, běžné vývojáři a profesionální vývojáře agentem. Další informace o jazyce na [python.org](https://www.python.org) a [Python pro začátečníky](https://www.python.org/about/gettingstarted/).

Visual Studio v systému Windows poskytuje [open-source](https://github.com/Microsoft/ptvs) podporu pro jazyk Python prostřednictvím vývoj Python a vědecké zpracování dat úlohy (Visual Studio 2017) a volné Python Tools pro Visual Studio rozšíření (Visual Studio 2015 a starší). Python v současné době nepodporuje v sadě Visual Studio pro Mac, ale je k dispozici na Mac a Linux pomocí Visual Studio Code (viz [Q & A pod](#questions-and-answers).

Abyste mohli začít:

- Postupujte podle [pokyny k instalaci](installation.md) nastavit zatížení Python
- Přejděte prostřednictvím jednoho nebo více Quickstarts k vytvoření projektu. Pokud si nejste jisti, začínat [vytvořte projekt ze šablony](quickstart-02-project-from-template.md).
- Postupujte podle [práce s Python v sadě Visual Studio](vs-tutorial-01-01.md) kurz prostředí úplného začátku do konce.
- Potom pomocí níže uvedených odkazů a prozkoumejte Python související funkce a možnosti sady Visual Studio, sám sebe.

| Funkce | Popis | Dokumentaci obecné Visual Studio | 
| --- | --- | --- |
| [Systém projektu Visual Studio](python-projects.md) | Implicitně vybere si strukturu složek Python kódu současně explicitní řízení k identifikaci kódu aplikace, testovacího kódu sestavení webové stránky, JavaScript, skripty atd. | [Řešení a projekty v sadě Visual Studio](../ide/solutions-and-projects-in-visual-studio.md) |
| [Šablony projektů](python-projects.md#project-templates) | Rychle vytvoří strukturu projektu pro konzolu, web, Azure, vědecké zpracování dat a jiné typy projektů | [Šablony sady Visual Studio](../ide/creating-project-and-item-templates.md#visual-studio-templates) |
| Podpora více překladač | Podporuje různé verze CPython a IronPython. | není k dispozici |
| Podpora IPython | Zahrnuje podporu pro IPython/Jupyter v REPL pro vložené pozemků, rozhraní .NET a Windows Presentation Foundation (WPF). | není k dispozici |
| [Bohaté úpravy, IntelliSense a pochopení kódu](code-editing.md) | Zahrnuje zvýrazňování syntaxe, automatické doplňování kódu a knihovny, [kódu, formátování](code-formatting.md), podpis nápovědy, zobrazení tříd, přejděte na definice, najít všechny odkazy, fragmenty kódu [refaktoring](code-refactoring.md), [ PyLint](code-pylint.md)a další. | [Psaní kódu v editoru kódu a textovém editoru](../ide/writing-code-in-the-code-and-text-editor.md) |
| [Interaktivní okno](interactive-repl.md) | Poskytuje rychlý prostředí REPL možnost snadno zvýrazněte část kódu a odeslat ho do okna interaktivní pro jazyk Python. | není k dispozici |
| [Plnohodnotné ladění](debugging.md) | Ladění lze provést s nebo bez projekt sady Visual Studio, včetně možnosti ladění spustitelného existující [ladění ve smíšeném režimu Python/C++](debugging-mixed-mode.md), [vzdálené ladění](debugging-cross-platform-remote.md) do systému Windows nebo Linux nebo Mac. [vzdálené ladění do Azure](debugging-azure-remote.md)a ladění interaktivních okna. | [Ladění v sadě Visual Studio](../debugger/debugging-in-visual-studio.md) |
| [Nástroje pro profilaci s komplexní vytváření sestav](profiling.md) | Popisuje, jak je právě čas strávený v rámci vaší aplikace, včetně možnosti porovnat výkon mezi různé profilování spustí. | [Nástroje pro profilaci](../profiling/profiling-tools.md) (ne všechny funkce profilace aplikace Visual Studio jsou dostupné pro jazyk Python) |
| [Nástroje pro testování částí](unit-testing.md) | Zjistit, spustit a správu testů v testovací Průzkumníka Visual Studio a snadno ladění testování částí. | [Testování částí kódu](../test/unit-test-your-code.md) |

Také zahrnuje úlohy Python [Azure SDK pro jazyk Python](azure-sdk-for-python.md), což zjednodušuje použití služby Azure z aplikací systému Windows, Mac OS X a Linux.

Video úvod, najdete v článku krátké [Python Tools pro Visual Studio](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121) kurzu na webu Microsoft Virtual Academy (asi 22 minut celkový). 

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Installing-Visual-Studio-Python-Support-go1id3LWE_1705918567]


## <a name="questions-and-answers"></a>Otázky a odpovědi

**OTÁZKY. Je k dispozici v sadě Visual Studio pro Mac podporu Python?**

A. Není v tuto chvíli, když na vyžádání na [UserVoice](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac/suggestions/18670291-python-tools-for-visual-studio-mac). [Visual Studio pro Mac](/visualstudio/mac/) dokumentace identifikuje aktuální typy vývoj, které podporují. Do té doby, Visual Studio Code v systému Windows, Mac a Linux [pracuje s Python prostřednictvím dostupná rozšíření](https://code.visualstudio.com/docs/languages/python).

**OTÁZKY. Co je můžete použít k vytvoření uživatelského rozhraní s Pythonem?**

A. Hlavní nabídky v této oblasti je [RT projektu](https://www.qt.io/qt-for-application-development/), s vazby pro jazyk Python známé jako [PySide (oficiální vazby)](http://wiki.qt.io/PySide) (také zobrazit [PySide stáhne](https://download.qt.io/official_releases/pyside/.)) a [ PyQt](https://wiki.python.org/moin/PyQt). V současné době podporu jazyka Python v sadě Visual Studio neobsahuje žádné konkrétní nástroje pro vývoj uživatelského rozhraní.

**OTÁZKY. Můžete vytvořit projekt Python samostatný spustitelný soubor?**

A. Python je obecně interpretovaný jazyk, se kterým je kód spouštět na vyžádání v prostředí vhodný podporující Python například Visual Studio a webovými servery. Visual Studio, sám v současné době neposkytuje způsob, jak vytvořit samostatný spustitelný soubor, což v podstatě znamená programu s embedded překladač Pythonu. Existují však různými prostředky v rámci komunity Python k vytvoření spustitelné soubory, jak je popsáno na [StackOverflow](http://stackoverflow.com/questions/5458048/how-to-make-a-python-script-standalone-executable-to-run-without-any-dependency). CPython také podporuje probíhá vloženým do nativní aplikace, jak je popsáno v příspěvku na blogu [pomocí CPython li souboru Zip](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/26/cpython-embeddable-zip-file/).

## <a name="features-matrix"></a>Matice funkce

Podpora v jazyce Python lze nainstalovat v následujících edicích sady Visual Studio, jak je popsáno v [Průvodce instalací](installation.md):

- [Visual Studio 2017 (všechny edice)](https://www.visualstudio.com/vs/)
- [Visual Studio 2015 (všechny edice)] (https://www.visualstudio.com/en-us/downloads/visual-studio-2015-downloads-vs)
- Visual Studio 2013 Community Edition
- Visual Studio 2013 Express pro Web, Update 2 nebo vyšší
- Visual Studio 2013 Express pro plochu, Update 2 nebo vyšší
- Visual Studio 2013 (Pro edice nebo vyšší)
- Visual Studio 2012 (Pro edice nebo vyšší)
- Visual Studio 2010 SP1 (Pro edice nebo vyšší; vyžaduje .NET 4.5)

Podporované funkce sady Visual Studio verze a edice:

| Podpora v jazyce Python | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Správu několika překladače | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automaticky rozpoznat oblíbených překladače | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Přidat vlastní překladače | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Virtuální prostředí | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PIP, snadná instalace | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Systém projektu | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Nový projekt z existujícího kódu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Zobrazit všechny soubory | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Správa zdrojového kódu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Integrace Gitu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004;<sup>1</sup> | &#10007; |
<br/>

| Úpravy | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| zvýraznění syntaxe | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatické dokončování | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Podpis nápovědy | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Rychlé informace | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Objekt prohlížeče nebo třídy zobrazení | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Navigační panel | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Přechod na definici | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Přejděte na | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Najít všechny odkazy | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatické odsazení | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Formátování kódu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Refaktorovat – přejmenovat | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Refaktorovat – extrahování metody | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Refaktorovat – přidat nebo odebrat import | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| PyLint | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Interaktivní okno | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Interaktivní okno | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IPython vložené grafů | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Desktop | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Aplikace konzoly a Windows | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| WPF IronPython (pomocí návrháře XAML) | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| IronPython Windows Forms | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Web | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Webový projekt Django | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Bottle webového projektu | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Webový projekt flask | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Obecné webového projektu | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Azure | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Nasazení do webové stránky | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004;<sup>2</sup> |
| Nasazení do webové role | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Nasazení do role pracovního procesu | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Spustit v Azure emulátoru | ? | ? | ? | &#10007; | &#10004;<sup>4</sup> | &#10004;<sup>4</sup> | &#10004;<sup>3</sup> | &#10007; |
| Vzdálené ladění | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>6</sup> | &#10004;<sup>8</sup> | &#10004;<sup>8</sup> | &#10007; |
| Připojit v Průzkumníku serveru | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>7</sup> | &#10004;<sup>7</sup> | &#10007; | &#10007; |
<br/>

| Django šablony | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Ladění | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; | &#10004; |
| Automatické dokončování | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10004; | &#10004; |
| Automatické dokončování šablon stylů CSS a JavaScript | &#10004; | &#10004; | &#10004; | &#10007; | &#10004;<sup>5</sup> | &#10004;<sup>5</sup> | &#10007; | &#10007; |
<br/>

| Ladění | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Ladění | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Ladění bez projektu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
| Ladění – připojení k úpravám | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Ladění ve smíšeném režimu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Vzdálené ladění (Windows, Mac OS X, Linux) | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; | &#10004; | &#10004; | &#10004; |
| Interaktivní okno ladění | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; |
<br/>

| Profilace | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | ---|
| Profilace | &#10004; | &#10004; | &#10004; | &#10007; | &#10007; | &#10004; | &#10004; | &#10004; |
<br/>

| Test | 2017 | 2015 | Comm – 2013 | Plocha 2013 | 2013 web | 2013 pro + | 2012 pro + | 2010 SP1 Pro + |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Průzkumníka testů | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Spuštění testu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
| Ladění testu | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10004; | &#10007; |
<br/>

1. Podpora Git pro sadu VS 2012 je k dispozici ve Visual Studio Tools for Git rozšíření, která je k dispozici na [Galerie sady Visual Studio](http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c).

2. Nasazení na web Azure vyžaduje, aby [Azure SDK pro .NET 2.1 - VS 2010 SP1](http://go.microsoft.com/fwlink/?LinkId=313855).  Novější verze nepodporují VS 2010.

3. Podpora pro Azure webovou roli a roli pracovního procesu vyžaduje [Azure SDK pro .NET 2.3 - VS 2012](http://go.microsoft.com/fwlink/?LinkId=323511) nebo novější.

4. Podpora pro Azure webovou roli a roli pracovního procesu vyžaduje [Azure SDK pro .NET 2.3 - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

5. Editor šablon Django ve Visual Studiu 2013 se některé známé problémy, které se vyřeší instalací aktualizace 2.

6. Vyžaduje Windows 8 nebo novější. Visual Studio 2013 Express pro Web nemá připojení do dialogového okna procesu, ale vzdálené ladění webu Azure je stále možné pomocí příkazu připojit ladicí program (Python) v Průzkumníku serveru. Vzdálené ladění vyžaduje [Azure SDK pro .NET 2.3 - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

7. Vyžaduje Windows 8 nebo novější. Připojit ladicí program (Python) příkaz v Průzkumníku serveru vyžaduje [Azure SDK pro .NET 2.3 - VS 2013](http://go.microsoft.com/fwlink/?LinkId=323510) nebo novější.

8. Vyžaduje Windows 8 nebo novější.

## <a name="additional-resources"></a>Další zdroje

- [Zápis senzor Kinect hry s Pythonem pomocí PyKinect](https://github.com/Microsoft/PTVS/wiki/PyKinect) (Githubu wiki)
- [WFastCGI most mezi službou IIS a Python](https://pypi.python.org/pypi/wfastcgi) (python.org)
- [Volné kurzy Pythonu na webu Microsoft Virtual Academy](https://mva.microsoft.com/search/SearchResults.aspx#!q=python)
- [Horní Python dotazy na Microsoft Virtual Academy](https://aka.ms/mva-top-python-questions)
