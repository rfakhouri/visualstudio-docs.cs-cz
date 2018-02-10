---
title: "Správa prostředí Python v sadě Visual Studio | Microsoft Docs"
description: "Jak používat prostředí Python oken v sadě Visual Studio ke správě globální a virtuální prostředí, nastavit vlastní prostředí, instalace překladače Python, instalace balíčků, nastavení cesty hledání a správu prostředí pro projekty v sadě Visual Studio."
ms.custom: 
ms.date: 01/16/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 40f901c65872fe593457883c36f0d60bf7e2fd8a
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="python-environments"></a>Prostředí Python

Python *prostředí* je kontext, ve kterém můžete spustit kód Python. Prostředí se skládá z překladač knihovny (obvykle Python standardní knihovny) a sadu instalovaných balíčků. Tyto součásti společně určují, které jazykové konstrukty a syntaxe jsou platné, spouštění jaký operační systém funkce mají přístup a které balíčky, které můžete použít.

V sadě Visual Studio, můžete spravovat všechna prostředí pomocí [okno prostředí Python](#managing-python-environments-in-visual-studio) jak je popsáno v tomto článku. Pro daný projekt, vyberete prostředí pro spuštění kódu, ladění, kontrola syntaxe, import a člen dokončených zobrazení a všemi ostatními úkoly, které jsou specifické pro překladač a nainstalované knihovny. Visual Studio také udržuje databázi IntelliSense pro každé prostředí, která poskytuje pro automatické dokončování při zadávání kódu.

Visual Studio také poskytuje podporu pro virtuální prostředí, `requirements.txt` souborů a cesty hledání.

**Poznámka:**: Pokud jste ještě Python v sadě Visual Studio, najdete v následujících článcích pro potřeby pozadí:

- [Práce s Python v sadě Visual Studio](overview-of-python-tools-for-visual-studio.md)
- [Instalace podpory Python v sadě Visual Studio](installing-python-support-in-visual-studio.md)

## <a name="global-and-virtual-environments"></a>Globální a virtuální prostředí

Existují dva typy prostředí Python: globální a virtuální.

**Globální prostředí**: instalace každý Python (například Python 2.7, Python 3.6 a Anaconda 4.4.0, viz [výběr a instalace Python překladače](#selecting-and-installing-python-interpreters) udržuje vlastní prostředí. Každé prostředí se skládá z konkrétní překladač Pythonu, jeho standardní knihovna a sadu předem nainstalované balíčky. Instalaci balíčku do globální prostředí bude dostupná pro všechny projekty pomocí prostředí. Pokud prostředí je umístěný v oblasti Ochrana systému souborů (v rámci `c:\program files`, například), pak instalace balíčků vyžaduje oprávnění správce.

Globální prostředí jsou k dispozici pro všechny projekty v počítači. V sadě Visual Studio vyberte jeden globální prostředí jako výchozí, což se použije pro všechny projekty Pokud zvolíte jinou pro projekt. Další informace najdete v tématu [výběr prostředí pro projekt](#selecting-an-environment-for-a-project).

**Virtuální prostředí**: protože balíčky nainstalované do globální prostředí jsou k dispozici na všechny projekty, které používají prostředí, je v konfliktu může dojít, pokud dva projekty vyžadují Nekompatibilní balíčky nebo různé verze stejného balíčku. Virtuální prostředí vyhnout takové konflikty pomocí překladač a standardní knihovny z globální prostředí ale udržování své vlastní balíček úložišť v izolovaném složek.

V sadě Visual Studio, můžete vytvořit virtuální prostředí pro konkrétní projekt, který je uložený v podsložce v projektu (viz [vytvoření virtuálních prostředí](#creating-virtual-environments). Soubor projektu také identifikuje virtuální prostředí. Visual Studio také zaznamenává všechny balíčky, které můžete nainstalovat do virtuálního prostředí v projektu `requirements.txt` souboru. Pokud sdílíte projektu a jinými vývojáři otevřít na svých počítačích, Visual Studio poskytuje možnost znovu vytvořte virtuální prostředí.

### <a name="selecting-and-installing-python-interpreters"></a>Výběr a instalace překladače Python

Ve výchozím nastavení instalaci zatížení vývoj Python ve Visual Studio 2017 se nainstaluje také Python 3 (64 bitů). Volitelně můžete pro instalaci 32bitové a 64bitové verze Python 2, Python 3, Anaconda 2 a Anaconda 3, jak je popsáno v [instalace](installing-python-support-in-visual-studio.md). Můžete také ručně nainstalovat všechny překladače uvedené v následující tabulce.

Pro Visual Studio 2015 a starší je nutné mezi překladače nainstalovat ručně.

Visual Studio (všechny verze) automaticky vytvoří prostředí pro každou kontrolou registru překladač Pythonu (následující [období 514 - Python registrace v registru Windows](https://www.python.org/dev/peps/pep-0514/)). Pokud Visual Studio nerozpozná nainstalované prostředí, přečtěte si téma [vytváření prostředí pro existující překladač](#creating-an-environment-for-an-existing-interpreter).

| Překladač | Popis |
| --- | --- |
| [CPython](https://www.python.org/) | "Nativní" a nejčastěji používaných překladač, k dispozici v 32bitové a 64bitové verze (32bitová verze doporučené). Zahrnuje nejnovější funkce jazyka, maximální kompatibility balíček Python, plná podpora ladění a interoperabilita s [IPython](http://ipython.org/). Viz také: [použít Python 2 nebo Python 3?](http://wiki.python.org/moin/Python2orPython3). Všimněte si, že Visual Studio 2015 a starší nepodporují Python 3.6 a může poskytnout chyba "Unsupported verze python 3.6". Používat jazyk Python, 3.5 nebo starší místo. |
| [IronPython](https://github.com/IronLanguages/ironpython2) | Implementace rozhraní .NET jazyka Python, k dispozici v 32bitové a 64bitové verze, C# / f # nebo Visual Basic zprostředkovatel komunikace s objekty, poskytuje přístup k rozhraní API technologie .NET, standardní Python ladění (ale ne C++ ve smíšeném režimu ladění) a ve smíšeném IronPython / C# ladění. IronPython, ale nepodporuje virtuální prostředí. |
| [Anaconda](https://www.continuum.io) | Platformě vědecké účely open data používá technologii Python a obsahuje nejnovější verzi CPython a většina těžko instalovat balíčky. Doporučujeme, abyste ho nelze v opačném případě rozhodnete-li. |
| [PyPy](http://www.pypy.org/) | Vysoce výkonné trasování JIT, provádění Python, který je vhodný pro dlouhodobé programy a situacích slouží k určení výkonu problémy, ale nemůže najít jiné řešení. Funguje s Visual Studio, ale s omezenou podporu pro pokročilé funkce ladění. |
| [Jython](http://www.jython.org/) | Implementace jazyka Python na virtuální počítač Java (JVM). Podobá se IronPython, kód spuštěný v Jython mohou komunikovat s třídy jazyka Java a knihovny, ale nemusí být možné používat mnoho knihovny určené pro CPython. Funguje s Visual Studio, ale s omezenou podporu pro pokročilé funkce ladění. |

Vývojáři, které chcete přidat nové formuláře detekce prostředí Python, zobrazit [PTVS prostředí detekce](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (webu github.com).

## <a name="managing-python-environments-in-visual-studio"></a>Správa prostředí Python v sadě Visual Studio

Chcete-li otevřít okno prostředí Python, vyberte **zobrazení > ostatní okna > prostředí Python** příkazu nabídky nebo klikněte pravým tlačítkem **prostředí Python** uzel pro projekt v Průzkumníku řešení a Vyberte **zobrazení všech prostředí Python**:

![Zobrazit všechna prostředí příkazu v Průzkumníku řešení](media/environments-view-all.png)

V obou případech se zobrazí okno prostředí Python jako karty na stejné úrovni do Průzkumníka řešení:

![Okno prostředí Python](media/environments-default-view.png)

Výše uvedený příklad ukazuje, že Python 3.4 (32bitová verze CPython) je nainstalována spolu s 32bitové a 64bitové verze IronPython 2.7. Výchozí prostředí tučným je Python 3.4, který se používá pro všechny nové projekty. Pokud nevidíte žádné prostředí uvedené, znamená to, že jste nainstalovali nástroje Python Tools pro sadu Visual Studio v sadě Visual Studio 2015 nebo dřívější, ale nebyly nainstalovány překladač Pythonu (viz [zvolíte a instalace Python překladače](#selecting-and-installing-python-interpreters) výše). **+ Vlastní...**  příkaz umožňuje [vytvoření prostředí pro existující překladač](#creating-an-environment-for-an-existing-interpreter).

Napravo od jednotlivých uvedených prostředí je ovládací prvek, které se otevře okno s interaktivní pro prostředí. Může se zobrazit další ovládací prvek se aktualizuje databázi IntelliSense pro prostředí.

Pod seznamem prostředí je selektor rozevíracího seznamu pro **přehled**, **balíčky**, a **IntelliSense** možnosti popsané dál v této části. Pokud rozbalíte **prostředí Python** okno dost široké, tyto možnosti se zobrazují jako karet, které možná pohodlnější pro práci s:

![Zobrazení v okně rozšířit prostředí Python](media/environments-expanded-view.png)

> [!Note]
> I když Visual Studio respektuje možnost balíčky systému lokality, neposkytuje způsob, jak změnit z Visual Studia.

Video Úvod do správy prostředí v sadě Visual Studio, najdete v části [Správa prostředí Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) (Microsoft Virtual Academy, 2m35s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Managing-Python-Environments-qrDmN4LWE_8305918567]

### <a name="creating-an-environment-for-an-existing-interpreter"></a>Vytvoření prostředí pro existující překladač

Pokud Visual Studio není vyhledat překladač (například když je nainstalovaná v nestandardním umístění), můžete vytvořit a následuje prostředí jako:

1. Vyberte **+ vlastní...**  v [okno prostředí Python](#managing-python-environments-in-visual-studio), který vytváří nové prostředí a otevře [ **konfigurace** kartě](#configure-tab) popsané dál.)

    ![Výchozí zobrazení pro novou vlastní prostředí](media/environments-custom-1.png)

1. Zadejte název pro prostředí v **popis** pole.
1. Zadejte nebo vyhledejte cestu překladač v **předponu cesta** pole.
1. Vyberte **automatické rozpoznání** mít Visual Studio dokončit zbývající pole nebo je dokončit ručně.
1. Vyberte **použít** uložit prostředí.
1. Pokud je třeba odebrat prostředí, vyberte **odebrat** příkaz na **konfigurace** kartě. Automatické rozpoznání prostředí nenabízí tuto možnost. Najdete v části Další informace.

### <a name="moving-an-existing-interpreter"></a>Přesunutí existující překladač

Pokud přesouváte existující překladač do nového umístění v systému souborů, Visual Studio automaticky nerozpozná změnu a jeho prostředí musíte aktualizovat ručně:

- Pokud jste původně vytvořili prostředí pro tento překladač, upravte prostředí tak, aby odkazoval na nové umístění.

- Pokud prostředí byl původně automaticky zjištěna, byla nainstalována na počítač s odlišné instalační program, který vytvořili položky registru, které hledá v sadě Visual Studio. Nejdříve obnovte v tomto případě překladač Pythonu do původního umístění. Pak odinstalujte ji pomocí instalačního programu, který vymaže položky registru. Potom přeinstalujte překladač v požadovaném umístění. Restartování sady Visual Studio a by měl automaticky rozpoznat nové umístění. Tento proces zajistí, že jsou správně použití jiné vedlejší účinky instalačního programu.

### <a name="overview-tab"></a>Karta Přehled

Poskytuje základní informace a příkazy pro prostředí:

![Karta Přehled prostředí Python](media/environments-overview-tab.png)

| Příkaz | Popis |
| --- | --- |
| Nastavit jako výchozí pro nové projekty toto prostředí | Nastaví active prostředí, které může způsobit, že Visual Studio se stručně přestane reagovat při načítání databázi IntelliSense. Prostředí s mnoha balíčky může být po delší dobu reagovat. |
| Navštívit webovou stránku distributorovi | Otevře prohlížeč na adresu URL od distribuci jazyka Python. Python 3.x, například přejde k python.org. |
| Otevřete okno interaktivní | Otevře se [interaktivních okna (REPL)](python-interactive-repl-in-visual-studio.md) pro toto prostředí v sadě Visual Studio použití žádné [spouštěcí skripty (viz níže)](#startup-scripts). |
| Prozkoumat interaktivní skripty | V tématu [spouštěcí skripty](#startup-scripts). |
| Použití IPython interaktivním režimu | Pokud nastavíte, otevře se okno interaktivní s IPython ve výchozím nastavení. Tato povoleno vložené ukazuje zeměpisný a rozšířené syntaxe IPython například `name?` chcete zobrazit nápovědu a `!command` pro příkazy prostředí. Tato možnost se doporučuje při použití distribuci Anaconda, jako je vyžaduje další balíčky. Další informace najdete v tématu [pomocí IPython v okně interaktivní](interactive-repl-ipython.md). |
| Otevřete v prostředí PowerShell | Spustí překladač v příkazové okno prostředí PowerShell. |
| (Složky odkazů) | Poskytují rychlý přístup k prostředí nástroje instalační složku, překladač python.exe a pythonw.exe překladač. První otevře v Průzkumníku Windows, dvou otevřete okno konzoly. |

#### <a name="startup-scripts"></a>Spouštěcí skripty

Interaktivní windows používáte ve svém pracovním postupu každý den, pravděpodobně vyvíjet pomocných funkcí, které používáte pravidelně. Například můžete vytvořit funkci, která otevře DataFrame v aplikaci Excel a pak uložte tento kód jako spouštěcí skript tak, aby byla vždy dostupná v okně interaktivní.

Spouštěcí skripty obsahovat kód, který interaktivních okna načte a spustí automaticky, včetně importy, definice funkcí a oznámena cokoliv jiného. Takové skripty odkazují dvěma způsoby:

1. Při instalaci prostředí sady Visual Studio vytvoří složku `Documents\Visual Studio 2017\Python Scripts\<environment>` kde &lt;prostředí & gt "odpovídá názvu prostředí. Můžete snadno přejít do složky specifické pro prostředí s **prozkoumat interaktivní skripty** příkaz. Při spuštění interaktivních okna pro prostředí se načítá a spouští ať `.py` se zde nacházejí soubory v abecedním pořadí.

1. **Skripty** řídit ve **nástroje > Možnosti > Python Tools > Interaktivní Windows** karta (najdete v části [možnosti interaktivního windows](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options)) slouží k určení dalších Složka pro spouštěcí skripty, které jsou načteny a spustit ve všech prostředích. Tato funkce se však v současné době nefunguje.

### <a name="configure-tab"></a>Karta Konfigurace

Pokud se zobrazí, obsahuje podrobnosti, jak je popsáno v následující tabulce. Pokud není k dispozici na této kartě, znamená to, že Visual Studio je Správa všech podrobností o automaticky.

![Karta Konfigurace prostředí Python](media/environments-configure-tab.png)

| Pole | Popis |
| --- | --- |
| **Popis** | Název prostředí. |
| **Předpona cesta** | Umístění složky základní překladač. Naplnění tuto hodnotu a kliknutím na **automatické rozpoznání**, Visual Studio se pokusí vyplňte další pole za vás. |
| **Překladač cesta** | Cesta k překladač spustitelný soubor, běžně cesta předponu následuje`python.exe` |
| **Oddílové překladač** | Cesta k mimo konzolu spustitelný soubor, často cesta předponou následuje `pythonw.exe`. |
| **Cesta ke knihovně** | Určuje kořenu standardní knihovny, ale pokud tato hodnota může být ignorována Visual Studio je schopen přesnější cestu požadavku z překladač. |
| **Jazyková verze** | Vybrat v rozevírací nabídce. |
| **Architektura** | Za normálních okolností zjištěna a vyplnit automaticky, v opačném případě určuje 32bitové nebo 64bitové verze. |
| **Proměnné prostředí Path** | Proměnné prostředí, která překladač používá k nalezení cest hledání. Visual Studio změní hodnotu proměnné při spouštění Python tak, aby obsahoval cesty pro hledání projektu. Obvykle tato vlastnost by měla být nastavená na `PYTHONPATH`, ale některé překladače použít jinou hodnotu. |

### <a name="pip-tab"></a>Karta PIP

Spravuje balíčky nainstalované v prostředí, což umožňuje hledat a instalovat nové (včetně závislostí). Hledání filtry vaší aktuálně nainstalovaných balíčků a [úložiště PyPI](https://pypi.python.org). Můžete také přímo zadat libovolný `pip install` příkaz do vyhledávacího pole, včetně příznaky, jako například `--user` nebo `--no-deps`.

![Karta pip prostředí Python](media/environments-pip-tab.png)

Instalace balíčku vytvoří podsložky v rámci v prostředí `Lib` složku v systému souborů. Například pokud máte Python 3.6, které se instaluje v `c:\Python36`, balíčky jsou nainstalovány v `c:\Python36\Lib`; Pokud máte nainstalovaný v Anaconda3 `c:\Program Files\Anaconda3` pak balíčky jsou nainstalovány v `c:\Program Files\Anaconda3\Lib`.

V takovém případě protože prostředí je umístěný v oblasti chráněného systému souborů, `c:\Program Files`, musíte spustit Visual Studio `pip install` zvýšenými tak, aby ji k vytvoření balíčku podsložky. Pokud se vyžaduje zvýšení oprávnění, sada Visual Studio zobrazí řádku "oprávnění správce může být nutné nainstalovat, aktualizovat nebo odebrat balíčky pro toto prostředí":

![Výzva ke zvýšení oprávnění pro instalaci balíčku](media/environments-pip-elevate.png)

**Zvýšení oprávnění teď** uděluje oprávnění pro nástrojem pip pro jednu operaci, správu subjektu také všechny operační systémy vyzve k zadání oprávnění. Výběr **pokračovat bez oprávnění správce** pokusy o instalaci balíčku, ale pip selže při pokusu o vytvoření složky s výstupem, jako "Chyba: Nepodařilo se vytvořit" C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': bylo odepřeno oprávnění. "

Výběr **vždy zvýšení oprávnění při instalaci nebo odebrání balíčků** dialogu zabraňuje zobrazování pro prostředí. Chcete-li se znovu zobrazí dialogové okno, přejděte na **nástroje > Možnosti > Python Tools > Obecné** a kliknutím na tlačítko, **resetovat všechny trvale skrytá dialogová okna**.

V tom, že stejné možnosti kartě, můžete také vybrat **vždy spustit jako správce pip** o potlačení pro všechna prostředí. V tématu [možnosti - karta Obecné](python-support-options-and-settings-in-visual-studio.md#general-options).

### <a name="intellisense-tab"></a>Karta IntelliSense

Ukazuje aktuální stav databáze doplňování IntelliSense:

![Karta IntelliSense prostředí Python](media/environments-intellisense-tab.png)

Databáze obsahuje metadata pro všechny prostředí knihovny a zvyšuje rychlost IntelliSense a snižuje využití paměti. Když zjistí nového prostředí sady Visual Studio (nebo je přidat jeden), automaticky se začne při kompilaci databáze analýzou zdrojové soubory knihovny. Tento proces může trvat z minutu na hodinu nebo déle v závislosti na tom, co je nainstalované. (Anacondu, například se dodává s mnoha knihovny a při kompilaci databáze nějakou dobu trvá.) Po dokončení můžete získat podrobné IntelliSense a nemusíte znovu aktualizujte databázi (s **aktualizovat DB** tlačítko) až po instalaci dalších knihoven.

Knihovny, pro které nebyla kompilována data jsou označené **!**; Pokud prostředí s databáze není kompletní, **!** také se zobrazí vedle sebe v seznamu hlavní prostředí.

## <a name="selecting-an-environment-for-a-project"></a>Výběr prostředí pro projekt

Specifické pro projekt prostředí Ujistěte se, že projektu vždy běží v prostředí s konkrétní, ignoruje prostředí globální výchozí. Například pokud prostředí výchozí globální CPython, ale vyžaduje projektu IronPython a některé knihovny, které nejsou nainstalované v globální prostředí, prostředí specifické pro projekt je nezbytné.

Projekt prostředí jsou uvedené v Průzkumníku řešení v uzlu prostředí Python. Tučné položky je aktuálně aktivní a Visual Studio použije pro ladění, jejich import a dokončování člen, kontrola syntaxe a další úlohy, které vyžadují prostředí:

![Prostředí projektu zobrazí v Průzkumníku řešení](media/environments-project.png)

Pokud chcete aktivovat do různých prostředí pro projekt, klikněte pravým tlačítkem na prostředí a vyberte **aktivovat prostředí**.

Jakékoli globální prostředí se dá přidat jako prostředí projektu kliknutím pravým tlačítkem na **prostředí Python** a výběrem **prostředí Python přidat nebo odebrat...** . V zobrazeném seznamu můžete vybrat, nebo zrušte výběr těchto prostředí, které jsou k dispozici ve vašem projektu.

![Dialogové okno Přidat nebo odebrat prostředí Python](media/environments-add-remove.png)

V Průzkumníku řešení můžete také rozšířit prostředí zobrazíte jeho nainstalované balíčky (ty lze importovat a používat ve vašem kódu, když je aktivní prostředí):

![Balíčky Python pro prostředí v Průzkumníku řešení](media/environments-installed-packages.png)

Chcete-li nainstalovat nové balíčky, klikněte pravým tlačítkem na prostředí, vyberte možnost **instalovat balíček Python...** a zadejte název požadované balíčku. Balíčky (a závislosti) se stahují z [indexu balíčků Pythonu (úložiště PyPI)](https://pypi.python.org/pypi), kde můžete také vyhledat dostupné balíčky. Stavový řádek sady Visual Studio a výstup – okno obsahuje informace o instalaci. Pro odinstalaci balíčku, klikněte pravým tlačítkem ji vyberte **odebrat**.

> [!Note]
> Podpora správy balíčků jazyka Python je aktuálně ve vývoji týmem vývojářů Python jádra. Zobrazené položky nemusí být vždy přesné, a instalace a odinstalace nemusí být spolehlivé nebo nejsou k dispozici. Visual Studio používá Správce balíčků pip, pokud je k dispozici a stáhne a nainstaluje se vyžádání. Visual Studio můžete také použít easy_install Správce balíčků. Zobrazí se také balíčky nainstalované pomocí systému pip nebo easy_install z příkazového řádku.

> [!Tip]
> Je běžné situace, kde pip nepodaří nainstalovat balíček, pokud balíček obsahuje zdrojový kód pro nativní součásti v `*.pyd` soubory. Bez požadovaná verze sady Visual Studio nainstalována nelze zkompilovat pip těchto součástí. Chybová zpráva zobrazená v této situaci je `error: Unable to find vcvarsall.bat`. `easy_install`často je možné stáhnout předem kompilovaném binární soubory, a můžete si stáhnout vhodný kompilátoru pro starší verze jazyka Python z [http://aka.ms/VCPython27](http://aka.ms/VCPython27). Další podrobnosti najdete v tématu [řešení problémů s problémové z "nelze najít vcvarsallbat"](https://blogs.msdn.microsoft.com/pythonengineering/2016/04/11/unable-to-find-vcvarsall-bat/) na Python tools blogu týmu.

## <a name="creating-virtual-environments"></a>Vytvoření virtuálního prostředí

1. Klikněte pravým tlačítkem na **prostředí Python** v Průzkumníku řešení a vyberte **přidat virtuální prostředí...** , který spustí následující:

    ![Vytvoření virtuálního prostředí](media/environments-add-virtual-1.png)

1. Zadejte název pro vytvoření virtuálního prostředí v cestě vašeho projektu, nebo úplnou cestu k jeho vytvoření jinde. (Pro zajištění maximální kompatibility pomocí jiných nástrojů, používejte pouze písmena a čísla v názvu.)

1. Jako základní překladač vyberte globální prostředí a klikněte na tlačítko **vytvořit**. Pokud `pip` a `virtualenv` nebo `venv` balíčky nejsou dostupné, budou staženy a nainstalovány.

    Pokud zadaná cesta obsahuje existující virtuální prostředí, je zjištěna základní překladač a tlačítko pro vytvoření změny **přidat**:

    ![Přidání existujícího virtuálního prostředí](media/environments-add-virtual-2.png)

Existující virtuální prostředí se dá přidat taky kliknutím pravým tlačítkem na **prostředí Python** v Průzkumníku řešení a výběrem **přidat existující virtuální prostředí...** . Visual Studio automaticky zjišťuje základní překladač pomocí `orig-prefix.txt` souboru v prostředí nástroje `lib` adresáře.

Po přidání virtuálního prostředí do projektu se zobrazí v **prostředí Python** okno, můžete ji aktivujete jako jakékoli jiné prostředí, a můžete spravovat své balíčky. Pravým tlačítkem a vyberete **odebrat** buď odebere odkaz na prostředí, nebo odstraní prostředí a všechny jeho soubory na disku (ale ne základní překladač).

Všimněte si, že jednou z nevýhod virtuální prostředí je, že budou obsahovat cesty k souborům pevně a proto nelze snadno být sdílené nebo přenosu do jiných počítačů vývoj. Naštěstí můžete použít `requirements.txt` souboru, jak je popsáno v další části, kde umožnit příjemcům projektu snadno obnovit prostředí.

## <a name="managing-required-packages-requirementstxt"></a>Správa požadované balíčky (requirements.txt)

Pokud jste sdílení projektu s ostatními, použití systému sestavení nebo plánujete [publikování do služby Microsoft Azure](python-azure-cloud-service-project-template.md), je třeba zadat externí balíčky, které vyžaduje projekt. Doporučuje se používat [soubor requirements.txt](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org) obsahující seznam příkazů pro pip, který nainstaluje požadované verze závislé balíčky.

Technicky libovolný název souboru může sloužit k sledování požadavků (pomocí `-r <full path to file>` při instalaci balíčku), ale Visual Studio poskytuje konkrétní podporu pro `requirements.txt`:

- Pokud jste načíst projekt, který obsahuje `requirements.txt` a chcete instalovat všechny balíčky uvedené v tomto souboru, rozbalte **prostředí Python** uzlu v **Průzkumníku řešení**, klikněte pravým tlačítkem uzel prostředí a vyberte možnost **nainstalovat z requirements.txt**:

    ![Nainstalovat z requirements.txt](media/environments-requirements-txt-install.png)

- Pokud již máte všechny potřebné balíčky nainstalované v projektu, můžete v prostředí, v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **generovat soubor requirements.txt** k vytvoření souboru nezbytné. Pokud soubor již existuje, jak se zobrazí výzva k její aktualizaci:

    ![Možnosti requirements.txt aktualizace](media/environments-requirements-txt-replace.png)

  - **Nahradí celý soubor** odebere všechny položky, komentáře a možnosti, které existují.
  - **Aktualizovat existující položky** zjistí požadavků balíčku a aktualizuje verze specifikátory tak, aby odpovídaly aktuálně nainstalovanou verzi.
  - **Aktualizace a přidání položky** aktualizuje všechny požadavky, které se nacházejí a přidá všechny ostatní balíčky na konec souboru.

Protože `requirements.txt` soubory jsou určeny k freeze – požadavky na projektu, všechny nainstalované balíčky jsou zapsány s přesné verze. Použití přesné verze zajišťuje, že budete moci snadno opakovat prostředí na jiném počítači. Balíčky jsou zahrnuty i v případě, že byly instalovány s rozsahem verze jako závislost jiný balíček, nebo instalační program než pip.

Pokud `requirements.txt` soubor existuje při přidávání nové virtuální prostředí, **Přidání virtuálního prostředí** dialogovém okně se zobrazí možnost automaticky, instalaci balíčků a usnadňuje tak znovu vytvořit prostředí na jiném počítači:

![Vytvoření virtuálního prostředí s requirements.txt](media/environments-requirements-txt.png)

Pokud balíček nelze nainstalovat systém PIP a zobrazí se v `requirements.txt` souboru celý instalace se nezdaří. V takovém případě ruční úpravy souboru vyloučit tohoto balíčku, nebo chcete použít [pip na možnosti](http://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format) k odkazování na instalovat verzi balíčku. Například může byste radši chtěli použít [ `pip wheel` ](http://pip.readthedocs.org/en/latest/reference/pip_wheel.html) závislost zkompilujete a přidat `--find-links <path>` možnost na váš `requirements.txt`:

```output
C:\Project>pip wheel azure
Downloading/unpacking azure
    Running setup.py (path:C:\Project\env\build\azure\setup.py) egg_info for package azure

Building wheels for collected packages: azure
    Running setup.py bdist_wheel for azure
    Destination directory: c:\project\wheelhouse
Successfully built azure
Cleaning up...

C:\Project>type requirements.txt
--find-links wheelhouse
--no-index
azure==0.8.0

C:\Project>pip install -r requirements.txt -v
Downloading/unpacking azure==0.8.0 (from -r requirements.txt (line 3))
    Local files found: C:/Project/wheelhouse/azure-0.8.0-py3-none-any.whl
Installing collected packages: azure
Successfully installed azure
Cleaning up...
    Removing temporary dir C:\Project\env\build...
```

## <a name="search-paths"></a>Cesty hledání

S typickému využití Python `PYTHONPATH` proměnnou prostředí (nebo `IRONPYTHONPATH`atd) poskytuje výchozí cesta hledání pro soubory modulu. To znamená, když použijete `from <name> import...` nebo `import <name>` prohlášení, Python prohledává v pořadí pro odpovídajícím názvem následujících umístěních:

1. Integrované moduly jazyka Python.
1. Složka obsahující kód Python, které používáte.
1. "Modul vyhledávání cestu" jako definovanou proměnnou prostředí použít. (V tématu [Path hledání modulu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) a [proměnné prostředí](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) v základní dokumentace Python.)

Visual Studio ignoruje proměnné prostředí path hledání, ale i v případě, že proměnná je nastavená pro celý systém. Je ignorován ve skutečnosti, přesněji *protože* je nastavena pro celý systém a proto vyvolá určité otázek, které nelze automaticky zodpovězeny: odkazovaný moduly, které jsou určené výhradně pro Python 2.7 nebo Python 3.3? Budou se přepsat standardní knihovna moduly? Vývojář si je vědoma toto chování nebo je škodlivý zneužití pokus?

Visual Studio tak poskytuje i prostředky ke specifikaci cest hledání přímo v prostředí a projekty. Kód, který můžete spustit nebo ladění v sadě Visual Studio obdrží cesty hledání v hodnotě `PYTHONPATH` (a ostatní ekvivalentní proměnné). Přidáním cesty hledání Visual Studio zkontroluje knihovny v těchto umístěních a vytvoří databáze IntelliSense pro ně (vytváření, ke které databáze může chvíli trvat v závislosti na počtu knihovny).

Chcete-li přidat cestu vyhledávání, klikněte pravým tlačítkem na **cesty hledání** položky v Průzkumníku řešení, vyberte **přidat složku do cesty pro hledání...** a vyberte složku, kterou chcete zahrnout. Tato cesta je používána pro jakékoli prostředí přidružený k projektu. (Může se zobrazit chyby Pokud prostředí je založena na Python 3 a pokusíte se do přidat cestu vyhledávání modulů Python 2.7.)

Soubory s `.zip` nebo `.egg` rozšíření lze také přidat jako cesty hledání tak, že vyberete **přidat archivu Zip do cesty pro hledání...** . Stejně jako u složky, obsah tyto soubory jsou kontrolovány a k dispozici pro technologii IntelliSense.

Pokud používáte pravidelně stejné cesty pro hledání a obsah se často nemění, může být efektivnější k její instalaci do vaší lokality balíčky složky. Cesta hledání se pak analyzují a uloženy v databázi IntelliSense, je vždycky být přidružen prostředí určený a nevyžaduje cesta hledání mají být přidány do každého projektu.
