---
title: "Odkaz na okno prostředí Python - Visual Studio | Microsoft Docs"
description: "Údaje na každé kartě, které se zobrazují v okně prostředí Python v sadě Visual Studio."
ms.custom: 
ms.date: 02/20/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 92d5014c257cf35e556eca1928e1c5612f4913eb
ms.sourcegitcommit: c0a2385a16cc4f47d2e1ff23d35c4da40f5605e0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/23/2018
---
# <a name="python-environments-window-tabs-reference"></a>Odkaz na prostředí Python okno karty

Chcete-li otevřít **prostředí Python** okno:

- Vyberte **zobrazení > ostatní okna > prostředí Python** příkazu nabídky.
- Klikněte pravým tlačítkem myši **prostředí Python** uzel pro projekt v Průzkumníku řešení a vyberte **zobrazení všech prostředí Python**

Pokud rozbalíte **prostředí Python** okno dost široké, tyto možnosti se zobrazují jako karet, které možná pohodlnější pro práci s. Pro přehlednost zobrazí se v rozšířené zobrazení karty v tomto článku.

![Zobrazení v okně rozšířit prostředí Python](media/environments-expanded-view.png)

## <a name="overview-tab"></a>Karta Přehled

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
| (Odkazy složku a program) | Poskytují rychlý přístup k prostředí nástroje instalační složku, překladač python.exe a pythonw.exe překladač. První otevře v Průzkumníku Windows, dvou otevřete okno konzoly. |

### <a name="startup-scripts"></a>Spouštěcí skripty

Interaktivní windows používáte ve svém pracovním postupu každý den, pravděpodobně vyvíjet pomocných funkcí, které používáte pravidelně. Například můžete vytvořit funkci, která otevře DataFrame v aplikaci Excel a pak uložte tento kód jako spouštěcí skript tak, aby byla vždy dostupná v okně interaktivní.

Spouštěcí skripty obsahovat kód, který interaktivních okna načte a spustí automaticky, včetně importy, definice funkcí a oznámena cokoliv jiného. Takové skripty odkazují dvěma způsoby:

1. Při instalaci prostředí sady Visual Studio vytvoří složku `Documents\Visual Studio 2017\Python Scripts\<environment>` kde &lt;prostředí & gt "odpovídá názvu prostředí. Můžete snadno přejít do složky specifické pro prostředí s **prozkoumat interaktivní skripty** příkaz. Při spuštění interaktivních okna pro prostředí se načítá a spouští ať `.py` se zde nacházejí soubory v abecedním pořadí.

