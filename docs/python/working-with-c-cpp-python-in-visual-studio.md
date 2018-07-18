---
title: Práce s C++ a Python
description: Návod k vytvoření rozšíření C++ pro Python s pomocí sady Visual Studio, včetně ladění ve smíšeném režimu.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: fc885df4b85e89c85c366f033113678243fbfe0b
ms.sourcegitcommit: 4ab232758d308bda742434beff8349a80c167890
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847814"
---
# <a name="creating-a-c-extension-for-python"></a>Vytvoření rozšíření C++ pro Python

Abychom rozšířili možnosti překladač Pythonu a aby umožnila přístup k funkcím nízké úrovně operačního systému se běžně používají moduly napsanými v C++ (nebo C). Existují tři hlavní typy modulů:

- Akcelerátor moduly: protože interpretovaný jazyk Python se určité části kódu můžete napsaný v jazyce C++ pro vyšší výkon.
- Obálka moduly: zveřejňují rozhraní existující C/C++ na kód v Pythonu nebo zpřístupnit další rozhraní API "Pythonic", který se snadno používá z Pythonu.
- Nižší úrovně systému přístup moduly: vytvoření pro přístup k nižší úrovni funkcím CPython runtime, operační systém nebo základního hardwaru.

Tento článek vás provede sestavení C++ rozšiřující modul pro CPython, která vypočítá hyperbolický tangens a volá z kódu Pythonu. Rutina je implementováno nejprve v jazyce Python k předvedení relativní výkonový zisk plynoucí z implementace stejnou rutinu v jazyce C++.

