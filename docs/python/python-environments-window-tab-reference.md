---
title: Odkaz na okno prostředí Pythonu
description: Informace o jednotlivých karet, které se zobrazí v okně prostředí Pythonu v sadě Visual Studio.
ms.date: 05/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d4adc1ac472bb05affa547d795690dc7143655fd
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "34572121"
---
# <a name="python-environments-window-tabs-reference"></a>Odkaz na kartách okno prostředí Pythonu

Chcete-li otevřít **prostředí Pythonu** okno:

- Vyberte **zobrazení > ostatní Windows > prostředí Pythonu** příkazu nabídky.
- Klikněte pravým tlačítkem myši **prostředí Pythonu** uzel projektu v Průzkumníku řešení a vyberte **zobrazit všechna prostředí Pythonu**

Pokud rozbalíte **prostředí Pythonu** okno dost široké, tyto možnosti se zobrazí jako karty, které může být pro vás být vhodnější pro práci s. Pro přehlednost karty v tomto článku jsou uvedeny v rozbalené zobrazení.

![Okno prostředí Pythonu rozšířené zobrazení](media/environments-expanded-view.png)

## <a name="overview-tab"></a>Karta Přehled

Poskytuje základní informace a příkazy pro prostředí:

![Karta Přehled prostředí Pythonu](media/environments-overview-tab.png)

