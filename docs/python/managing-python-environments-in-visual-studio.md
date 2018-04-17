---
title: Správa prostředí Python a překladače
description: Jak používat prostředí Python oken v sadě Visual Studio ke správě globální a virtuální prostředí, nastavit vlastní prostředí, instalace překladače Python, instalace balíčků, nastavení cesty hledání a správu prostředí pro projekty v sadě Visual Studio.
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- devlang-python
ms.devlang: python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 1bff11b34f6f9a6a469230f30c636e65ab143e30
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="managing-python-environments-in-visual-studio"></a>Správa prostředí Python v sadě Visual Studio

Python *prostředí* je kontext, ve kterém můžete spustit kód Python a zahrnuje globální, virtuální a conda prostředí. Prostředí se skládá z překladač knihovny (obvykle Python standardní knihovny) a sadu instalovaných balíčků. Tyto součásti společně určují, které jazykové konstrukty a syntaxe jsou platné, spouštění jaký operační systém funkce mají přístup a které balíčky, které můžete použít.

V sadě Visual Studio v systému Windows [prostředí Python](#managing-python-environments-in-visual-studio) okno, jak je popsáno v tomto článku je kde spravovat těchto prostředí a vyberte jedno jako výchozí pro nové projekty. Pro daný projekt můžete také vyberte konkrétní prostředí místo použijte výchozí nastavení.

**Poznámka:**: Pokud jste ještě Python v sadě Visual Studio, najdete v následujících článcích pro potřeby pozadí:

- [Práce s Python v sadě Visual Studio](overview-of-python-tools-for-visual-studio.md)
- [Instalace podpory Python v sadě Visual Studio](installing-python-support-in-visual-studio.md)

Poznámka prostředí pro Python kód, který je nemůžete spravovat, taky otevřít pouze jako složku použitím **soubor > Otevřít > složky** příkaz. Místo toho [vytvořit projekt Python z existujícího kódu](quickstart-01-python-in-visual-studio-project-from-existing-code.md) abyste mohli využívat funkce prostředí sady Visual Studio.

Pokud chcete instalovat balíčky v prostředí, podívejte se na [balíčky karta](python-environments-window-tab-reference.md#packages-tab).

## <a name="types-of-environments"></a>Typy prostředí

### <a name="global-environments"></a>Globální prostředí

Instalace jednotlivých Python (například Python 2.7, Python 3.6, Anaconda 4.4.0, atd., najdete v části [výběr a instalace Python překladače](installing-python-interpreters.md)) udržuje vlastní globální prostředí. Každé prostředí se skládá z konkrétní překladač Pythonu, jeho standardní knihovna a sadu předem nainstalované balíčky. Instalaci balíčku do globální prostředí bude dostupná pro všechny projekty pomocí prostředí. Pokud prostředí je umístěný v oblasti Ochrana systému souborů (v rámci `c:\program files`, například), pak instalace balíčků vyžaduje oprávnění správce.

Globální prostředí jsou k dispozici pro všechny projekty v počítači. V sadě Visual Studio vyberte jeden globální prostředí jako výchozí, což se použije pro všechny projekty Pokud zvolíte jinou pro projekt. Další informace najdete v tématu [výběr prostředí pro projekt](selecting-a-python-environment-for-a-project.md).

### <a name="virtual-environments"></a>Virtuální prostředí

Protože balíčky nainstalované do globální prostředí jsou k dispozici na všechny projekty, které používají prostředí, je v konfliktu může dojít, pokud dva projekty vyžadují Nekompatibilní balíčky nebo různé verze stejného balíčku. Virtuální prostředí vyhnout takové konflikty pomocí překladač a standardní knihovny z globální prostředí ale udržování své vlastní balíček úložišť v izolovaném složek.

V sadě Visual Studio můžete vytvořit virtuální prostředí pro konkrétní projekt, který je uložený v podsložce v projektu. Visual Studio poskytuje příkazu, který bude generovat `requirements.txt` souboru z virtuálního prostředí, což usnadňuje znovu vytvořit prostředí v jiných počítačích. Další informace najdete v tématu [pomocí virtuální prostředí](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="conda-environments"></a>Conda prostředí

Prostředí conda je vytvořené pomocí `conda` nástroj. Conda prostředí jsou obvykle uložena v `envs` složky v rámci instalace Anaconda a proto akce podobně jako globální prostředí. Například instalaci nového balíčku do prostředí conda zpřístupní tento balíček na všechny projekty pomocí prostředí.

Visual Studio, v současné době automaticky nerozpozná conda prostředí, ale Visual Studio může ukazovat na ji ručně. V tématu [ručně Identifikace stávajícího prostředí](#manually-identifying-an-existing-environment).

## <a name="the-python-environments-window"></a>Okno prostředí Python

Prostředí, které zná Visual Studio se zobrazí v **prostředí Python** okno. Otevřete okno, použijte jednu z následujících metod:

- Vyberte **zobrazení > ostatní okna > prostředí Python** příkazu nabídky.
- Klikněte pravým tlačítkem myši **prostředí Python** uzel pro projekt v Průzkumníku řešení a vyberte **zobrazení všech prostředí Python**:

    ![Zobrazit všechna prostředí příkazu v Průzkumníku řešení](media/environments-view-all.png)

V obou případech **prostředí Python** okno se zobrazí jako karty na stejné úrovni do Průzkumníka řešení:

![Okno prostředí Python](media/environments-default-view.png)

Na obrázku výše vidíte, že Visual Studio zjistil dvou zařízení Python 3.6 (32 bitů) společně s Anaconda 5.0.0.

Výchozí prostředí tučným je 3.6 Python (v tomto případě část instalace Anaconda), který Visual Studio používá pro všechny nové projekty. Příkazy v dolní části okna platí pro vybraný jazyk Python 3.6 překladač, který jako jste viděli je konkrétní instalace v `C:\Python36-32`. Pokud nevidíte očekáváte, že prostředí, najdete v části [ručně Identifikace stávajícího prostředí](#manually-identifying-an-existing-environment).

Napravo od jednotlivých uvedených prostředí je ovládací prvek, které se otevře okno s interaktivní pro prostředí. Další ovládací prvek může se zobrazit se aktualizuje databázi IntelliSense pro prostředí (viz [odkaz na okno prostředí](python-environments-window-tab-reference.md#intellisense-tab) podrobnosti o databázi).

Pod seznamem prostředí je selektor rozevíracího seznamu pro **přehled**, **balíčky**, a **IntelliSense** možnosti popsané v [prostředí Python odkaz na kartě okno](python-environments-window-tab-reference.md). Navíc pokud rozbalíte **prostředí Python** okno dost široké, tyto možnosti se zobrazují jako karet, které možná pohodlnější pro práci s:

![Zobrazení v okně rozšířit prostředí Python](media/environments-expanded-view.png)

> [!Note]
> I když Visual Studio respektuje možnost balíčky systému lokality, neposkytuje způsob, jak změnit z Visual Studia.

|   |   |
|---|---|
| ![film ikonu fotoaparátu pro video](../install/media/video-icon.png "přehrát video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) na prostředí Python v sadě Visual Studio (2 m 35s).|

### <a name="what-if-no-environments-appear"></a>Co dělat, když se zobrazí žádné prostředí?

Pokud se zobrazí žádné prostředí, znamená to, Visual Studio se nepodařilo zjistit všechny instalace Python ve standardní umístění. Například může máte nainstalované Visual Studio 2017, ale vymazat všechny možnosti překladač v instalační možnosti pro pracovní vytížení Python. Podobně nainstaloval Visual Studio 2015 a starší ale nenainstalovala překladač ručně (najdete v části [instalaci Python překladače](installing-python-interpreters.md)).

Pokud znáte máte překladač Pythonu ve vašem počítači, ale Visual Studio (všechny verze) není zjišťovat a potom použít **+ vlastní...**  příkazu ručně zadejte jeho umístění. Najdete v části Další [ručně Identifikace stávajícího prostředí](#manually-identifying-an-existing-environment).

> [!Tip]
> Visual Studio zjišťuje aktualizace na stávající interpret, jako je například upgrade Python 2.7.11 k 2.7.14 pomocí instalační programy z python.org. Během procesu instalace starší prostředí dané zařízení zmizí z **prostředí Python** seznamu před zobrazí se místo ní.
>
> Ale pokud přesunete ručně překladač a jeho prostředí pomocí systému souborů, Visual Studio nebude vědět nové umístění. Další informace najdete v tématu [přesun překladač](installing-python-interpreters.md#moving-an-interpreter).

## <a name="manually-identifying-an-existing-environment"></a>Ručně Identifikace stávajícího prostředí

Prostředí, který je nainstalován v nestandardním umístění, včetně conda prostředí pomocí následujících kroků:

1. Vyberte **+ vlastní...**  v **prostředí Python** okno, které se otevře **konfigurace** karty:

    ![Výchozí zobrazení pro novou vlastní prostředí](media/environments-custom-1.png)

1. Zadejte název pro prostředí v **popis** pole.

1. Zadejte nebo vyhledejte (pomocí **... ***) k cestě překladač v **předponu cesta** pole.

1. Pokud Visual Studio zjistí překladač Pythonu v tomto umístění (například cesta pro prostředí conda vidíte níže), umožňuje **automatické rozpoznání** příkaz. Výběr **automatické rozpoznání* dokončení zbývající pole. Tato pole můžete také dokončit ručně.

    ![Povolení automatické rozpoznání příkaz](media/environments-custom-2.png)

    ![Dokončení polí prostředí po použití automatické rozpoznání](media/environments-custom-3.png)

1. Po pole obsahují hodnoty, které chcete, vyberte **použít** konfiguraci uložíte. Teď můžete použít v prostředí, stejně jako jakýkoli jiný v sadě Visual Studio.

1. Pokud musíte odstranit ručně identifikovaných prostředí, vyberte **odebrat** příkaz na **konfigurace** kartě. Automatické rozpoznání prostředí nenabízí tuto možnost. Další informace najdete v tématu [karta konfigurace](python-environments-window-tab-reference.md#configure-tab).

## <a name="see-also"></a>Viz také

- [Instalace překladače Python](installing-python-interpreters.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Python](python-environments-window-tab-reference.md)