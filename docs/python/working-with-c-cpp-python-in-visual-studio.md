---
title: Práce s C++ a Python
description: Návod, vytváření rozšíření pro C++ pro jazyk Python pomocí sady Visual Studio, včetně ladění ve smíšeném režimu.
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
ms.openlocfilehash: c339b531e120c6e257dc4b5ee84c8a41b64ec6bd
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118301"
---
# <a name="creating-a-c-extension-for-python"></a>Vytvoření rozšíření C++ pro Python

Moduly, které jsou napsané v C++ (nebo C) se běžně používají k rozšíření možností překladač Pythonu tak, aby přístup k funkcím nízké úrovně operačního systému. Existují tři primární typy modulů:

- Moduly akcelerátoru: Python je interpretovaný jazyk, a proto může být zapsán určité části kódu v jazyce C++ pro vyšší výkon.
- Obálka moduly: vystavit existující rozhraní C/C++ pro kód Python nebo odhalí další rozhraní API "Pythonic", které se snadno používá z Pythonu.
- Nízké úrovně systému přístup moduly: vytvořili pro přístup k funkcím nižší úrovně CPython runtime, operační systém nebo základní hardware.

Tento článek vás provede sestavování rozšíření modulu C++ pro CPython, která vypočítá hyperbolický tangens a volá z kódu jazyka Python. Rutiny se implementuje nejprve v Pythonu k předvedení relativní výkonnější implementace stejné rutiny v jazyce C++.

