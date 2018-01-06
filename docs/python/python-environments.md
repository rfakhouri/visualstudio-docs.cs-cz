---
title: "Prostředí Python v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 07/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "11"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: bd871b1e78878c8ae05cb69e1ac97d50197a18b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="python-environments"></a>Prostředí Python

Python v sadě Visual Studio usnadňuje správu více prostředí Python a snadno přepínat mezi nimi pro různé projekty.

**Poznámka:**: Pokud jste ještě Python v sadě Visual Studio, najdete v následujících tématech nejprve jako to znamenat diskusní závisí na je:

- [Práce s Python v sadě Visual Studio](python-in-visual-studio.md)
- [Instalace podpory Python v sadě Visual Studio](installation.md)

Python *prostředí*, ve které je vždy spustit kód Python, se skládá z překladač, knihovny (obvykle Python standardní knihovnu), a sadu instalovaných balíčků. Tyto součásti společně určují, které jazykové konstrukty a syntaxe jsou platné, spouštění jaký operační systém funkce mají přístup a které balíčky, které můžete použít.

V sadě Visual Studio, prostředí také zahrnuje databázi IntelliSense pro prostředí s knihovny, tak, že zadáte příkaz jako `import` editor v sadě Visual Studio se automaticky zobrazí seznam dostupných knihoven, jakož i moduly v rámci Tyto knihovny.

Často vývojáři použít pouze jeden, globální prostředí Python. Ostatní vývojáři však zapotřebí spravovat několik globální prostředí, projektu konkrétní prostředí a virtuální prostředí, jak je popsáno v tomto tématu:

- [Výběr a instalace překladače Python](#selecting-and-installing-python-interpreters)
- [Správa prostředí Python v sadě Visual Studio](#managing-python-environments-in-visual-studio)
- [Globální prostředí](#global-environments)
- [Specifické pro projekt prostředí](#project-specific-environments)
- [Virtuální prostředí](#virtual-environments)
- [Správa požadované balíčky](#managing-required-packages)
- [Cesty hledání](#search-paths)

Video úvod naleznete v tématu [Správa prostředí Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) (Microsoft Virtual Academy, 2m35s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Managing-Python-Environments-qrDmN4LWE_8305918567]

## <a name="selecting-and-installing-python-interpreters"></a>Výběr a instalace překladače Python

S výjimkou s Visual Studio 2017 podpora v jazyce Python není součástí překladač Pythonu proto musíte nainstalovat některou z následujících pro spouštění vašeho kódu. Obecně platí Visual Studio automaticky rozpozná nově nainstalovaná překladače a nastaví prostředí pro každou. Pokud se nezjistí nainstalované prostředí, přečtěte si téma [vytváření prostředí pro existující překladač](#creating-an-environment-for-an-existing-interpreter).

| Překladač | Popis |
| --- | --- |
| [CPython](https://www.python.org/) | "Nativní" a nejčastěji používaných překladač, k dispozici v 32bitové a 64bitové verze (32bitová verze doporučené). Zahrnuje nejnovější funkce jazyka, maximální kompatibility balíček Python, plná podpora ladění a interoperabilita s [IPython](http://ipython.org/). Viz také: [použít Python 2 nebo Python 3?](http://wiki.python.org/moin/Python2orPython3). Všimněte si, že Visual Studio 2015 a starší nepodporují Python 3.6 a může poskytnout chyba "Unsupported verze python 3.6". Používat jazyk Python, 3.5 nebo starší místo. |
| [IronPython](https://github.com/IronLanguages/main) | Implementace rozhraní .NET jazyka Python, k dispozici v 32bitové a 64bitové verze, C# / f # nebo Visual Basic zprostředkovatel komunikace s objekty, poskytuje přístup k rozhraní API technologie .NET, standardní Python ladění (ale ne C++ ve smíšeném režimu ladění) a ve smíšeném IronPython / C# ladění. IronPython, ale nepodporuje virtuální prostředí. | 
| [Anaconda](https://www.continuum.io) | Platformě vědecké účely open data používá technologii Python a obsahuje nejnovější verzi CPython a většina těžko instalovat balíčky. Doporučujeme, abyste ho nelze v opačném případě rozhodnete-li. |
| [PyPy](http://www.pypy.org/) | Vysoce výkonné trasování JIT, provádění Python, který je vhodný pro dlouhodobé programy a situacích slouží k určení výkonu problémy, ale nemůže najít jiné řešení. Funguje s Visual Studio, ale s omezenou podporu pro pokročilé funkce ladění. |
| [Jython](http://www.jython.org/) | Implementace jazyka Python na virtuální počítač Java (JVM). Podobá se IronPython, kód spuštěný v Jython mohou komunikovat s třídy jazyka Java a knihovny, ale nemusí být možné používat mnoho knihovny určené pro CPython. Funguje s Visual Studio, ale s omezenou podporu pro pokročilé funkce ladění. |

Vývojáři, které chcete přidat nové formuláře detekce prostředí Python, zobrazit [PTVS prostředí detekce](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (webu github.com).

## <a name="managing-python-environments-in-visual-studio"></a>Správa prostředí Python v sadě Visual Studio

Otevřete okno prostředí Python, proveďte jednu z následujících akcí:

1. Vyberte **zobrazení > ostatní okna > prostředí Python** příkazu nabídky.
1. Klikněte pravým tlačítkem myši **prostředí Python** pro projekt v Průzkumníku řešení a vyberte **zobrazení všech prostředí Python**:

    ![Zobrazit všechna prostředí příkazu v Průzkumníku řešení](media/environments-view-all.png)

V obou případech se zobrazí okno prostředí Python jako karty na stejné úrovni do Průzkumníka řešení:

![Okno prostředí Python](media/environments-default-view.png)

Výše uvedený příklad ukazuje, že Python 3.4 (32bitová verze CPython) je nainstalována spolu s 32bitové a 64bitové verze IronPython 2.7. V takovém případě je výchozí prostředí tučným Python 3.4, který se používá pro všechny nové projekty. Pokud nevidíte žádné prostředí uvedené, znamená to, že jste nainstalovali nástroje Python Tools pro sadu Visual Studio v sadě Visual Studio 2015 nebo dřívější, ale nebyly nainstalovány překladač Pythonu (viz [zvolíte a instalace Python překladače](#selecting-and-installing-python-interpreters) výše). 

> [!Tip]
> Když **prostředí Python** prostředí jsou uvedené v horní části a různé karty v dolní části, je omezený, jako v příkladu nahoře. Okno dostatečně zvětšující však změny široké zobrazení, které možná pohodlnější pro práci s.
>
> ![Zobrazení v okně rozšířit prostředí Python](media/environments-expanded-view.png)

> [!Note]
> I když Visual Studio respektuje možnost balíčky systému lokality, neposkytuje způsob, jak změnit z Visual Studia.

### <a name="creating-an-environment-for-an-existing-interpreter"></a>Vytvoření prostředí pro existující překladač

Visual Studio normálně vyhledá nainstalované překladač Pythonu kontrolou registru (následující [období 514 - Python registrace v registru Windows](https://www.python.org/dev/peps/pep-0514/)). Ale Visual Studio nemusí být pokud překladač je nainstalován v nestandardním způsobem. V takových případech můžete odkazovat Visual Studio přímo překladač následujícím způsobem:

1. Vyberte **+ vlastní...**  v [okno prostředí Python](#managing-python-environments-in-visual-studio), který vytváří nové prostředí a otevře [ **konfigurace** kartě](#configure-tab) popsané dál.)

    ![Výchozí zobrazení pro novou vlastní prostředí](media/environments-custom-1.png)

1. Zadejte název pro prostředí v **popis** pole.
1. Zadejte nebo vyhledejte cestu překladač v **předponu cesta** pole.
1. Vyberte **automatické rozpoznání** mít Visual Studio dokončit zbývající pole nebo je dokončit ručně.
1. Vyberte **použít** uložit prostředí.
1. Pokud je třeba odebrat prostředí, vyberte **odebrat** příkaz na **konfigurace** kartě. Automatické rozpoznání prostředí nenabízí tuto možnost. Najdete v části Další informace.

### <a name="moving-an-existing-interpreter"></a>Přesunutí existující překladač

Pokud přesouváte existující překladač do nového umístění v systému souborů, Visual Studio nerozpozná automaticky změnu. Ruční kroky jsou nezbytné k aktualizaci seznamu v okně prostředí:

- Pokud jste původně vytvořili prostředí pro tento překladač, upravte prostředí tak, aby odkazoval na nové umístění.

- Pokud prostředí byl původně automaticky zjištěna, byla nainstalována na počítač s odlišné instalační program, který vytvořili položky registru, které hledá v sadě Visual Studio. Nejdříve obnovte v tomto případě překladač Pythonu do původního umístění. Pak odinstalujte ji pomocí instalačního programu, který vymaže položky registru. Potom přeinstalujte překladač v požadovaném umístění. Restartování sady Visual Studio a by měl automaticky rozpoznat nové umístění. Tento proces zajistí, že jsou správně použití jiné vedlejší účinky instalačního programu.

### <a name="overview-tab"></a>Karta Přehled

Poskytuje základní informace a příkazy pro prostředí:

![Karta Přehled prostředí Python](media/environments-overview-tab.png)

| Příkaz | Popis |
| --- | --- |
| Nastavit jako výchozí pro nové projekty toto prostředí | Nastaví active prostředí, které může způsobit, že Visual Studio se stručně přestane reagovat při načítání databázi IntelliSense. Prostředí s mnoha balíčky může být po delší dobu reagovat. |
| Navštívit webovou stránku distributorovi | Otevře prohlížeč na adresu URL od distribuci jazyka Python. Python 3.x, například přejde k python.org. |
| Otevřete okno interaktivní | Otevře se [interaktivních okna (REPL)](interactive-repl.md) pro toto prostředí v sadě Visual Studio použití žádné [spouštěcí skripty (viz níže)](#startup-scripts). |
| Použití IPython interaktivním režimu | Pokud nastavíte, otevře se okno interaktivní s IPython ve výchozím nastavení. Tato povoleno vložené ukazuje zeměpisný a rozšířené syntaxe IPython například `name?` chcete zobrazit nápovědu a `!command` pro příkazy prostředí. Tato možnost se doporučuje při použití distribuci Anaconda, jako je vyžaduje další balíčky. Další informace najdete v tématu [pomocí IPython v okně interaktivní](interactive-repl-ipython.md). |
| Otevřete v prostředí PowerShell | Spustí překladač v příkazové okno prostředí PowerShell. |
| (Složky odkazů) | Poskytují rychlý přístup k prostředí nástroje instalační složku, překladač python.exe a pythonw.exe překladač. První otevře v Průzkumníku Windows, dvou otevřete okno konzoly. |

#### <a name="startup-scripts"></a>Spouštěcí skripty

Interaktivní windows používáte ve svém pracovním postupu každý den, pravděpodobně vyvíjet pomocných funkcí, které používáte pravidelně. Například můžete vytvořit funkci, která otevře DataFrame v aplikaci Excel a pak uložte tento kód jako spouštěcí skript tak, aby byla vždy dostupná v okně interaktivní.

Spouštěcí skripty obsahovat kód, který interaktivních okna načte a spustí automaticky, včetně importy, definice funkcí a oznámena cokoliv jiného. Takové skripty odkazují dvěma způsoby:

1. Při instalaci prostředí sady Visual Studio vytvoří složku `Documents\Visual Studio 2017\Python Scripts\<environment>` kde &lt;prostředí & gt "odpovídá názvu prostředí. Můžete snadno přejít do složky specifické pro prostředí s **prozkoumat interaktivní skripty** příkaz. Při spuštění interaktivních okna pro prostředí se načítá a spouští ať `.py` se zde nacházejí soubory v abecedním pořadí.

1. **Skripty** řídit ve **nástroje > Možnosti > Python Tools > Interaktivní Windows** karta (najdete v části [možnosti interaktivního windows](options.md#interactive-windows-options)) slouží k určení dalších Složka pro spouštěcí skripty, které jsou načteny a spustit ve všech prostředích. Tato funkce se však v současné době nefunguje.

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

Spravuje balíčky nainstalované v prostředí, což umožňuje také vyhledat a nainstalovat nové (včetně závislostí). Hledání filtry vaší aktuálně nainstalovaných balíčků a [úložiště PyPI](https://pypi.python.org). Můžete také přímo zadat libovolný `pip install` příkaz do vyhledávacího pole, včetně příznaky, jako například `--user` nebo `--no-deps`.

![Karta pip prostředí Python](media/environments-pip-tab.png)

Instalace balíčku vytvoří podsložky v rámci v prostředí `Lib` složku v systému souborů. Například pokud máte Python 3.6, které se instaluje v `c:\Python36`, balíčky jsou nainstalovány v `c:\Python36\Lib`; Pokud máte nainstalovaný v Anaconda3 `c:\Program Files\Anaconda3` pak balíčky jsou nainstalovány v `c:\Program Files\Anaconda3\Lib`.

V takovém případě protože prostředí je umístěný v oblasti chráněného systému souborů, `c:\Program Files`, musíte spustit Visual Studio `pip install` zvýšenými tak, aby ji k vytvoření balíčku podsložky. Pokud se vyžaduje zvýšení oprávnění, sada Visual Studio zobrazí řádku "oprávnění správce může být nutné nainstalovat, aktualizovat nebo odebrat balíčky pro toto prostředí":

![Výzva ke zvýšení oprávnění pro instalaci balíčku](media/environments-pip-elevate.png)

**Zvýšení oprávnění teď** uděluje oprávnění pro nástrojem pip pro jednu operaci, správu subjektu také všechny operační systémy vyzve k zadání oprávnění. Výběr **pokračovat bez oprávnění správce** pokusy o instalaci balíčku, ale pip selže při pokusu o vytvoření složky s výstupem, jako "Chyba: Nepodařilo se vytvořit" C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': bylo odepřeno oprávnění. "

Výběr **vždy zvýšení oprávnění při instalaci nebo odebrání balíčků** dialogu zabraňuje zobrazování pro prostředí. Chcete-li se znovu zobrazí dialogové okno, přejděte na **nástroje > Možnosti > Python Tools > Obecné** a kliknutím na tlačítko, **resetovat všechny trvale skrytá dialogová okna**. 

V tom, že stejné možnosti kartě, můžete také vybrat **vždy spustit jako správce pip** o potlačení pro všechna prostředí. V tématu [možnosti - karta Obecné](options.md#general-options).

### <a name="intellisense-tab"></a>Karta IntelliSense

Ukazuje aktuální stav databáze doplňování IntelliSense:

![Karta IntelliSense prostředí Python](media/environments-intellisense-tab.png)

Databáze obsahuje metadata pro všechny prostředí knihovny a zvyšuje rychlost IntelliSense a snižuje využití paměti. Když zjistí nového prostředí sady Visual Studio (nebo je přidat jeden), automaticky se začne při kompilaci databáze analýzou zdrojové soubory knihovny. Tento proces může trvat z minutu na hodinu nebo déle v závislosti na tom, co je nainstalované. (Anacondu, například se dodává s mnoha knihovny a při kompilaci databáze nějakou dobu trvá.) Po dokončení můžete získat podrobné IntelliSense a nemusíte znovu aktualizujte databázi (s **aktualizovat DB** tlačítko) až po instalaci dalších knihoven.

Knihovny, pro které nebyla kompilována data jsou označené **!**; Pokud prostředí s databáze není kompletní, **!** také se zobrazí vedle sebe v seznamu hlavní prostředí.

## <a name="global-environments"></a>Globální prostředí

Globální (nebo systémové) prostředí jsou k dispozici pro všechny projekty na počítači. Sada Visual Studio automaticky obvykle zjistí globální prostředí a lze zobrazit v [okno prostředí Python](#managing-python-environments-in-visual-studio). Pokud ne, můžete přidat prostředí ručně pomocí této stejného časového období.

Visual Studio používá výchozí prostředí pro všechny nové projekty pro provádění, ladění, kontrola syntaxe, zobrazování, importu a dokončování člen a další úlohy, které vyžadují prostředí. Změna výchozího prostředí má vliv na všechny projekty, ve kterých nebylo [specifické pro projekt prostředí](#project-specific-environments) přidali, jak je popsáno dále.

## <a name="project-specific-environments"></a>Specifické pro projekt prostředí

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

## <a name="virtual-environments"></a>Virtuální prostředí

Protože balíčky nainstalované do globální prostředí jsou k dispozici na všechny projekty, které ho používají, je v konfliktu může dojít, pokud dva projekty vyžadují Nekompatibilní balíčky nebo různé verze stejného balíčku. Aby nedošlo ke konfliktům, Visual Studio poskytuje možnost vytvářet *virtuální prostředí*, které jsou obvykle specifické do projektu.

Jako další prostředí Python virtuálního prostředí se skládá z překladač Pythonu, knihovny a sadu balíčků. V takovém případě ale virtuálního prostředí používá překladač a knihovna z jedné globální prostředí (za předpokladu, že podporuje virtuální prostředí), ale jeho balíčky jsou oddělené a izolované od na globální a všechny ostatní virtuální prostředí. Tato izolace znovu zabraňuje konflikty a minimalizuje virtuální prostředí nároky na přibližnou velikost jeho balíčků. 

Vytvoření virtuálního prostředí:

1. Klikněte pravým tlačítkem na **prostředí Python** v Průzkumníku řešení a vyberte **přidat virtuální prostředí...** , který spustí následující:

    ![Vytvoření virtuálního prostředí](media/environments-add-virtual-1.png)

1. Zadejte název pro vytvoření virtuálního prostředí v cestě vašeho projektu, nebo úplnou cestu k jeho vytvoření jinde. (Pro zajištění maximální kompatibility pomocí jiných nástrojů, používejte pouze písmena a čísla v názvu.)

1. Jako základní překladač vyberte globální prostředí a klikněte na tlačítko **vytvořit**. Pokud `pip` a `virtualenv` nebo `venv` balíčky nejsou dostupné, budou staženy a nainstalovány.

    Pokud zadaná cesta obsahuje existující virtuální prostředí, je zjištěna základní překladač a tlačítko pro vytvoření změny **přidat**:

    ![Přidání existujícího virtuálního prostředí](media/environments-add-virtual-2.png)

Existující virtuální prostředí se dá přidat taky kliknutím pravým tlačítkem na **prostředí Python** v Průzkumníku řešení a výběrem **přidat existující virtuální prostředí...** . Visual Studio automaticky zjišťuje základní překladač pomocí `orig-prefix.txt` souboru v prostředí nástroje `lib` adresáře.

Po přidání virtuálního prostředí do projektu se zobrazí v **prostředí Python** okno, můžete ji aktivujete jako jakékoli jiné prostředí, a můžete spravovat své balíčky. Pravým tlačítkem a vyberete **odebrat** buď odebere odkaz na prostředí, nebo odstraní prostředí a všechny jeho soubory na disku (ale ne základní překladač).

Všimněte si, že jednou z nevýhod virtuální prostředí je, že budou obsahovat cesty k souborům pevně a proto nelze snadno být sdílené nebo přenosu na jiné počítače vývoj. Naštěstí můžete použít `requirements.txt` souboru, jak je popsáno v následující části.

## <a name="managing-required-packages"></a>Správa požadované balíčky

Pokud jste sdílení projektu s ostatními, použití systému sestavení nebo plánujete [publikování do služby Microsoft Azure](template-azure-cloud-service.md), je třeba zadat externí balíčky vyžaduje. Doporučuje se používat [soubor requirements.txt](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org) obsahující seznam příkazů pro pip, který nainstaluje požadované verze závislé balíčky.

Technicky libovolný název souboru může sloužit k sledování požadavků (pomocí `-r <full path to file>` při instalaci balíčku), ale Visual Studio poskytuje konkrétní podporu pro `requirements.txt`:

- Pokud jste načíst projekt, který obsahuje `requirements.txt` a chcete instalovat všechny balíčky uvedené v tomto souboru, rozbalte **prostředí Python** uzlu v **Průzkumníku řešení**, klikněte pravým tlačítkem uzel prostředí a vyberte možnost **nainstalovat z requirements.txt**:

    ![Nainstalovat z requirements.txt](media/environments-requirements-txt-install.png)

- Pokud již máte všechny potřebné balíčky nainstalované v projektu, můžete v prostředí, v Průzkumníku řešení klikněte pravým tlačítkem a vyberte **generovat soubor requirements.txt** k vytvoření souboru nezbytné. Pokud soubor již existuje, jak se zobrazí výzva k její aktualizaci:

    ![Možnosti requirements.txt aktualizace](media/environments-requirements-txt-replace.png)

    - **Nahradí celý soubor** odebere všechny položky, komentáře a možnosti, které existují.
    - **Aktualizovat existující položky** zjistí požadavků balíčku a aktualizuje verze specifikátory tak, aby odpovídaly aktuálně nainstalovanou verzi.
    - **Aktualizace a přidání položky** aktualizuje všechny požadavky, které se nacházejí a přidá všechny ostatní balíčky na konec souboru.

Protože `requirements.txt` soubory jsou určeny k freeze – požadavky na projektu, všechny nainstalované balíčky jsou zapsány s přesné verze. Použití přesné verze zajišťuje, že budete moci snadno opakovat prostředí na jiném počítači. Balíčky jsou zahrnuty i v případě, že byly instalovány s rozsahem verze jako závislost jiný balíček, nebo instalační program než pip.

Pokud` requirements.txt` soubor existuje při přidávání nové virtuální prostředí, **Přidání virtuálního prostředí** dialogovém okně se zobrazí možnost automaticky, instalaci balíčků a usnadňuje tak znovu vytvořit prostředí na jiném počítači:

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

S typickému využití Python `PYTHONPATH` proměnnou prostředí (nebo `IRONPYTHONPATH`atd) poskytuje výchozí cesta hledání pro soubory modulu. To znamená, když použijete `import <name>` prohlášení, Python, první hledání jeho integrované moduly pro odpovídající název a potom složka hledání obsahující Python kódu je spouštěno, pak prohledá "Cesta pro hledání modulu" podle definice příslušné prostředí Proměnná. (V tématu [Path hledání modulu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) a [proměnné prostředí](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) v základní dokumentace Python.)

Proměnné prostředí path hledání, ale je ignorován v sadě Visual Studio, i když je nastavená pro celý systém. Je ignorován ve skutečnosti, přesněji *protože* je nastavena pro celý systém a proto vyvolá určité otázek, které nelze automaticky zodpovězeny: odkazovaný moduly, které jsou určené výhradně pro Python 2.7 nebo Python 3.3? Budou se přepsat standardní knihovna moduly? Vývojář si je vědoma toto chování nebo je škodlivý zneužití pokus?

Podpora v jazyce Python v sadě Visual Studio tak poskytuje i prostředky ke specifikaci cest hledání přímo v prostředí a projekty. Cesty hledání se předávají jako hodnotu `PYTHONPATH` (nebo ekvivalentního) při ladění nebo spuštění skriptu ze sady Visual Studio. Přidáním cesty hledání Visual Studio zkontroluje knihovny v těchto umístěních a vytvoří databáze IntelliSense pro ně (vytváření, ke které databáze může chvíli trvat v závislosti na počtu knihovny).

Chcete-li přidat cestu vyhledávání, klikněte pravým tlačítkem na **cesty hledání** položky v Průzkumníku řešení, vyberte **přidat složku do cesty pro hledání...** a vyberte složku, kterou chcete zahrnout. Tato cesta je používána pro jakékoli prostředí přidružený k projektu.

Soubory s `.zip` nebo `.egg` rozšíření lze také přidat jako cesty hledání tak, že vyberete **přidat archivu Zip do cesty pro hledání...** . Stejně jako u složky, obsah tyto soubory jsou kontrolovány a k dispozici pro technologii IntelliSense.

> [!Note]
> Je možné přidat cestu vyhledávání modulů Python 2.7, když používáte Python 3.3 a mohou zobrazit v důsledku chyby.

Pokud používáte pravidelně stejné cesty pro hledání a obsah se často nemění, může být efektivnější k její instalaci do vaší lokality balíčky složky. Ho je pak možné analyzovat a uloženy v databázi IntelliSense, je vždycky být přidružen prostředí určený a nevyžaduje cesta hledání přidávaného pro každý projekt.