| Příkaz | Popis |
| --- | --- |
| Nastavit toto prostředí jako výchozí pro nové projekty | Nastaví na aktivní prostředí, což může způsobit, že Visual Studio (2017 verze 15.5 a starší) stručně přestane reagovat při načítání databáze IntelliSense. Prostředí s mnoha balíčky je možné jako nereagující po delší dobu. |
| Navštívit web distributora | Otevře prohlížeč na adresu URL poskytované distribuci jazyka Python. Python 3.x, například přejde na python.org. |
| Otevřít interaktivní okno | Otevře [interaktivního okna (REPL)](python-interactive-repl-in-visual-studio.md) pro toto prostředí v sadě Visual Studio, použití některou [spouštěcí skripty (viz níže)](#startup-scripts). |
| Prozkoumat interaktivní skripty | Zobrazit [spouštěcí skripty](#startup-scripts). |
| Použít interaktivní režim IPython | Pokud nastavíte, ve výchozím nastavení otevře interaktivní okno s ipythonem vzniká. Tato povolené vložené, který jako a také rozšířené syntaxe IPython `name?` zobrazíte nápovědu a `!command` pro příkazy prostředí. Tato možnost se doporučuje při použití Anaconda distribuce, protože vyžaduje dodatečné balíčky. Další informace najdete v tématu [pomocí IPython v interaktivním okně](interactive-repl-ipython.md). |
| Otevřít v Powershellu | Spuštění interpretu v příkazovém okně prostředí PowerShell. |
| (Složka a program odkazů) | Poskytují rychlý přístup k prostředí instalační složku, překladač python.exe a překladač pythonw.exe. První zobrazí v Průzkumníku Windows, druhé dvě otevřete okno konzoly. |

### <a name="startup-scripts"></a>Spouštěcí skripty

V pracovním postupu vaší každý den používáte interaktivních oken, pravděpodobně vývoj pomocných funkcí, které používáte pravidelně. Může například vytvořit funkci, která se otevře datový rámec v Excelu a uložte tento kód jako spouštěcí skript tak, aby byla vždy dostupná v interaktivním okně.

Spouštěcí skripty obsahovat kód, který interaktivní okno načte a spustí automaticky, včetně importy, definice funkcí a prakticky cokoli jiného. Tyto skripty jsou odkazovány dvěma způsoby:

1. Při instalaci prostředí sady Visual Studio vytvoří složku `Documents\Visual Studio 2017\Python Scripts\<environment>` kde &lt;prostředí&gt; odpovídá názvu prostředí. Můžete snadno přejít do složky specifické pro prostředí s **prozkoumat interaktivní skripty** příkazu. Při spuštění interaktivní okno pro toto prostředí se načte a spustí cokoli, co `.py` zde nacházejí soubory v abecedním pořadí.

1. **Skripty** v ovládacím prvku **nástroje > Možnosti > Nástroje Pythonu > Interaktivní Windows** kartu (naleznete v tématu [interaktivních oken možnosti](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options)) slouží k určení dalších Složka pro spouštěcí skripty, které jsou načteny a spustit ve všech prostředích. Tato funkce se však nefunguje v současné době.

## <a name="configure-tab"></a>Karta Konfigurace

Pokud je k dispozici, obsahuje podrobnosti, jak je popsáno v následující tabulce. Pokud tato karta není k dispozici, znamená to, že Visual Studio automaticky spravuje všechny podrobnosti.

![Karta Konfigurace prostředí Pythonu](media/environments-configure-tab.png)

| Pole | Popis |
| --- | --- |
| **Popis** | Název prostředí. |
| **Předponová cesta** | Umístění složky základní překladač. Vyplnění tuto hodnotu a kliknutím na **automaticky rozpoznat**, Visual Studio se pokusí vyplnit i ostatní pole za vás. |
| **Cesta k interpretu** | Cesta k interpretu spustitelný soubor, obvykle předponová cesta za nímž následuje `python.exe` |
| **Interpret v okně** | Cesta k mimo konzolu spustitelný soubor, často následuje předponová cesta `pythonw.exe`. |
| **Cestu ke knihovně**<br/>(Pokud je k dispozici) | Určuje kořenový standardní knihovnu, ale tato hodnota může ignorovat, pokud je schopen žádat přesnější cestu interpretu sady Visual Studio. |
| **Verze jazyka** | Vybrat z rozevírací nabídky. |
| **Architektura** | Obvykle zjištěno a vyplní automaticky, v opačném případě určuje 32bitové nebo 64bitové. |
| **Proměnné prostředí Path** | Proměnná prostředí, která překladač používá k vyhledání cesty pro hledání. Visual Studio se změní hodnota proměnné při spuštění Pythonu tak, aby obsahoval cesty pro hledání v projektu. Obvykle by tato vlastnost nastavená na `PYTHONPATH`, ale některých interpretů použít jinou hodnotu. |

## <a name="packages-tab"></a>Karta balíčky

*Také s popiskem "pip" v dřívějších verzích.*

Spravuje balíčky nainstalované ve prostředí pomocí nástroje pip, díky tomu můžete také vyhledat a nainstalovat nové balíčky (včetně případných závislostí). V sadě Visual Studio 2017 verze 15.7 nebo novější **balíčky (Conda)** využívající Správce balíčků conda místo toho se zobrazí karta. (Pokud se nezobrazí široké možnosti volby, nastavte možnost **nástroje** > **možnosti** > **Python** > **experimentální**   >  **Použití Správce balíčků conda Pokud je k dispozici (místo pip)** a restartujte aplikaci Visual Studio.)

Balíčky, které jsou už nainstalované, se zobrazí s ovládacími prvky pro aktualizaci (šipka nahoru) a odinstalujte (X v kruhu), balíček:

![Karta balíčky prostředí Pythonu](media/environments-pip-tab-controls.png)

Zadání vyhledávacích filtrů termín seznam nainstalovaných balíčků, jakož i balíčky, které je možné nainstalovat z PyPI.

![Karta balíčky prostředí Pythonu pomocí služby search na "počet"](media/environments-pip-tab.png)

Jak je vidět na obrázku výše, výsledky hledání zobrazit počet balíčků, které odpovídají hledanému výrazu; první položka v seznamu, ale příkaz pro spuštění `pip install <name>` přímo. Pokud ale používáte **balíčky (Conda)** kartě, zobrazí se místo toho `conda install <name>`:

![Příkaz instalovat kartu balíčků Conda ukazující conda](media/environments-conda-tab-install.png)

V obou případech můžete přizpůsobit instalaci tak, že přidáte argumenty za názvem balíčku do vyhledávacího pole. Pokud zahrnete argumenty, výsledky vyhledávání ukazuje `pip install` nebo `conda install` za nímž následuje obsah do vyhledávacího pole:

![Pomocí argumentů pip a conda install příkazy pro probuzení](media/environments-pip-tab-arguments.png)

Instalace balíčku vytvoří podsložky v rámci životního prostředí `Lib` složku v systému souborů. Například pokud máte Python 3.6, které se nainstaluje v `c:\Python36`, balíčky se nainstalují v `c:\Python36\Lib`; Pokud máte Anaconda3 nainstalované v `c:\Program Files\Anaconda3` pak balíčky se nainstalují v `c:\Program Files\Anaconda3\Lib`.

### <a name="granting-administrator-privileges-for-package-install"></a>Udělení oprávnění správce pro balíček nainstalovat

Při instalaci balíčků do prostředí, ve kterém se nachází v chráněné části systému souborů, jako například `c:\Program Files\Anaconda3\Lib`, musíte spustit aplikaci Visual Studio `pip install` se zvýšenými oprávněními, aby mohla vytvořit podsložky, balíčku. Když se vyžaduje zvýšení úrovně oprávnění, aplikace Visual Studio zobrazí řádku "správce můžou být nutná oprávnění k instalaci, aktualizaci nebo odebrání balíčků pro toto prostředí":

![Výzvy ke zvýšení oprávnění pro instalaci balíčku](media/environments-pip-elevate.png)

**Zvýšit** uděluje oprávnění správce k nástroje pip pro jednu operaci, předmět taky pro libovolný operační systém zobrazí výzvu k zadání oprávnění. Výběr **pokračovat bez oprávnění správce** pokusí nainstalovat, ale pip nezdaří při pokusu o vytvoření složky s výstupem, jako "Chyba: nepovedlo se vytvořit" C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': přístup byl odepřen. "

Výběr **vždy zvýšit při instalaci nebo odebrání balíčků** brání dialogového okna v zobrazení pro prostředí. Chcete-li se znovu zobrazí dialogové okno, přejděte na **nástroje > Možnosti > Nástroje Pythonu > Obecné** a klikněte na tlačítko **resetovat všechna trvale skrytá dialogová okna**.

V tom, že stejné možnosti kartu, můžete také vybrat **vždy spustit jako správce pip** k potlačení dialogového okna pro všechna prostředí. Zobrazit [možnosti – karta Obecné](python-support-options-and-settings-in-visual-studio.md#general-options).

### <a name="security-restrictions-with-older-versions-of-python"></a>Omezení zabezpečení se staršími verzemi Pythonu

Při použití Python 2.6, 3.1 a 3.2, sada Visual Studio zobrazí upozornění "z důvodu zabezpečení, které omezení instalace z Internetu, nemusí fungovat v této verzi jazyka Python":

![Zpráva o pip nainstalovat omezení starší verze jazyka Python](media/environments-old-version-restriction.png)

Důvod pro toto upozornění je, že se tyto starší verze jazyka Python, `pip install` neobsahuje podporu pro zabezpečení TLS (Transport Layer) 1.2, která je potřebná pro stahování balíčků ze zdroje balíčku, pypi.org. Vlastní sestavení Python v takovém případě podporu protokolu TLS 1.2 `pip install` mohou fungovat.

Je možné stáhnout si odpovídající `get-pip.py` pro balíček [bootstrap.pypa.io](https://bootstrap.pypa.io/), je nutné ručně stáhněte si balíček z [pypi.org](https://pypi.org/)a pak balíček nainstalujte z této místní kopii.

Doporučení, ale stačí upgradovat na Python 2.7 nebo 3.3 +, ve kterém případ upozornění se nezobrazí.

## <a name="intellisense-tab"></a>Karta IntelliSense

Zobrazí aktuální stav databáze pro dokončování IntelliSense:

![Karta IntelliSense prostředí Pythonu](media/environments-intellisense-tab.png)

- V **Visual Studio 2017 verze 15.5** a starší, dokončování IntelliSense závisí na databázi, která je kompilovaná pro danou knihovnu. Vytváření databáze se provádí na pozadí, když knihovně je nainstalovaná, ale může nějakou dobu trvat a nemusí být úplné, když začnete psát kód.
- **Visual Studio 2017 verze 15.6** a později pomocí metody rychlejší poskytují dokončování, které nezávisí na databázi ve výchozím nastavení. Z tohoto důvodu označené na kartě **IntelliSense [databáze deaktivována]**. Databázi můžete povolit zrušením možnost **nástroje** > **možnosti** > **Python**  >   **Experimentální** > **používaly nový styl IntelliSense pro prostředí**.

Po zjišťuje nové prostředí sady Visual Studio (nebo přidejte jedno), automaticky se začne při kompilaci databáze díky analýze zdrojové soubory knihovny. Tento proces může trvat od minutu hodinu nebo déle v závislosti na tom, co je nainstalována. (Anaconda, například se dodává s mnoha knihoven a kompilaci databáze nějakou dobu trvá.) Jakmile budete hotovi, získáte podrobný IntelliSense a není potřeba znovu aktualizujte databázi (s **aktualizace DB** tlačítko) až po instalaci další knihovny.

Knihovny, pro které nebyla kompilována data jsou označené **!**; Pokud databázích tohoto prostředí není kompletní, **!** také se vedle něj zobrazí v seznamu hlavních prostředí.

## <a name="see-also"></a>Viz také:

- [Správa prostředí Pythonu v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Cesty pro hledání](search-paths.md)
