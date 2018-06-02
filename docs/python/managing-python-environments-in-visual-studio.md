---
title: Správa prostředí Python a překladače
description: Použijte okno prostředí Python a spravovat globální, virtuální a conda prostředí, instalace překladače Python a balíčky a přiřazení prostředí k projektů sady Visual Studio.
ms.date: 05/22/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d8c500b5f10f424cf60d92fd75a77e0ccb55866e
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34477571"
---
# <a name="how-to-create-and-manage-python-environments-in-visual-studio"></a>Jak vytvořit a spravovat prostředí Python v sadě Visual Studio

Python *prostředí* je kontext, ve kterém můžete spustit kód Python a zahrnuje globální, virtuální a conda prostředí. Prostředí se skládá z překladač knihovny (obvykle Python standardní knihovny) a sadu instalovaných balíčků. Tyto součásti společně určují, které jazykové konstrukty a syntaxe jsou platné, spouštění jaký operační systém funkce mají přístup a které balíčky, které můžete použít.

V sadě Visual Studio v systému Windows [okno prostředí Python](#the-python-environments-window) okno, jak je popsáno v tomto článku je kde spravovat těchto prostředí a vyberte jedno jako výchozí pro nové projekty. Pro daný projekt, můžete také [vyberte konkrétní prostředí](selecting-a-python-environment-for-a-project.md) místo použití výchozí.

**Poznámka:**: Pokud jste ještě Python v sadě Visual Studio, najdete v následujících článcích pro potřeby pozadí:

- [Práce s Python v sadě Visual Studio](overview-of-python-tools-for-visual-studio.md)
- [Instalace podpory Python v sadě Visual Studio](installing-python-support-in-visual-studio.md)

Poznámka prostředí pro Python kód, který je nemůžete spravovat, taky otevřít pouze jako složek pomocí **soubor** > **otevřete** > **složky** příkaz. Místo toho [vytvořit projekt Python z existujícího kódu](quickstart-01-python-in-visual-studio-project-from-existing-code.md) abyste mohli využívat funkce prostředí sady Visual Studio.

Pokud chcete instalovat balíčky v prostředí, podívejte se na [balíčky kartě odkaz](python-environments-window-tab-reference.md#packages-tab).

## <a name="types-of-environments"></a>Typy prostředí

### <a name="global-environments"></a>Globální prostředí

Instalace jednotlivých Python (například Python 2.7, Python 3.6, Anaconda 4.4.0, atd., najdete v části [výběr a instalace Python překladače](installing-python-interpreters.md)) udržuje vlastní globální prostředí. Každé prostředí se skládá z konkrétní překladač Pythonu, jeho standardní knihovna a sadu předem nainstalované balíčky. Instalaci balíčku do globální prostředí bude dostupná pro všechny projekty pomocí prostředí. Pokud prostředí je umístěný v oblasti Ochrana systému souborů (v rámci `c:\program files`, například), pak instalace balíčků vyžaduje oprávnění správce.

Globální prostředí jsou k dispozici pro všechny projekty v počítači. V sadě Visual Studio vyberte jeden globální prostředí jako výchozí, což se použije pro všechny projekty Pokud zvolíte jinou pro projekt. Další informace najdete v tématu [výběr prostředí pro projekt](selecting-a-python-environment-for-a-project.md).

### <a name="virtual-environments"></a>Virtuální prostředí

Protože balíčky nainstalované do globální prostředí jsou k dispozici na všechny projekty, které používají prostředí, je v konfliktu může dojít, pokud dva projekty vyžadují Nekompatibilní balíčky nebo různé verze stejného balíčku. Virtuální prostředí vyhnout takové konflikty pomocí překladač a standardní knihovny z globální prostředí ale udržování své vlastní balíček úložišť v izolovaném složek.

V sadě Visual Studio můžete vytvořit virtuální prostředí pro konkrétní projekt, který je uložený v podsložce v projektu. Visual Studio poskytuje příkazu, který bude generovat `requirements.txt` souboru z virtuálního prostředí, což usnadňuje znovu vytvořit prostředí v jiných počítačích. Další informace najdete v tématu [pomocí virtuální prostředí](selecting-a-python-environment-for-a-project.md#using-virtual-environments).

### <a name="conda-environments"></a>Conda prostředí

Prostředí conda je vytvořené pomocí `conda` nástroj, nebo pomocí integrovaného conda správy v nástroji Visual Studio 2017 15.7 a vyšší verze. (Vyžaduje Anaconda nebo Miniconda; Anaconda je k dispozici prostřednictvím Instalační program sady Visual Studio, najdete v části [instalaci – Visual Studio 2017](installing-python-support-in-visual-studio.md#visual-studio-2017).)

> [!Note]
> Chcete-li dosáhnout nejlepších výsledků s conda prostředí, použijte conda 4.4.8 nebo novější (conda verze se liší od verze Anaconda). Instalaci z instalačního programu Visual Studio 2017 Anaconda 5.1

Pokud chcete zjistit verzi conda, kde jsou uloženy conda prostředí, a další informace, spusťte `conda info` Anaconda příkazového řádku (to znamená, příkazový řádek kde Anaconda je v cestě):

```cli
conda info
```

Vaše prostředí složky conda zobrazit takto:

```output
       envs directories : c:\anaconda3\envs
                          C:\Users\user\AppData\Local\conda\conda\envs
                          C:\Users\user\.conda\envs
```

Protože conda prostředí nejsou uložené s projektem, že fungují podobně do globální prostředí. Například instalaci nového balíčku do prostředí conda zpřístupní tento balíček na všechny projekty pomocí prostředí.

Pro Visual Studio 2017 15.6 a starší verze, můžete použít conda prostředí tak, že odkazuje na ně ručně, jak je popsáno v části [ručně identifikovat stávajícího prostředí](#manually-identify-an-existing-environment).

Visual Studio 2017 verze 15.7 a novější conda prostředí automaticky zjistí a zobrazí je v **prostředí Python** okno, jak je popsáno v následující části.

## <a name="the-python-environments-window"></a>Okno prostředí Python

Prostředí, které zná Visual Studio se zobrazí v **prostředí Python** okno. Otevřete okno, použijte jednu z následujících metod:

- Vyberte **zobrazení** > **ostatní okna** > **prostředí Python** příkazu nabídky.
- Klikněte pravým tlačítkem myši **prostředí Python** uzel pro projekt v Průzkumníku řešení a vyberte **zobrazení všech prostředí Python**:

    ![Zobrazit všechna prostředí příkazu v Průzkumníku řešení](media/environments-view-all.png)

V obou případech **prostředí Python** okno se zobrazí jako karty na stejné úrovni do Průzkumníka řešení:

![Okno prostředí Python](media/environments-default-view.png)

Pokud nevidíte očekávané prostředí v seznamu, přečtěte si téma [ručně identifikovat stávajícího prostředí](#manually-identify-an-existing-environment).

Výběr prostředí v seznamu zobrazí různé vlastnosti a příkazy pro prostředí na **přehled** kartě. Například, uvidíte na předchozím obrázku, zda je umístění překladač `C:\Python36-32`. Pomocí rozevíracího seznamu pod seznamem prostředí můžete přepnout na různé karty, jako **balíčky**, a **IntelliSense**. Tyto karty jsou popsané v [prostředí Python okno karty](python-environments-window-tab-reference.md).

Výběr prostředí neaktivuje žádným způsobem. Výchozí prostředí, zobrazeny tučným v seznamu je aktuálně aktivovaný prostředí, ve kterém sada Visual Studio používá pro všechny nové projekty. Chcete-li aktivovat jiné prostředí, použijte **vytvořit prostředí výchozí pro nové projekty** příkaz. V kontextu projektu aktivací vždy do různých prostředí. Další informace najdete v tématu [výběr prostředí pro projekt](selecting-a-python-environment-for-a-project.md).

Napravo od jednotlivých uvedených prostředí je ovládací prvek, které se otevře okno s interaktivní pro prostředí. (Visual Studio 2017 15,5 a starší, další ovládací prvek se zobrazit se aktualizuje databázi IntelliSense pro prostředí. V tématu [prostředí okno karty](python-environments-window-tab-reference.md#intellisense-tab) podrobnosti o databázi).

> [!Tip]
> Po rozbalení **prostředí Python** okno dost široké, získat úplnější zobrazení vašeho prostředí, které mohou být pro práci s pohodlnější.
>
> ![Zobrazení v okně rozšířit prostředí Python](media/environments-expanded-view.png)

> [!Note]
> I když Visual Studio respektuje možnost balíčky systému lokality, neposkytuje způsob, jak změnit z Visual Studia.

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | [Podívejte se na video (Microsoft Virtual Academy)](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567) na prostředí Python v sadě Visual Studio (2 m 35s).|

### <a name="what-if-no-environments-appear"></a>Co dělat, když se zobrazí žádné prostředí?

Pokud se zobrazí žádné prostředí, znamená to, Visual Studio se nepodařilo zjistit všechny instalace Python ve standardní umístění. Například může máte nainstalované Visual Studio 2017, ale vymazat všechny možnosti překladač v instalační možnosti pro pracovní vytížení Python. Podobně nainstaloval Visual Studio 2015 a starší ale nenainstalovala překladač ručně (najdete v části [instalaci Python překladače](installing-python-interpreters.md)).

Pokud znáte máte překladač Pythonu ve vašem počítači, ale Visual Studio (všechny verze) není zjišťovat a potom použít **+ vlastní...**  příkazu ručně zadejte jeho umístění. Najdete v části Další [ručně identifikovat stávajícího prostředí](#manually-identify-an-existing-environment).

> [!Tip]
> Visual Studio zjišťuje aktualizace na stávající interpret, jako je například upgrade Python 2.7.11 k 2.7.14 pomocí instalační programy z python.org. Během procesu instalace starší prostředí dané zařízení zmizí z **prostředí Python** seznamu před zobrazí se místo ní.
>
> Ale pokud přesunete ručně překladač a jeho prostředí pomocí systému souborů, Visual Studio nebude vědět nové umístění. Další informace najdete v tématu [přesun překladač](installing-python-interpreters.md#moving-an-interpreter).

< a name = "ručně identifikace existující prostředí ></a>

## <a name="manually-identify-an-existing-environment"></a>Ručně identifikovat stávajícího prostředí

Prostředí, který je nainstalován v nestandardním umístění (včetně conda prostředí Visual Studio 2017 verze 15.6 a starší) pomocí následujících kroků:

1. Vyberte **+ vlastní** v **prostředí Python** okno, které se otevře **konfigurace** karty:

    ![Výchozí zobrazení pro novou vlastní prostředí](media/environments-custom-1.png)

1. Zadejte název pro prostředí v **popis** pole.

1. Zadejte nebo vyhledejte (pomocí **... ***) k cestě překladač v **předponu cesta** pole.

1. Pokud Visual Studio zjistí překladač Pythonu v tomto umístění (například cesta pro prostředí conda vidíte níže), umožňuje **automatické rozpoznání** příkaz. Výběr **automatické rozpoznání* dokončení zbývající pole. Tato pole můžete také dokončit ručně.

    ![Povolení automatické rozpoznání příkaz](media/environments-custom-2.png)

    ![Dokončení polí prostředí po použití automatické rozpoznání](media/environments-custom-3.png)

1. Po pole obsahují hodnoty, které chcete, vyberte **použít** konfiguraci uložíte. Teď můžete použít v prostředí, stejně jako jakýkoli jiný v sadě Visual Studio.

1. Pokud musíte odstranit ručně identifikovaných prostředí, vyberte **odebrat** příkaz na **konfigurace** kartě. Automatické rozpoznání prostředí nenabízí tuto možnost. Další informace najdete v tématu [karta konfigurace](python-environments-window-tab-reference.md#configure-tab).

## <a name="create-a-conda-environment"></a>Vytvořte prostředí conda

*Visual Studio 2017 verze 15.7 a novější.*

1. Vyberte **+ vytvořit conda prostředí** v **prostředí Python** okna, což otevře **vytvořit nové prostředí conda** karty:

    ![Vytvoření karty pro nové prostředí conda](media/environments-conda-1.png)

1. Zadejte název pro prostředí v **název** vyberte základní překladač Pythonu ve **Python** pole a vyberte možnost **vytvořit**.

1. **Výstup** v okně se zobrazí průběh pro nové prostředí s několika pokyny rozhraní příkazového řádku po dokončení vytvoření:

    ![Úspěšné vytvoření conda prostředí](media/environments-conda-2.png)

1. V sadě Visual Studio, můžete aktivovat conda prostředí pro projekt, jako byste jiné prostředí, jak je popsáno na [výběr prostředí pro projekt](selecting-a-python-environment-for-a-project.md).

1. Chcete-li instalovat balíčky v prostředí, použijte [balíčky karta](python-environments-window-tab-reference.md#packages-tab).

## <a name="see-also"></a>Viz také:

- [Instalace překladače Python](installing-python-interpreters.md)
- [Výběr interpretu pro projekt](selecting-a-python-environment-for-a-project.md)
- [Používání souboru requirements.txt pro závislosti](managing-required-packages-with-requirements-txt.md)
- [Cesty pro hledání](search-paths.md)
- [Odkaz na okno prostředí Python](python-environments-window-tab-reference.md)