Přístup provádět je, že pro standardní CPython rozšíření jak je popsáno v [dokumentace pro Python](https://docs.python.org/3/c-api/). Porovnání mezi touto a jinými způsoby je popsaný v části [přístupy](#alternative-approaches) na konci tohoto článku.

Je hotová ukázka z tohoto návodu můžete najít na [python ukázky vs-cpp-extension](https://github.com/Microsoft/python-sample-vs-cpp-extension) (GitHub).

## <a name="prerequisites"></a>Požadavky

- Visual Studio 2017 s oběma **Desktop Development with C++** a **vývoj v jazyce Python** úlohy, které jsou nainstalované s výchozími možnostmi.
- V **vývoj v jazyce Python** pracovního vytížení, také vybrat pole na pravé straně pro **nástroje Pythonu pro nativní vývoj**. Tato možnost nastaví většinu konfiguraci popsané v tomto článku. (Tato možnost také zahrnuje úlohy pro C++ automaticky.)

    ![Výběr možnosti nástrojů nativního vývoje v Pythonu](media/cpp-install-native.png)

    > [!Tip]
    > Instalace **pro datové vědy a analytické aplikace** úloh také zahrnuje Python a **nástroje Pythonu pro nativní vývoj** možnost ve výchozím nastavení.

Další informace najdete v tématu [instalace podpory Pythonu pro Visual Studio](installing-python-support-in-visual-studio.md), včetně použití ostatních verzí sady Visual Studio. Pokud instalujete Python samostatně, je potřeba vybrat možnost **stáhnout symboly ladění** a **ladicí binární soubory ke stažení** pod **rozšířené možnosti** v instalačním programu. Tato možnost zajišťuje, že máte k dispozici knihovny pro potřeby ladění, pokud budete chtít provést sestavení pro ladění.

## <a name="create-the-python-application"></a>Vytvoření aplikace v Pythonu

1. Vytvoření nového projektu Pythonu v sadě Visual Studio tak, že vyberete **soubor > Nový > projekt**. Vyhledejte "Python", vyberte **aplikace v Pythonu** šablony, nabízí vhodný název a umístění a vyberte **OK**.

1. Práce s jazykem C++ vyžaduje, že používáte interpret Pythonu 32 bitů (doporučeno Python 3.6). V **Průzkumníka řešení** okno sady Visual Studio, rozbalte uzel projektu a potom rozbalte položku **prostředí Pythonu** uzlu. Pokud nevidíte 32-bit prostředí jako výchozí (buď v tučné písmo nebo s popiskem s "globální výchozí nastavení"), postupujte podle pokynů [výběr prostředí Pythonu pro projekt](selecting-a-python-environment-for-a-project.md). Pokud nemáte k dispozici 32-bit překladač nainstalovaný, přečtěte si téma [interpretů Pythonu instalace](installing-python-interpreters.md).

1. V projektu `.py` soubor, vložte následující kód, který benchmarks výpočtu hyperbolický tangens (implementováno bez použití matematické knihovny pro snazší porovnání). Můžete zadat kód ručně, aby se některé z prostředí [Python funkce úprav](editing-python-code-in-visual-studio.md).

    ```python
    from itertools import islice
    from random import random
    from time import perf_counter

    COUNT = 500000  # Change this value depending on the speed of your computer
    DATA = list(islice(iter(lambda: (random() - 0.5) * 3.0, None), COUNT))

    e = 2.7182818284590452353602874713527

    def sinh(x):
        return (1 - (e ** (-2 * x))) / (2 * (e ** -x))

    def cosh(x):
        return (1 + (e ** (-2 * x))) / (2 * (e ** -x))

    def tanh(x):
        tanh_x = sinh(x) / cosh(x)
        return tanh_x

    def sequence_tanh(data):
        '''Applies the hyperbolic tangent function to map all values in
        the sequence to a value between -1.0 and 1.0.
        '''
        result = []
        for x in data:
            result.append(tanh(x))
        return result

    def test(fn, name):
        start = perf_counter()
        result = fn(DATA)
        duration = perf_counter() - start
        print('{} took {:.3f} seconds\n\n'.format(name, duration))

        for d in result:
            assert -1 <= d <= 1, " incorrect values"

    if __name__ == "__main__":
        print('Running benchmarks with COUNT = {}'.format(COUNT))

        test(sequence_tanh, 'sequence_tanh')

        test(lambda d: [tanh(x) for x in d], '[tanh(x) for x in d]')
    ```

1. Spuštění programu pomocí **ladit > Spustit bez ladění** (Ctrl + F5) a zobrazit výsledky. Můžete upravit `COUNT` proměnné, chcete-li změnit, jak dlouho trvá srovnávací testy ke spuštění. Pro účely tohoto názorného postupu nastavte počet tak, aby každý srovnávací test trvá přibližně 2 sekundy.

## <a name="create-the-core-c-project"></a>Vytvoření projektu C++ core

1. Klikněte pravým tlačítkem na řešení v Průzkumníku řešení a vyberte **Přidat > Nový projekt...** . Řešení sady Visual Studio může obsahovat Python a C++ projektů najednou (což je jednou z výhod pomocí sady Visual Studio pro jazyk Python).

1. Hledání na "C++", vyberte **prázdný projekt**, zadejte název (Tento článek používá "superfastcode") a vyberte **OK**.

    > [!Tip]
    > S **nástroje Pythonu pro nativní vývoj** nainstalovaná v sadě Visual Studio 2017, můžete začít s **rozšiřující modul Pythonu** šablony místo toho, který má v podstatě co je popsáno níže již v místě. V tomto návodu, počínaje prázdný projekt ukazuje vytvoření rozšíření modulu krok za krokem. Jakmile pochopíte procesu šablony vám šetří čas při psaní vlastních rozšíření.

1. Vytvoření souboru jazyka C++ v novém projektu kliknutím pravým tlačítkem myši **zdrojové soubory** uzlu, pak vyberte **Přidat > Nová položka... "** vyberte **soubor C++**, pojmenujte ho `module.cpp`, a Vyberte **OK**.

    > [!Important]
    > Soubor s `.cpp` rozšíření je potřeba zapnout na stránkách vlastností jazyka C++ v následujících kroků.

1. Klikněte pravým tlačítkem na projekt C++ v řešení, vyberte **vlastnosti**.

1. V horní části **stránky vlastností** dialogové okno, které se zobrazí, nastavte **konfigurace** k **všechny konfigurace** a **platformy** k **Win32**.

1. Nastavit konkrétní vlastnosti, jak je popsáno v následující tabulce a pak vyberte **OK**.

    | Tabulátor | Vlastnost | Hodnota |
    | --- | --- | --- |
    | Obecné | Obecné > název cílové | Zadejte název modulu, jak chcete na něj odkazovat z Pythonu v `from...import` příkazy. Použijte tento stejný název v C++, při definování modulu pro Python. Pokud chcete použít název projektu jako název modulu, ponechte výchozí hodnotu `$(ProjectName)`. |
    | | Obecné > cílit na rozšíření | .pyd |
    | | Výchozí nastavení projektu > typ konfigurace | Dynamická knihovna (.dll) |
    | C/C++ > Obecné | Další adresáře souborů k zahrnutí | Přidat Python `include` složky jako odpovídající vaší instalaci, například `c:\Python36\include`.  |
    | C/C++ > preprocesoru | Definice preprocesoru | Přidat `Py_LIMITED_API;` na začátku řetězce (středník). Tato definice omezuje některé funkce může volat z Pythonu a činí kód mezi různými verzemi Pythonu. |
    | C/C++ > generování kódu | Knihovna prostředí runtime | Vícevláknová DLL (/ MD) (viz následující upozornění) |
    | Linker > Obecné | Další adresáře knihoven | Přidat Python `libs` složku obsahující `.lib` soubory podle potřeby pro vaši instalaci, například `c:\Python36\libs`. (Ujistěte se, aby odkazoval na `libs` složku, která obsahuje `.lib` soubory, a *není* `Lib` složku, která obsahuje `.py` souborů.) |

    > [!Tip]
    > Pokud nevidíte kartu jazyka C/C++ ve vlastnostech projektu, je to, protože projekt neobsahuje žádné soubory, které identifikuje jako zdrojové soubory jazyka C/C++. K tomuto stavu může dojít, pokud vytvořte zdrojový soubor bez `.c` nebo `.cpp` rozšíření. Například pokud nechtěně zadáte `module.coo` místo `module.cpp` v dialogovém okně Nový položky dříve, pak Visual Studio vytvoří soubor, ale tento typ souboru není nastavena na "C / C + kódu," což je co aktivuje na kartě Vlastnosti C/C++. Takové misidentification zůstane tak i v případě, přejmenujte soubor s `.cpp`. Typ souboru nastavit správně, klikněte pravým tlačítkem na soubor v Průzkumníku řešení, vyberte **vlastnosti**, nastavte **typ souboru** k **kódu C/C++**.

    > [!Warning]
    > Vždycky nastavený **C/C++ > generování kódu > knihovny prostředí Runtime** možnost "Vícevláknová DLL (/ MD)", i pro konfiguraci ladění, protože toto nastavení je, co jsou vybaveny binární soubory Pythonu bez ladění. Pokud jste se nastavit "Vícevláknová DLL pro ladění (/ MDd)" možnost vytváření konfigurace ladění způsobil chybu *C1189: Py_LIMITED_API není kompatibilní s Py_DEBUG Py_TRACE_REFS a Py_REF_DEBUG*. Kromě toho pokud odeberete `Py_LIMITED_API` aby se zabránilo chybě sestavení, Python, dojde k chybě při pokusu o import modulu. (Selhání dojde během volání knihovny DLL `PyModule_Create` jak je popsáno dále, výstupní zpráva z *Python závažná chyba: PyThreadState_Get: žádná aktuální vlákno*.)
    >
    > Možnost/MDd sloužící k sestavení ladicí binární soubory Pythonu (například python_d.exe), ale že ji vyberete rozšiřující knihovny DLL stále způsobuje chybu sestavení s `Py_LIMITED_API`.

1. Klikněte pravým tlačítkem na projekt C++ a vyberte **sestavení** k otestování konfigurace (Debug a Release). `.pyd` Soubory jsou umístěny v *řešení* ve složce **ladění** a **vydání**, ne C++ projektu samotné složce.

1. Přidejte následující kód do projektu C++ `module.cpp` souboru:

    ```cpp
    #include <Windows.h>
    #include <cmath>

    const double e = 2.7182818284590452353602874713527;

    double sinh_impl(double x) {
        return (1 - pow(e, (-2 * x))) / (2 * pow(e, -x));
    }

    double cosh_impl(double x) {
        return (1 + pow(e, (-2 * x))) / (2 * pow(e, -x));
    }

    double tanh_impl(double x) {
        return sinh_impl(x) / cosh_impl(x);
    }
    ```

1. Sestavení projektu C++ znovu pro potvrzení, že váš kód je správný.

## <a name="convert-the-c-project-to-an-extension-for-python"></a>Převeďte projekt C++ rozšíření pro Python

Chcete-li knihovny DLL C++ do rozšíření pro Python, nejdřív změnit exportovaných metod pro interakci s typy Python. Potom přidáte funkci, která se exportuje modul včetně definice metod modulu.

Další informace o jaké je uvedené v této části pro Python 3.x, odkazovat [referenční příručce rozhraní API Python/C](https://docs.python.org/3/c-api/index.html) a hlavně [objekty modulu](https://docs.python.org/3/c-api/module.html) na webu python.org (Nezapomeňte si vyberte verzi jazyka Python z rozevírací seznam v pravém horním rohu zobrazíte správnou dokumentaci).

Pokud pracujete se Python 2.7, použijte místo toho [rozšíření Python 2.7 pomocí jazyka C nebo C++](https://docs.python.org/2.7/extending/extending.html) a [portování rozšiřující moduly Pythonu 3](https://docs.python.org/2.7/howto/cporting.html) (python.org).

1. V souboru C++ zahrnují `Python.h` v horní části:

    ```cpp
    #include <Python.h>
    ```

1. Upravit `tanh_impl` metody přijímají a vrací typy Pythonu ( `PyOjbect*`, to znamená):

    ```cpp
    PyObject* tanh_impl(PyObject *, PyObject* o) {
        double x = PyFloat_AsDouble(o);
        double tanh_x = sinh_impl(x) / cosh_impl(x);
        return PyFloat_FromDouble(tanh_x);
    }
    ```

1. Přidat strukturu, která definuje jak C++ `tanh_impl` funkce se zobrazí Pythonu:

    ```cpp
    static PyMethodDef superfastcode_methods[] = {
        // The first property is the name exposed to Python, fast_tanh, the second is the C++
        // function name that contains the implementation.
        { "fast_tanh", (PyCFunction)tanh_impl, METH_O, nullptr },

        // Terminate the array with an object containing nulls.
        { nullptr, nullptr, 0, nullptr }
    };
    ```

1. Přidat strukturu, která definuje modulu, které chcete na ni odkazovat v kódu Python, zejména při použití `from...import` příkazu. (To odpovídat hodnotě ve vlastnostech projektu v rámci **vlastnosti konfigurace > Obecné > název cílového**.) V následujícím příkladu, název modulu "superfastcode" znamená, slouží `from superfastcode import fast_tanh` v Pythonu, protože `fast_tanh` je definována v rámci `superfastcode_methods`. (Interní do projektu jazyka C++, jako je module.cpp, názvů souborů jsou irelevantní.)

    ```cpp
    static PyModuleDef superfastcode_module = {
        PyModuleDef_HEAD_INIT,
        "superfastcode",                        // Module name to use with Python import statements
        "Provides some functions, but faster",  // Module description
        0,
        superfastcode_methods                   // Structure that defines the methods of the module
    };
    ```

1. Přidejte metodu, která Python volá při načtení modulu, který musí mít název `PyInit_<module-name>`, kde *&lt;module_name&gt;* přesně odpovídá projektu C++ **Obecné > název cílového** vlastnosti (to znamená, název souboru odpovídá `.pyd` sestavené projektem).

    ```cpp
    PyMODINIT_FUNC PyInit_superfastcode() {
        return PyModule_Create(&superfastcode_module);
    }
    ```

1. Nastavení konfigurace cílového "Verze" a sestavení projektu C++ znovu k ověření kódu. Pokud narazíte na chyby, zkontrolujte následující případy:
    - Nepovedlo se najít Python.h (*E1696: Nelze otevřít zdrojový soubor "Python.h"* a/nebo *C1083: nejde otevřít vložený soubor: "Python.h": žádný odpovídající soubor nebo adresář*): Ověřte, že ji v **C/C++ > Obecné > Další adresáře souborů k zahrnutí** v bodech vlastnosti projektu k instalaci Pythonu `include` složky. Přejděte ke kroku 6 v části [vytvoření projektu core C++](#create-the-core-c-project).
    - Nepovedlo se najít knihovny jazyka Python: Ověřte, že cestu ve **Linker > Obecné > Další adresáře knihoven** v bodech vlastnosti projektu k instalaci Pythonu `libs` složky. Přejděte ke kroku 6 v části [vytvoření projektu core C++](#create-the-core-c-project).
    - Chyby linkeru týkající se Cílová architektura: Změňte architekturu projektu C++ cíl odpovídat vaší instalaci Pythonu. Například pokud cílíte x64 s projektu jazyka C++, ale instalace Pythonu x86, změňte projekt C++ pro cílení x86.

## <a name="test-the-code-and-compare-the-results"></a>Testování kódu a porovnejte výsledky

Teď, když máte knihovnu DLL strukturované jako rozšíření Python, můžete na něj odkazovat z projektu Pythonu, naimportujte modul a použijte její metody.

### <a name="make-the-dll-available-to-python"></a>Zpřístupnění knihovny DLL pro Python

Existují dva způsoby, jak zpřístupnit knihovny DLL pro Python.

První metoda funguje v případě Pythonu projekt a projekt C++ jsou ve stejném řešení. Přejděte do Průzkumníku řešení klikněte pravým tlačítkem myši **odkazy** uzlu v projektu Pythonu a pak vyberte **přidat odkaz**. V zobrazeném dialogu vyberte **projekty** kartu, vyberte **superfastcode** projektu (nebo cokoli, co název používáte) a potom **OK**.

![Přidání odkazu na projekt superfastcode](media/cpp-add-reference.png)

Alternativní metody popsané v následujících krocích, nainstaluje modul v globálním prostředí Pythonu ji dáte k dispozici i jiné projekty Pythonu. (To obvykle vyžaduje aktualizaci databáze pro dokončování IntelliSense pro toto prostředí v sadě Visual Studio 2017 verze 15.5 a starší. Aktualizace je také nutné při odebírání modulu z prostředí.)

1. Pokud používáte Visual Studio 2017, spusťte instalační program sady Visual Studio, vyberte **změnit**vyberte **jednotlivé komponenty > sestavení kompilátory, nástroje a moduly runtime > Sada nástrojů Visual C++ 2015.3 v140**. Tento krok je nezbytný, protože Pythonu (pro Windows) sama o sobě sestavené pomocí sady Visual Studio 2015 (verze 14.0) a očekává, že tyto nástroje jsou k dispozici, při vytváření rozšíření pomocí metody popsané. (Všimněte si, že budete muset nainstalovat 32bitovou verzi jazyka Python a zaměřit knihovna DLL Win32 a ne x64.)

1. Vytvořte soubor s názvem `setup.py` v projektu jazyka C++ tak, že kliknete pravým tlačítkem projekt a vyberete **Přidat > Nová položka...** . Vyberte "Soubor C++ (.cpp)", zadejte název souboru `setup.py`a výběrem **OK** (pojmenování souboru s `.py` rozšíření umožňuje rozpoznat Python bez ohledu na C++ pomocí souboru šablony sady Visual Studio). Když soubor se zobrazí v editoru, vložte následující kód do ní:

    ```python
    from distutils.core import setup, Extension, DEBUG

    sfc_module = Extension('superfastcode', sources = ['module.cpp'])

    setup(name = 'superfastcode', version = '1.0',
        description = 'Python Package with superfastcode C++ extension',
        ext_modules = [sfc_module]
        )
    ```

    Zobrazit [rozšíření sestavení jazyka C a C++](https://docs.python.org/3/extending/building.html) (python.org) dokumentaci o tomto skriptu.

1. `setup.py` Kódu nastaví Python k vytváření rozšíření pomocí nástrojů Visual Studio 2015 C++ při použití z příkazového řádku. Otevřete příkazový řádek se zvýšenými oprávněními, přejděte do složky obsahující projekt C++ (to znamená, že tato složka obsahuje `setup.py`) a zadejte následující příkaz:

    ```command
    pip install .
    ```

### <a name="call-the-dll-from-python"></a>Volání knihovny DLL z Pythonu

Po zadání některé z metod uvedených výše, teď můžete volat `fast_tanh` funkce z kódu v Pythonu a porovnávají jeho implementace Pythonu:

1. Přidejte následující řádky do vaší `.py` souboru k volání `fast_tanh` metoda exportovaná z knihovny DLL a zobrazí jeho výstup.

    ```python
    from superfastcode import fast_tanh
    test(lambda d: [fast_tanh(x) for x in d], '[fast_tanh(x) for x in d]')
    ```

1. Spusťte program Pythonu (**ladit > Spustit bez ladění** nebo Ctrl + F5) a podívejte se, rutina C++ běží rychleji než implementace Python pěti až 20 násobek. Příklad typického výstupu se zobrazí takto:

    ```output
    Running benchmarks with COUNT = 500000
    sequence_tanh took 1.542 seconds

    [tanh(x) for x in d] took 1.087 seconds

    [fast_tanh(x) for x in d] took 0.158 seconds
    ```

    Pokud **spustit bez ladění** příkaz je zakázán, klikněte pravým tlačítkem na projekt Python v Průzkumníku řešení a vyberte **nastavit jako spouštěný projekt**.

1. Zkuste zvýšit `COUNT` proměnné tak, aby rozdíly jsou zřetelnější. Sestavení pro ladění modulu C++ také probíhá pomaleji, než sestavení pro vydání protože je méně optimalizovaná sestavení pro ladění a obsahuje Kontrola různých chyb. Můžete přepínat mezi těmito konfiguracemi porovnání.

## <a name="debug-the-c-code"></a>Ladění kódu C++

Visual Studio podporuje ladění kódu Python a C++ společně.

1. Klikněte pravým tlačítkem na projekt Python v Průzkumníku řešení, vyberte **vlastnosti**, vyberte **ladění** kartu a potom vyberte **ladit > Povolit ladění nativního kódu** možnost.

    > [!Tip]
    > Po povolení ladění nativního kódu v okně výstupu Python může zmizet hned po dokončení programu bez ztráty obvykle pozastavení "Stisknutím libovolné klávesy pokračovat...". K vynucení pozastavení, přidejte `-i` umožňuje **spuštění > argumenty pro interpret** pole na **ladění** kartě povolit ladění nativního kódu. Tento argument interpret Pythonu umístí do interaktivního režimu po dokončení kódu, kdy čeká na stisknutí klávesy Ctrl + Z, Enter ukončete. (Případně, pokud vám nevadí, úpravy kódu Python, můžete přidat `import os` a `os.system("pause")` příkazy na konci programu. Tento kód duplicity původní řádek pozastavit).

1. Vyberte **soubor > Uložit** uložit změny vlastností.

1. Nastavte konfiguraci sestavení na "Ladění" v panelu nástrojů sady Visual Studio.

    ![Nastavení konfigurace sestavení pro ladění](media/cpp-set-debug.png)

1. Protože kód obecně trvá delší dobu v ladicím programu, můžete chtít změnit `COUNT` proměnné v vaše `.py` souboru na hodnotu, která je menší, asi pětkrát (například změnit z `500000` k `100000`).

1. V kódu jazyka C++, nastavit zarážku na prvním řádku `tanh_impl` metodu a poté spuštění ladicího programu (F5 nebo **ladit > Spustit ladění**). Ladicí program se zastaví, když je volána, že kód. Pokud není zarážka dosažena, zkontrolujte, že je nastavení konfigurace pro ladění a že jste uložili projektu (který neprobíhá automaticky při spuštění ladicího programu).

    ![Zastavení na zarážce v kódu jazyka C++](media/cpp-debugging.png)

1. V tomto okamžiku můžete krokovat kód jazyka C++, zkontrolujte proměnné a tak dále. Tyto funkce jsou podrobně popsány v [ladění jazyka C++ a Python společně](debugging-mixed-mode-c-cpp-python-in-visual-studio.md).

## <a name="alternative-approaches"></a>Alternativní přístupy

Existuje široká škála způsob, jak vytvořit rozšíření Pythonu, jak je popsáno v následující tabulce. První položka pro CPython je, co je popsaná v tomto článku už.

| Přístup | Ročníku | Zástupce počet uživatelů: | Pro(s) | CON(s) |
| --- | --- | --- | --- | --- |
| Moduly rozšíření jazyka C/C++ pro CPython | 1991 | Standardní knihovna | [Rozsáhlé dokumentace a kurzy](https://docs.python.org/3/c-api/). Úplnou kontrolu. | Kompilace, přenositelnost, odkazovat na správu. Vysoká znalostní báze C. |
| [pybind11](https://github.com/pybind/pybind11) (doporučeno pro jazyk C++) | 2015 |  | Odlehčený, pouze záhlaví knihovny pro vytváření vazeb Pythonu z existujícího kódu C++. Několik závislostí. PyPy kompatibility. | Novější, méně až po zralé. Silná použití jazyka C ++ 11. Krátký seznam podporovaných kompilátory (je součástí sady Visual Studio). |
| Cython (Recommnded pro jazyk C) | 2007 | [gevent](http://www.gevent.org/), [kivy](https://kivy.org/) | Jako v Pythonu. Vysoce vyspělé. Vysoký výkon. | Kompilace, novou syntaxi, nové sady nástrojů. |
| [Boost.Python](https://www.boost.org/doc/libs/1_66_0/libs/python/doc/html/index.html) | 2002 | | Funguje s téměř každou kompilátorem jazyka C++. | Rozsáhlý a komplexní sadu knihoven; obsahuje mnoho řešení pro staré kompilátory. |
| ctypes | 2003 | [oscrypto](https://github.com/wbond/oscrypto) | Žádné kompilace širokou dostupnost. | Přístup k a mutace struktury C náročné a náchylné k chybám. |
| SWIG | 1996 | [crfsuite](http://www.chokkan.org/software/crfsuite/) | Generovat vazby pro řadu jazyků najednou. | Pokud Python je jediný cíl nadměrnému zatížení. |
| cffi | 2013 | [kryptografie](https://cryptography.io/en/latest/), [pypy](http://pypy.org/) | Snadné integraci, PyPy kompatibility. | Novější, méně až po zralé. |

## <a name="see-also"></a>Viz také:

Je hotová ukázka z tohoto návodu můžete najít na [python ukázky vs-cpp-extension](https://github.com/Microsoft/python-sample-vs-cpp-extension) (GitHub).