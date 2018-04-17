---
title: Dynamické symbolický provádění | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Dynamic symbolic execution
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 083ee0e340688065ab765961676da63c405fd434
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="input-generatation-using-dynamic-symbolic-execution"></a>Vstupní generatation pomocí dynamické symbolický provádění

IntelliTest generuje vstupy pro [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing) analýzou podmínky větve v programu. Test vstupy jsou zvolen v závislosti na tom, jestli můžete aktivovat nový větvení chování programu. Analýza je přírůstkové proces. Zpřesnění predikát **Otázka: I -> {hodnotu true, false}** přes formální testovací vstupní parametry **I**. **q** představuje sadu chování, které již IntelliTest sledoval. Na začátku **q: = false**, protože nic ještě dodržen.

Kroky smyčky jsou:

1. IntelliTest určuje vstupy **i** tak, aby **q (i) = false** pomocí [Řešitel omezení](#constraint-solver). 
   Pomocí konstrukce, vstup **i** bude trvat cesta k provádění není nikdy dříve. Původně, to znamená, že **i** může být žádný vstup, protože neexistuje žádná cesta provádění ještě nebyla zjištěná.

1. IntelliTest provede test s vybraným vstupní **i**a sleduje spuštění testu a program v rámci testu.

1. Během provádění trvá programu na konkrétní cestu, která je dáno všechny větve podmíněného programu. Sada všechny podmínky, které určují, provádění se nazývá *podmínky cesty*napsaných jako predikát **p: I -> {hodnotu true, false}** přes formální vstupní parametry. IntelliTest vypočítá reprezentace této predikátu.

1. Nastaví IntelliTest **q: = (q nebo p)**. Jinými slovy, zaznamenává fakt, že zaznamenal cesty představované **p**.

1. Přejděte ke kroku 1.

Na IntelliTest [Řešitel omezení](#constraint-solver) můžete řeší hodnoty všech typů, které se mohou objevit v aplikacích .NET:

* [Celá čísla](#integers-and-floats) a [jako plovoucí](#integers-and-floats)
* [Objekty](#objects)
* [Struktury](#structs)
* [Pole](#arrays-and-strings) a [řetězce](#arrays-and-strings)

IntelliTest filtruje vstupních hodnot, které porušují stanovené předpoklady.

Kromě okamžitou vstupy (argumenty, které mají [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing)), test můžete navrhnout další vstupní hodnoty z [PexChoose](static-helper-classes.md#pexchoose) statická třída. Volby také určuje chování [parametry mocks](#parameterized-mocks).

<a name="constraint-solver"></a>
## <a name="constraint-solver"></a>Řešitel omezení

IntelliTest používá k určení vstupní hodnoty testovací a program testovaného Řešitel omezení.

Používá IntelliTest [Z3](https://github.com/Z3Prover/z3/wiki) Řešitel omezení.

<a name="dynamic-code-coverage"></a>
## <a name="dynamic-code-coverage"></a>Pokrytí kódu dynamické

Jako vedlejším účinkem modulu runtime, monitorování IntelliTest shromažďuje data pro pokrytí dynamický kód. To se označuje jako *dynamické* protože IntelliTest zná pouze o kód, který provedl, proto ji nelze poskytují absolutní hodnoty pro pokrytí stejným způsobem jako jiný nástroj pokrytí obvyklým způsobem. 

Například když IntelliTest ohlásí dynamické pokrytí jako základní bloky 5/10, to znamená, že pět bloky mimo deset byly zahrnuté, kde celkový počet bloků v všechny metody, které mají bylo dosaženo, pokud analýza (a všechny metody, které existují v ssembly testovaného) je 10.
Dále v analýzy, jako jsou dostupné další metody zjištění obou čítači (5 v této eaxmple) a může zvýšit jmenovatel (10).

<a name="integers-and-floats"></a>
## <a name="integers-and-floats"></a>Celá čísla a obtékaných objektů

Na IntelliTest [Řešitel omezení](#constraint-solver) určuje testování vstupní hodnoty typů primitiv, například **bajtů**, **int**, **float**a jiné v pořadí pro spuštění různých provádění cesty pro test a program v rámci testu.

<a name="objects"></a>
## <a name="objects"></a>Objekty

IntelliTest můžete buď [vytvoření instancí existujících tříd rozhraní .NET](#existing-classes), nebo můžete použít k IntelliTest automaticky [vytvořit mock objektů](#parameterized-mocks) , implementovat určité rozhraní a chovat různými způsoby v závislosti na využití.

<a name="existing-classes"></a>
## <a name="instantiating-existing-classes"></a>Vytváření instancí existujících tříd

**Co je problém?**

IntelliTest monitoruje spuštění pokyny při spuštění testu a program v rámci testu. Konkrétně monitoruje veškerý přístup na pole. Poté použije [Řešitel omezení](#constraint-solver) k určení nového vstupy test, včetně objektů a jejich hodnoty pole tak, aby byl test a program v testu budou chovat jinak zajímavé.

To znamená, že IntelliTest musí pro vytvoření určitých typů objektů a nastavení jejich hodnot polí. Pokud je třída [viditelné](#visibility) a má [viditelné](#visibility) výchozí konstruktor IntelliTest můžete vytvořit instance třídy.
Pokud jsou tato pole třídy [viditelné](#visibility), IntelliTest můžete nastavit pole automaticky.

Pokud není viditelná typ, nebo pole nejsou [viditelné](#visibility), IntelliTest musí nápovědu k vytváření objektů a přiřaďte je do zajímavé stavů k dosažení maximální kód pokrytí. IntelliTest využít reflexe k vytvoření a Inicializace instance libovolného způsoby, ale není to obvykle  
žádoucí, protože ho může přenést objekt do stavu, který může nikdy dojít během spuštění normální programu. Místo toho IntelliTest spoléhá na pomocné parametry od uživatele.

<a name="visibility"></a>
## <a name="visibility"></a>Viditelnost

Rozhraní .NET Framework má model vypracovala viditelnost: typy, metod, pole a ostatní členové může být **privátní**, **veřejné**, **interní**a další.

Pokud IntelliTest vygeneruje testy, pokusí se provádět jenom akce (například volání konstruktory, metody a nastavení polí), které jsou právní s ohledem na viditelnost pravidla technologie .NET z v kontextu generovaného testy.

Pravidla jsou následující:

* **Viditelnost členů interní**
  * IntelliTest předpokládá, že generovaný testy bude mít přístup k interní členy, které byly viditelné uzavření [PexClass](attribute-glossary.md#pexclass).
  Má .NET **InternalsVisibleToAttribute** rozšířit viditelnost vnitřní členy ostatních sestavení.<p />

* **Přehled privátního a členy rodiny (chráněné v C#) [PexClass](attribute-glossary.md#pexclass)**
  * IntelliTest vždy umístí generovaného testů přímo v [PexClass](attribute-glossary.md#pexclass) nebo do podtřídy. Proto IntelliTest předpokládá, že ho může využívat všechny viditelné rodinných příslušnících (**chráněné** v jazyce C#).
  * Pokud generovaného testy jsou umístěny přímo do [PexClass](attribute-glossary.md#pexclass) (obvykle s použitím částečné třídy), IntelliTest předpokládá, že ho může také používat všichni členové privátní [PexClass](attribute-glossary.md#pexclass).<p />

* **Viditelnost veřejné členy**
  * IntelliTest předpokládá, že ho může využívat všechny exportovaný členů zobrazených v kontextu [PexClass](attribute-glossary.md#pexclass).

<a name="parameterized-mocks"></a>
## <a name="parameterized-mocks"></a>Parametrizované mocks

Postup testování metodu, která má parametr typu rozhraní? Nebo třídy nezapečetěných? IntelliTest nebude vědět, které implementace se později použije, když tato metoda je volána. A pravděpodobně není k dispozici i skutečné implementace k dispozici v době testu.

Konvenční odpověď je použití *model objektů* s explicitní chování. 

Objekt imitované implementuje rozhraní (nebo rozšiřuje třídu nezapečetěných). Nepředstavuje se skutečné implementace, ale pouze zástupce, který umožňuje provádění testů pomocí mock objektu. Její chování je definována ručně v rámci každé testovacího případu, kdy se používá. Existují celou řadu nástrojů, které usnadňují definovat mock objektů a jejich očekávané chování, ale toto chování je stále ručně definovat.

Místo pevně definovaných hodnot v mock objektů můžete vygenerovat IntelliTest hodnoty. Stejně jako umožňuje [parametrizované testování částí](test-generation.md#parameterized-unit-testing), IntelliTest taky umožňuje parametrizované mMocks.

Parametrizované mocks mít dva režimy různých spuštění:

* **Výběr**: při prohlížení kódu, parametrizované mocks jsou zdroj další testovací vstupy a IntelliTest se pokusí o zvolte zajímavé hodnoty
* **opakování**: při provádění testu vytvořených předtím, parametrizované mocks chovají jako zástupných procedur s chováním (jinými slovy, předdefinované chování).

Použití [PexChoose](static-helper-classes.md#pexchoose) získat hodnoty pro parametrizované mocks.

<a name="structs"></a>
## <a name="structs"></a>Struktury

IntelliTest je důvody o **struktura** hodnoty se podobně jako se zabývá [objekty](#objects).

<a name="arrays-and-strings"></a>
## <a name="arrays-and-strings"></a>Pole a řetězce

IntelliTest monitoruje spuštění pokyny při jeho spuštění testu a program v rámci testu. Konkrétně dodržuje, když program závisí na délka řetězce nebo pole (a dolní meze a délek vícerozměrné). Také zaznamenává, jak program používá jiný elementy řetězec nebo pole. Poté použije [Řešitel omezení](#constraint-solver) k určení, které délky a hodnoty element může způsobit, že test a program testovaného chovat v zajímavými způsoby.

IntelliTest se pokusí minimální velikost pole a řetězců, které jsou potřeba k aktivaci zajímavé chování programu.

<a name="additional-inputs"></a>
## <a name="obtaining-additional-inputs"></a>Získání dalších vstupy

[PexChoose](static-helper-classes.md#pexchoose) statická třída slouží k získání dalších vstupy do testu a lze použít k implementaci [parametry mocks](#parameterized-mocks).

<a name="further-reading"></a>
## <a name="further-reading"></a>Další čtení

* [Jak to funguje?](https://blogs.msdn.microsoft.com/visualstudioalm/2014/12/11/smart-unit-tests-a-mental-model/)

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