1. **Skripty** řídit ve **nástroje > Možnosti > Python Tools > Interaktivní Windows** karta (najdete v části [možnosti interaktivního windows](python-support-options-and-settings-in-visual-studio.md#interactive-windows-options)) slouží k určení dalších Složka pro spouštěcí skripty, které jsou načteny a spustit ve všech prostředích. Tato funkce se však v současné době nefunguje.

## <a name="configure-tab"></a>Karta Konfigurace

Pokud je k dispozici, obsahuje podrobnosti, jak je popsáno v následující tabulce. Pokud není k dispozici na této kartě, znamená to, že Visual Studio je Správa všech podrobností o automaticky.

![Karta Konfigurace prostředí Python](media/environments-configure-tab.png)

| Pole | Popis |
| --- | --- |
| **Popis** | Název prostředí. |
| **Předpona cesta** | Umístění složky základní překladač. Naplnění tuto hodnotu a kliknutím na **automatické rozpoznání**, Visual Studio se pokusí vyplňte další pole za vás. |
| **Překladač cesta** | Cesta k překladač spustitelný soubor, běžně cesta předponu následuje `python.exe` |
| **Oddílové překladač** | Cesta k mimo konzolu spustitelný soubor, často cesta předponou následuje `pythonw.exe`. |
| **Cesta ke knihovně**<br/>(Pokud je k dispozici) | Určuje kořenu standardní knihovny, ale pokud tato hodnota může být ignorována Visual Studio je schopen přesnější cestu požadavku z překladač. |
| **Jazyková verze** | Vybrat v rozevírací nabídce. |
| **Architektura** | Za normálních okolností zjištěna a vyplnit automaticky, v opačném případě určuje 32bitové nebo 64bitové verze. |
| **Proměnné prostředí Path** | Proměnné prostředí, která překladač používá k nalezení cest hledání. Visual Studio změní hodnotu proměnné při spouštění Python tak, aby obsahoval cesty pro hledání projektu. Obvykle tato vlastnost by měla být nastavená na `PYTHONPATH`, ale některé překladače použít jinou hodnotu. |

## <a name="packages-tab"></a>Karta balíčky

*Také s označením "pip" v dřívějších verzích.*

Spravuje balíčky nainstalované v prostředí, což umožňuje hledat a instalovat nové (včetně závislostí). Hledání filtry vaší aktuálně nainstalovaných balíčků a [úložiště PyPI](https://pypi.python.org). Můžete také přímo zadat libovolný `pip install` příkaz do vyhledávacího pole, včetně příznaky, jako například `--user` nebo `--no-deps`.

![Karta balíčky prostředí Python](media/environments-pip-tab.png)

Instalace balíčku vytvoří podsložky v rámci v prostředí `Lib` složku v systému souborů. Například pokud máte Python 3.6, které se instaluje v `c:\Python36`, balíčky jsou nainstalovány v `c:\Python36\Lib`; Pokud máte nainstalovaný v Anaconda3 `c:\Program Files\Anaconda3` pak balíčky jsou nainstalovány v `c:\Program Files\Anaconda3\Lib`.

V takovém případě protože prostředí je umístěný v oblasti chráněného systému souborů, `c:\Program Files`, musíte spustit Visual Studio `pip install` zvýšenými tak, aby ji k vytvoření balíčku podsložky. Pokud se vyžaduje zvýšení oprávnění, sada Visual Studio zobrazí řádku "oprávnění správce může být nutné nainstalovat, aktualizovat nebo odebrat balíčky pro toto prostředí":

![Výzva ke zvýšení oprávnění pro instalaci balíčku](media/environments-pip-elevate.png)

**Zvýšení oprávnění teď** uděluje oprávnění pro nástrojem pip pro jednu operaci, správu subjektu také všechny operační systémy vyzve k zadání oprávnění. Výběr **pokračovat bez oprávnění správce** pokusy o instalaci balíčku, ale pip selže při pokusu o vytvoření složky s výstupem, jako "Chyba: Nepodařilo se vytvořit" C:\Program Files\Anaconda3\Lib\site-packages\ PNG.PY': bylo odepřeno oprávnění. "

Výběr **vždy zvýšení oprávnění při instalaci nebo odebrání balíčků** dialogu zabraňuje zobrazování pro prostředí. Chcete-li se znovu zobrazí dialogové okno, přejděte na **nástroje > Možnosti > Python Tools > Obecné** a kliknutím na tlačítko, **resetovat všechny trvale skrytá dialogová okna**.

V tom, že stejné možnosti kartě, můžete také vybrat **vždy spustit jako správce pip** o potlačení pro všechna prostředí. V tématu [možnosti - karta Obecné](python-support-options-and-settings-in-visual-studio.md#general-options).

## <a name="intellisense-tab"></a>Karta IntelliSense

Ukazuje aktuální stav databáze doplňování IntelliSense:

![Karta IntelliSense prostředí Python](media/environments-intellisense-tab.png)

Databáze obsahuje metadata pro všechny prostředí knihovny a zvyšuje rychlost IntelliSense a snižuje využití paměti. Když zjistí nového prostředí sady Visual Studio (nebo je přidat jeden), automaticky se začne při kompilaci databáze analýzou zdrojové soubory knihovny. Tento proces může trvat z minutu na hodinu nebo déle v závislosti na tom, co je nainstalované. (Anacondu, například se dodává s mnoha knihovny a při kompilaci databáze nějakou dobu trvá.) Po dokončení můžete získat podrobné IntelliSense a nemusíte znovu aktualizujte databázi (s **aktualizovat DB** tlačítko) až po instalaci dalších knihoven.

Knihovny, pro které nebyla kompilována data jsou označené **!**; Pokud prostředí s databáze není kompletní, **!** také se zobrazí vedle sebe v seznamu hlavní prostředí.

## <a name="see-also"></a>Viz také

- [Správa prostředí Python v sadě Visual Studio](managing-python-environments-in-visual-studio.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md) 
- [Cesty pro hledání](search-paths.md)