Přístup prováděné v tomto poli je, že pro standardní CPython rozšíření, jak je popsáno v [Python dokumentaci](https://docs.python.org/3/c-api/). Porovnání mezi touto a jinými prostředky je popsaný v části [Alternativní přístupy](#alternative-approaches) na konci tohoto článku.

Je hotová ukázka z tohoto návodu můžete najít na [python ukázky vs-cpp přípona](https://github.com/Microsoft/python-sample-vs-cpp-extension) (Githubu).

## <a name="prerequisites"></a>Požadavky

- Visual Studio 2017 s oběma **vývoj plochy s jazykem C++** a **vývoj Python** úlohy, které jsou nainstalované s výchozími možnostmi.
- V **vývoj Python** zatížení, také políčko na pravé straně pro **Python tools nativní vývoj**. Tato možnost nastavuje většinu konfigurace popsané v tomto článku. (Tato možnost také zahrnuje úlohy C++ automaticky.)

    ![Vybráním možnosti nástroje jazyka Python nativní vývoj](media/cpp-install-native.png)

    > [!Tip]
    > Instalace **vědecké zpracování dat a analytických aplikací** zatížení také zahrnuje Python a **Python tools nativní vývoj** možnost ve výchozím nastavení.

Další informace najdete v tématu [instalaci podpory jazyka Python pro Visual Studio](installing-python-support-in-visual-studio.md), včetně použití jiné verze sady Visual Studio. Pokud instalujete Python samostatně, je nutné vybrat **stáhnout symboly ladění** a **ladicí binární soubory ke stažení** pod **pokročilé možnosti** v instalačním programu. Tato možnost zajistí, abyste měli k dispozici nezbytné ladění knihoven, pokud se rozhodnete sestavení ladicí verze.

## <a name="create-the-python-application"></a>Vytvoření aplikace Python

1. Vytvořte nový projekt Python v sadě Visual Studio výběrem **soubor > Nový > projekt**. Vyhledejte "Python", vyberte **aplikace Python** šablony, poskytněte vhodný název a umístění a vyberte **OK**.

1. Práce s C++ vyžaduje použití překladač Pythonu 32-bit (Python 3.6 doporučené). V **Průzkumníku řešení** okno sady Visual Studio, rozbalte uzel projektu a potom rozbalte položku **prostředí Python** uzlu. Pokud nevidíte 32-bit prostředí jako výchozí (buď v tučné a s popiskem "globální výchozí"), postupujte podle pokynů [výběr prostředí Python pro projekt](selecting-a-python-environment-for-a-project.md). Pokud nemáte k dispozici 32bitová verze překladač, nainstalovat, přečtěte si téma [instalaci Python překladače](installing-python-interpreters.md).

1. V projektu `.py` souboru, vložte následující kód, který benchmarks výpočet hyperbolický tangens (implementována bez použití knihovny math pro snazší porovnání). Můžete zadat kód ručně, aby některé z prostředí [Python úpravy funkce](editing-python-code-in-visual-studio.md).

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

1. Spustit pomocí programu **ladění > Spustit bez ladění** (Ctrl + F5) a zobrazte si výsledky. Můžete upravit `COUNT` proměnné změnit, jak dlouho trvat srovnávací testy ke spuštění. Pro účely tohoto návodu nastavte počet tak, aby každý srovnávací test trvá přibližně dvou sekund.

## <a name="create-the-core-c-project"></a>Vytvoření projektu C++ jádra

1. V Průzkumníku řešení klikněte pravým tlačítkem a vyberte **Přidat > Nový projekt...** . Řešení sady Visual Studio může obsahovat Python a C++ projekty společně (které je jednou z výhod pomocí sady Visual Studio pro jazyk Python).

1. Vyhledávání v "C++", vyberte **prázdný projekt**, zadejte název (Tento článek používá "superfastcode") a vyberte **OK**.

    > [!Tip]
    > S **nativní vývoj nástrojů Python** ve Visual Studio 2017 instalace, můžete začít s **modul Python rozšíření** šablony místo toho, který má většinu co je popsáno níže již v místě. V tomto návodu ale spuštění s prázdným projektem ukazuje vytvoření rozšíření modulu krok za krokem. Jakmile porozumíte proces, uloží šablony času při psaní vlastních rozšíření.

1. Vytvořte soubor C++ v novém projektu kliknutím pravým tlačítkem myši **zdrojové soubory** uzlu, pak vyberte **Přidat > novou položku... "**, vyberte **soubor C++**, pojmenujte ji `module.cpp`, a Vyberte **OK**.

    > [!Important]
    > Soubor s `.cpp` rozšíření je nutné zapnout na stránkách vlastností C++ v krocích, které následují.

1. Klikněte pravým tlačítkem na projekt C++ v řešení, vyberte **vlastnosti**.

1. V horní části **stránky vlastností** nastavte dialogové okno, který se zobrazí **konfigurace** k **všechny konfigurace** a **platformy** k **Win32**.

1. Nastavte konkrétní vlastnosti, jak je popsáno v následující tabulce a pak vyberte **OK**.

    | Tabulátor | Vlastnost | Hodnota |
    | --- | --- | --- |
    | Obecné | Obecné > název cíle | Zadejte název modulu, jak chcete na ni odkazuje z Pythonu v `from...import` příkazy. Při definování modulu pro jazyk Python použijete tento stejný název v jazyce C++. Pokud chcete použít název projektu s názvem modulu, ponechte výchozí hodnotu `$(ProjectName)`. |
    | | Obecné > cíle rozšíření | .pyd |
    | | Výchozí nastavení projektu > typ konfigurace | Dynamická knihovna (DLL) |
    | C/C++-> Obecné | Další zahrnuté adresáře | Přidat Python `include` složky podle potřeby pro instalaci, například `c:\Python36\include`.  |
    | C/C++ > preprocesor | Definice preprocesoru | Přidat `Py_LIMITED_API;` na začátku řetězce (včetně středník). Tuto definici omezuje některé funkce můžete volat z Python a umožňuje kód víc přenosného mezi různými verzemi jazyka Python. |
    | C/C++ > generování kódu | Běhové knihovny | Vícevláknové knihovny DLL (/ MD) (viz následující upozornění) |
    | Linkeru > Obecné | Další knihovny adresáře | Přidat Python `libs` složku obsahující `.lib` soubory potřebné pro instalaci, například `c:\Python36\libs`. (Ujistěte se, tak, aby odkazoval `libs` složku, která obsahuje `.lib` soubory, a *není* `Lib` složku, která obsahuje `.py` soubory.) |

    > [!Tip]
    > Pokud se nezobrazí na kartě C/C++ ve vlastnostech projektu, je to, protože projektu neobsahuje všechny soubory, které označuje jako C/C++ zdrojové soubory. K tomuto stavu může dojít, pokud vytvoření zdrojového souboru bez `.c` nebo `.cpp` rozšíření. Například, pokud jste omylem zadali `module.coo` místo `module.cpp` nové položky dříve v dialogovém okně, pak Visual Studio vytvoří soubor, ale typ souboru není nastavena na "C / C + kód," což je co aktivuje na kartě Vlastnosti C/C++. Takové misidentification zůstane tak i v případě, že přejmenujte soubor s `.cpp`. Typ souboru nastavit správně, klikněte pravým tlačítkem na soubor v Průzkumníku řešení, vyberte **vlastnosti**, nastavte **typ souboru** k **kódu C/C++**.

    > [!Warning]
    > Vždy nastaven **C/C++ > generování kódu > Runtime Library** možnost k "vícevláknové knihovny DLL (/ MD)", i pro konfiguraci ladění, protože toto nastavení je to, co jsou vytvořené binární soubory bez ladění Python s. Pokud jste se nastavit "vícevláknové ladění knihoven DLL (/ MDd)" možnost vytváření konfiguraci ladění způsobil chybu *C1189: Py_LIMITED_API není kompatibilní s Py_DEBUG, Py_TRACE_REFS a Py_REF_DEBUG*. Kromě toho pokud odeberete `Py_LIMITED_API` nechcete chyby sestavení, Python, dojde k chybě při pokusu o import modulu. (V rámci volání knihovny DLL se stane havárii `PyModule_Create` jak je popsáno dále, s výstup zprávu *Python závažná chyba: PyThreadState_Get: žádný aktuální vlákno*.)
    >
    > Možnost /MDd slouží k vytvoření ladicí binární soubory Python (například python_d.exe), ale stále výběr rozšiřující knihovny DLL způsobuje chybu sestavení s `Py_LIMITED_API`.

1. Klikněte pravým tlačítkem na projekt C++ a vyberte **sestavení** k testování vaše konfigurace (ladění a vydání). `.pyd` Soubory jsou umístěny v *řešení* ve složce **ladění** a **verze**, není C++ projektu samotné složce.

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

1. Sestavení projektu C++ znovu pro potvrzení, že jste kód napsali správně.

## <a name="convert-the-c-project-to-an-extension-for-python"></a>Převedení projektu C++ na rozšíření pro jazyk Python

Chcete-li C++ DLL do rozšíření pro jazyk Python, nejdřív změnit exportovaných metod pro interakci s typy Python. Potom je přidat funkce, který exportuje modulu, společně s definice metod modulu.

Pozadí na zobrazené v této části pro jazyk Python 3.x, naleznete [Python nebo C API referenční příručce](https://docs.python.org/3/c-api/index.html) a hlavně [objekty modulu](https://docs.python.org/3/c-api/module.html) na python.org (Nezapomeňte vyberte verzi jazyka Python z rozevírací seznam ovládací prvek v pravém horním k dokumentaci pro správné).

Pokud pracujete s Python 2.7, přečtěte si téma místo [rozšíření Python 2.7 pomocí jazyka C nebo C++](https://docs.python.org/2.7/extending/extending.html) a [portování rozšíření modulů pro Python 3](https://docs.python.org/2.7/howto/cporting.html) (python.org).

1. V souboru C++ zahrnují `Python.h` v horní části:

    ```cpp
    #include <Python.h>
    ```

1. Změnit `tanh_impl` metoda přijmout a návratové typy Python ( `PyOjbect*`, která je):

    ```cpp
    PyObject* tanh_impl(PyObject *, PyObject* o) {
        double x = PyFloat_AsDouble(o);
        double tanh_x = sinh_impl(x) / cosh_impl(x);
        return PyFloat_FromDouble(tanh_x);
    }
    ```

1. Přidat strukturu, která definuje jak C++ `tanh_impl` pro Python zobrazí funkce:

    ```cpp
    static PyMethodDef superfastcode_methods[] = {
        // The first property is the name exposed to Python, fast_tanh, the second is the C++
        // function name that contains the implementation.
        { "fast_tanh", (PyCFunction)tanh_impl, METH_O, nullptr },

        // Terminate the array with an object containing nulls.
        { nullptr, nullptr, 0, nullptr }
    };
    ```

1. Přidat strukturu, která definuje modul, jak chcete na ni odkazuje v kódu jazyka Python, konkrétně při použití `from...import` příkaz. (Tento odpovídají hodnotě ve vlastnostech projektu v části nastavit **vlastnosti konfigurace > Obecné > název cílové**.) V následujícím příkladu, název modulu "superfastcode" znamená, můžete použít `from superfastcode import fast_tanh` v Python, protože `fast_tanh` je definována v rámci `superfastcode_methods`. (Názvy souborů interní do projektu C++, jako je module.cpp, jsou irelevantní.)

    ```cpp
    static PyModuleDef superfastcode_module = {
        PyModuleDef_HEAD_INIT,
        "superfastcode",                        // Module name to use with Python import statements
        "Provides some functions, but faster",  // Module description
        0,
        superfastcode_methods                   // Structure that defines the methods of the module
    };
    ```

1. Přidejte metodu, která volá Python, pokud ho načte modul, který musí mít název `PyInit_<module-name>`, kde *&lt;module_name&gt;* přesně odpovídá projektu C++ **Obecné > název cílové** vlastnost (to znamená, odpovídá název souboru `.pyd` sestavený projektem).

    ```cpp
    PyMODINIT_FUNC PyInit_superfastcode() {
        return PyModule_Create(&superfastcode_module);
    }
    ```

1. Nastavení konfigurace cílového "Verze" a sestavení projektu C++ znovu k ověření vašeho kódu. Pokud narazíte na chyby, zkontrolujte v následujících případech:
    - Nepodařilo se najít Python.h (*E1696: Nelze otevřít zdrojový soubor "Python.h"* nebo *C1083: Nelze otevřít vložený soubor: "Python.h": podobný soubor nebo adresář*): Ověřte, že cestu ve **C/C++ > Obecné > Další adresáře Include** v bodech vlastnosti projektu do instalace Python `include` složky. Podívejte se na krok 6 v části [vytvoření projektu základní C++](#create-the-core-c-project).
    - Nepodařilo se najít Python knihovny: Ověřte, že cestu ve **Linkeru > Obecné > Další adresáře knihovny** v bodech vlastnosti projektu do instalace Python `libs` složky. Podívejte se na krok 6 v části [vytvoření projektu základní C++](#create-the-core-c-project).
    - Linkeru chyb souvisejících s architekturou cílového: změnit cíl C++ projektu architektura odpovídat instalace Python. Předpokládejme například pokud jste cílení x64 s projektem C++, ale vaše instalace Python je x86, změňte projektu C++ pro x86.

## <a name="test-the-code-and-compare-the-results"></a>Testování kódu a porovnejte výsledky

Teď, když máte knihovnu DLL strukturovaná jako rozšíření Python, můžete na ni odkazuje z projektu Python, naimportujte modul a použít její metody.

### <a name="make-the-dll-available-to-python"></a>Zpřístupnit knihovnu DLL jazyka Python

Existují dva způsoby, jak zpřístupnit knihovnu DLL jazyka Python.

První metoda funguje v případě, že Python projekt a projekt C++ jsou ve stejném řešení. Přejděte do Průzkumníka řešení klikněte pravým tlačítkem myši **odkazy** uzlu v projektu jazyka Python a potom vyberte **přidat odkaz na**. V dialogovém okně se zobrazí, vyberte **projekty** vyberte **superfastcode** projektu (nebo ať název je používáte) a potom **OK**.

![Přidat odkaz na projekt superfastcode](media/cpp-add-reference.png)

Alternativní metody popsané v následujících krocích se nainstaluje modul v globální prostředí Python zpřístupnění do jiných Python projektů. (Takže obvykle to vyžaduje, můžete obnovit databázi doplňování IntelliSense pro prostředí v aplikaci Visual Studio 2017 15,5 a starší verze. Aktualizace je také nezbytné při odebírání modulu z prostředí.)

1. Pokud používáte Visual Studio 2017, spusťte instalační program sady Visual Studio, vyberte **upravit**, vyberte **jednotlivých součástí > kompilátory, sestavení nástroje a moduly runtime > Sada nástrojů Visual C++ 2015.3 v140**. Tento krok je nezbytný, protože Python (pro Windows) je sám vytvořené s nástroji Visual Studio 2015 (verze 14.0) a očekává, že tyto nástroje jsou k dispozici při sestavování rozšíření pomocí metody popsané v tomto poli. (Všimněte si, že budete muset nainstalovat 32bitovou verzi jazyka Python a cíle DLL Win32 a není x64.)

1. Vytvořte soubor s názvem `setup.py` v projektu jazyka C++ kliknutím pravým tlačítkem na projekt a výběrem **Přidat > novou položku...** . Potom vyberte "Soubor C++ ()", zadejte název souboru `setup.py`a výběr **OK** (pojmenovávání souborů a `.py` rozšíření umožňuje rozpoznat ho jako Python bez ohledu C++ pomocí souborů šablony sady Visual Studio). Když soubor se zobrazí v editoru, vložte do ní následující kód:

    ```python
    from distutils.core import setup, Extension, DEBUG

    sfc_module = Extension('superfastcode', sources = ['module.cpp'])

    setup(name = 'superfastcode', version = '1.0',
        description = 'Python Package with superfastcode C++ extension',
        ext_modules = [sfc_module]
        )
    ```

    V tématu [rozšíření sestavení C a C++](https://docs.python.org/3/extending/building.html) (python.org) pro dokumentaci na tento skript.

1. `setup.py` Kód dá pokyn Python k sestavení rozšíření pomocí nástrojů Visual Studio 2015 C++ při použití z příkazového řádku. Otevřete příkazový řádek se zvýšenými oprávněními, přejděte do složky obsahující projekt C++ (to znamená, složky, která obsahuje `setup.py`) a zadejte následující příkaz:

    ```command
    pip install .
    ```

### <a name="call-the-dll-from-python"></a>Volání knihovny DLL z Pythonu

Po dokončení některou z výše uvedených metod, teď můžete volat `fast_tanh` funkce z kód Python a porovnání jeho výkon a Python implementace:

1. Přidejte následující řádky do vaší `.py` souboru k volání `fast_tanh` Metoda Export z knihovny DLL a zobrazí jeho výstup.

    ```python
    from superfastcode import fast_tanh
    test(lambda d: [fast_tanh(x) for x in d], '[fast_tanh(x) for x in d]')
    ```

1. Spusťte Python program (**ladění > Spustit bez ladění** nebo Ctrl + F5) a sledovat rutiny C++ rychleji než implementace Python spouští pět až 20 vyšší. Zobrazí se následující typické výstup:

    ```output
    Running benchmarks with COUNT = 500000
    sequence_tanh took 1.542 seconds

    [tanh(x) for x in d] took 1.087 seconds

    [fast_tanh(x) for x in d] took 0.158 seconds
    ```

1. Pokuste se zvýšit `COUNT` proměnné tak, aby rozdíly jsou mnohem výraznější. Sestavení ladicí verze modulu C++ také pracovat pomaleji než sestavení pro vydání protože ladění sestavení méně je optimalizovaná a obsahuje různé chyby kontroly. Nebojte se, že přepínat mezi tyto konfigurace pro porovnání.

## <a name="debug-the-c-code"></a>Ladění kódu C++

Visual Studio podporuje ladění kódu jazyka Python a C++ společně.

1. Klikněte pravým tlačítkem na projekt Python v Průzkumníku řešení, vyberte **vlastnosti**, vyberte **ladění** a pak vyberte **ladění > Povolit ladění nativního kódu** možnost.

    > [!Tip]
    > Když povolíte ladění nativního kódu, ve výstupním okně Python může zmizet okamžitě, když program dokončí bez budete obvykle pozastavení "Stisknutím libovolné klávesy... Pokračujte". K vynucení pozastavení, přidejte `-i` možnost k **spustit > překladač argumenty** na **ladění** kartě při povolení ladění nativního kódu. Tento argument překladač Pythonu umístí do interaktivním režimu po dokončení kód v tomto okamžiku se čeká na stiskněte klávesy Ctrl + Z, zadejte ukončíte. (Případně, pokud vám nevadí, úprava kódu jazyka Python, můžete přidat `import os` a `os.system("pause")` příkazy na konci vašeho programu. Tento kód duplicity řádku původní pozastavení).

1. Vyberte **soubor > Uložit** uložit změny vlastností.

1. Nastavte konfiguraci sestavení na "Debug" na panelu nástrojů Visual Studio.

    ![Nastavení konfigurace sestavení pro ladění](media/cpp-set-debug.png)

1. Protože kód obvykle trvá déle ke spuštění v ladicím programu, můžete změnit `COUNT` proměnné v vaší `.py` souboru na hodnotu, která se chystáte pětkrát menší (například změnit z `500000` k `100000`).

1. Ve vašem kódu C++ nastavit zarážky první řádek `tanh_impl` metoda pak spuštění ladicího programu (F5 nebo **ladění > Spustit ladění**). Ladicí program zastaví, když je volána tento kód. Pokud není průchodu zarážkou, zkontrolujte, že konfigurace je nastavená na ladění a že jste uložili projektu (který neprobíhá automaticky při spuštění ladicího programu).

    ![Zastavení u zarážky v kódu C++](media/cpp-debugging.png)

1. V tomto okamžiku můžete krok prostřednictvím kódu C++, zkontrolujte proměnné a tak dále. Tyto funkce jsou podrobně popsané na [ladění C++ a Python společně](debugging-mixed-mode-c-cpp-python-in-visual-studio.md).

## <a name="alternative-approaches"></a>Alternativní přístupy

Existuje mnoho různých prostředků k vytvoření rozšíření Python, jak je popsáno v následující tabulce. První položka pro CPython je, co bylo popsané v tomto článku již.

| Přístup | Ročníku | Zástupce jiní uživatelé | Pro(s) | CON(s) |
| --- | --- | --- | --- | --- |
| C/C++ rozšíření modulů pro CPython | 1991 | Standardní knihovna | [Kurzy a rozsáhlou dokumentaci](https://docs.python.org/3/c-api/). Celkový počet ovládacího prvku. | Kompilace, přenositelnost, odkaz na správu. Vysoká C znalostní báze. |
| [pybind11](https://github.com/pybind/pybind11) (doporučeno pro jazyk C++) | 2015 |  | Knihovna Lightweight, pouze záhlaví pro vytvoření vazby Python z existujícího kódu C++. Několik závislostí. PyPy kompatibility. | Novější, méně vyspělá. Silná pomocí funkcí C ++ 11. Krátké seznam podporovaných kompilátory (je součástí sady Visual Studio). |
| Cython (Recommnded pro C) | 2007 | [gevent](http://www.gevent.org/), [kivy](https://kivy.org/) | Jako Python. Vysoce vyspělá. Vysoký výkon. | Kompilace, nových nástrojů a nové syntaxe. |
| [Boost.Python](https://www.boost.org/doc/libs/1_66_0/libs/python/doc/html/index.html) | 2002 | | Funguje s téměř každé kompilátoru C++. | Velké a komplexní sada knihoven; obsahuje mnoho zástupná staré kompilátory. |
| ctypes | 2003 | [oscrypto](https://github.com/wbond/oscrypto) | Žádné kompilace široké dostupnosti. | Přístup k informacím a mutace C struktury náročná a chyba náchylné k chybám. |
| SWIG | 1996 | [crfsuite](http://www.chokkan.org/software/crfsuite/) | Generovat vazby u mnoha jazycích najednou. | Nadměrnému zatížení, pokud Python je jediný cíl. |
| cffi | 2013 | [kryptografie](https://cryptography.io/en/latest/), [pypy](http://pypy.org/) | Snadná integrace, PyPy kompatibility. | Novější, méně vyspělá. |

## <a name="see-also"></a>Viz také:

Je hotová ukázka z tohoto návodu můžete najít na [python ukázky vs-cpp přípona](https://github.com/Microsoft/python-sample-vs-cpp-extension) (Githubu).