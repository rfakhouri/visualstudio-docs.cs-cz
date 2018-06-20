---
title: Ve smíšeném režimu ladění pro jazyk Python
description: Postup ladění současně C++ a Python v sadě Visual Studio, včetně krokování mezi prostředími, zobrazení hodnoty a vyhodnocení výrazů.
ms.date: 01/16/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 6c6556ab99f7c72407da9915d73e7a19e6dd45da
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234582"
---
# <a name="debugging-python-and-c-together"></a>Společně ladění Python a C++

Většina regulární ladicí programy Python podporovat ladění pouze Python kódu. V praxi však Python se používá ve spojení s C nebo C++ v scénářům, které vyžadují vysoký výkon nebo možnost přímo volat rozhraní API platformy. (Viz [vytváření rozšíření pro C++ pro jazyk Python](working-with-c-cpp-python-in-visual-studio.md) podrobný.)

Visual Studio poskytuje integrované, souběžných ladění ve smíšeném režimu pro Python a nativní C/C++, za předpokladu, že jste vybrali **Python tools nativní vývoj** možnost pro vývoj Python zatížení v sadě Visual Studio Instalační program.

> [!Note]
> Ladění ve smíšeném režimu není k dispozici s nástroji Python Tools pro sadu Visual Studio 1.x v sadě Visual Studio 2015 a starší.

Funkce ladění ve smíšeném režimu patří, jak je popsáno v tomto článku:

- Zásobníky volání kombinované
- Krok mezi Python a nativní kód
- Zarážky v obou typech kódu
- V tématu Python reprezentace objektů v nativní rámce a naopak
- Ladění v kontextu projektu Python nebo projektů C++

![Ladění ve smíšeném režimu](media/mixed-mode-debugging.png)

|   |   |
|---|---|
| ![Ikona filmové kamery pro video](../install/media/video-icon.png "Sledovat video") | Úvod do vytváření, testování a ladění nativních modulů C sadou Visual Studio, najdete v části [podrobné informace: vytváření nativní moduly](https://youtu.be/D9RlT06a1EI) (webu youtube.com, 9 m 09s). Přehrávání videa se vztahuje na Visual Studio 2015 a 2017. |

## <a name="enable-mixed-mode-debugging-in-a-python-project"></a>Povolit ladění ve smíšeném režimu v projektu jazyka Python

1. Klikněte pravým tlačítkem na projekt Python v Průzkumníku řešení, vyberte **vlastnosti**, vyberte **ladění** a pak vyberte **povolit ladění nativního kódu**. Tato možnost umožňuje ve smíšeném režimu pro všechny ladicí relace.

    ![Povolení ladění nativního kódu](media/mixed-mode-debugging-enable-native.png)

    > [!Tip]
    > Když povolíte ladění nativního kódu, ve výstupním okně Python může zmizet okamžitě, když program dokončí bez budete obvykle pozastavení "Stisknutím libovolné klávesy... Pokračujte". K vynucení pozastavení, přidejte `-i` možnost k **spustit > překladač argumenty** na **ladění** kartě při povolení ladění nativního kódu. Tento argument překladač Pythonu umístí do interaktivním režimu po dokončení kód v tomto okamžiku se čeká na stiskněte klávesy Ctrl + Z, zadejte ukončíte.

1. Při připojování k existující proces ladicího programu ve smíšeném režimu (**ladění > připojit k procesu...** ), použijte **vyberte...**  tlačítko Otevřít **vybrat typ kódu** dialogové okno. Nastavte **ladění tyto typy kódu** možnost a vyberte oba **nativní** a **Python** v seznamu:

    ![Vyberte typy kódu nativní a Python](media/mixed-mode-debugging-code-type.png)

    Nastavení typu kódu jsou trvalé, takže pokud chcete zakázat ladění ve smíšeném režimu při připojování k jiným procesem později, zrušte typ kód Python.

    Je možné vybrat jiné typy kódu kromě nebo místo **nativní**. Například pokud spravované aplikace hostuje CPython, které v zapnout používá rozšíření nativní moduly, a chcete ladit všechny tři, můžete zkontrolovat **Python**, **nativní**, a **spravované**společně v jednotném ladění rozhraní včetně zásobníky volání kombinované a zanoříte se mezi všechny tři moduly runtime.

1. Když začnete ladění ve smíšeném režimu poprvé, může se zobrazit **Python symboly požadované** dialogové okno (najdete v části [symboly pro ladění ve smíšeném režimu](debugging-symbols-for-mixed-mode-c-cpp-python.md)). Musíte nainstalovat jenom jednou symboly pro jakékoli dané prostředí Python. Symboly jsou automaticky zahrnuty, pokud instalujete podporu Python prostřednictvím Visual Studio 2017 Instalační služby.

1. Zkontrolujte zdrojový kód pro standardní Python, sám o sobě dostupný při ladění, navštivte [ https://www.python.org/downloads/source/ ](https://www.python.org/downloads/source/), stáhněte archivu vhodné pro vaši verzi a rozbalte ho do složky. Budete pak bodu aplikace Visual Studio pro konkrétní soubory v této složce v ať bod výzvu.

## <a name="enable-mixed-mode-debugging-in-a-cc-project"></a>Povolit ladění ve smíšeném režimu v projektu C/C++

Visual Studio 2017 (verze 15,5 a vyšší) podporuje ve smíšeném režimu ladění z projektu C/C++ (například když [vložení Python v jiné aplikaci, jak je popsáno na python.org](https://docs.python.org/3/extending/embedding.html)). Pokud chcete povolit ladění ve smíšeném režimu, konfigurace projektu C/C++ pro spuštění "Ladicího programu Python/Native":

1. Klikněte pravým tlačítkem na projekt C/C++ v Průzkumníku řešení a vyberte **vlastnosti**
1. Vyberte **ladění** vyberte "Python/nativní ladicí program" z **ladicí program ke spuštění**a vyberte **OK**.

    ![Výběr Python/nativní ladicí program v projektu C/C++](media/mixed-mode-debugging-select-cpp-debugger.png)

Pomocí této metody, mějte na paměti, že nelze ladění `py.exe` Spouštěč samostatně, protože ji vytvoří podřízenou `python.exe` proces, který nebude připojen ladicí program k. Pokud chcete spustit `python.exe` přímo s argumenty, změnit **příkaz** možnost ve vlastnostech Python/nativní ladění (viz předchozí obrázek) zadat úplnou cestu k `python.exe`, pak zadejte argumenty v **Příkaz argumenty**.

### <a name="attaching-the-mixed-mode-debugger"></a>Připojení ladicího programu ve smíšeném režimu

Pro všechny předchozí verze sady Visual Studio přímé ladění ve smíšeném režimu je povolené jenom v případě, že spuštění Python projektu v sadě Visual Studio, protože projekty C/C++ použít jenom nativní ladicí program. Můžete však připojit ladicí program samostatně:

1. Spusťte projekt C++ bez ladění (**ladění > Spustit bez ladění** nebo Ctrl + F5).
1. Vyberte **ladění > připojit k procesu...** . V dialogovém okně se zobrazí, vyberte odpovídající proces, pak používat **vyberte...**  tlačítko Otevřít **vybrat typ kódu** dialogové okno, ve kterém můžete vybrat Python:

    ![Výběr Python jako typ ladění při připojení ladicí program](media/mixed-mode-debugging-attach-type.png)

1. Vyberte **OK** tento dialog zavřít pak **Attach** spuštění ladicího programu.
1. Budete muset zavést vhodný pozastavení nebo zpoždění v aplikaci C++ a ujistěte se, že ji nebude volat kód Python, kterou chcete ladit před máte možnost připojit ladicí program.

## <a name="mixed-mode-specific-features"></a>Konkrétní funkce ve smíšeném režimu

- [Zásobník volání kombinované](#combined-call-stack)
- [Krokování s mezi Python a nativní kód](#stepping-between-python-and-native-code)
- [Zobrazení PyObject hodnoty v nativním kódu](#pyobject-values-view-in-native-code)
- [Zobrazení nativní hodnoty v kódu jazyka Python](#native-values-view-in-python-code)

### <a name="combined-call-stack"></a>Zásobník volání kombinované

Okno zásobník volání ukazuje nativní a rámce zásobníku Python prokládaný s přechody označena mezi těmito dvěma:

![Zásobník volání kombinované](media/mixed-mode-debugging-call-stack.png)

Přechody zobrazí jako "[externí kód]", bez zadání směr přechodu, pokud **nástroje > Možnosti > ladění > Obecné > povolit volbu pouze vlastní kód** je možnost nastavena.

Dvakrát klikněte na libovolný snímek volání stane aktivní a otevře příslušné zdrojový kód, pokud je to možné. Pokud zdrojový kód není k dispozici, rámečku přišla stále aktivní a může být prověřovány lokální proměnné.

### <a name="stepping-between-python-and-native-code"></a>Krokování s mezi Python a nativní kód

Pokud používáte Krokovat s vnořením (F11) nebo příkazy Krokovat s Vystoupením (Shift + F11), ve smíšeném režimu ladicí program zpracovává správně změny mezi typy kódu. Například když Python volá metodu typu, která je implementována v jazyce C, krokování na volání, metoda zastaví na začátku nativní funkce implementace metody. Podobně když nativní kód volá některé funkce rozhraní API Python, jejímž výsledkem volaná kód Python. Například zanoříte se do `PyObject_CallObject` na hodnotu funkce, která byla původně definována v Pythonu zastaví na začátku funkce Python. Krokování z Pythonu pro nativní je také podporována pro nativní funkce volána z Pythonu prostřednictvím [ctypes](http://docs.python.org/3/library/ctypes.html).

### <a name="pyobject-values-view-in-native-code"></a>Zobrazení PyObject hodnoty v nativním kódu

Při aktivním nativní rámce (C nebo C++) jeho místní proměnné zobrazí místní okno ladicí program. V nativních modulů Python rozšíření, mnoho z těchto proměnných jsou typu `PyObject` (což je typedef pro `_object`), nebo několik dalších základních typů Python (viz seznam níže). Při ladění ve smíšeném režimu, k dispozici tyto hodnoty do další podřízené uzlu s označením "Python zobrazení." Po rozbalení tento uzel zobrazuje reprezentace Python proměnné, identické by zobrazené Pokud místní proměnné odkazující na stejný objekt nacházel v rámci Python. Podřízené objekty tohoto uzlu se upravovat.

![Zobrazení Python](media/mixed-mode-debugging-python-view.png)

Tuto funkci zakázat, klikněte pravým tlačítkem na libovolné místo v místní hodnoty – okno a přepnutí **Python > zobrazit uzly zobrazení Python** nabídky:

![Povolení zobrazení Python](media/mixed-mode-debugging-enable-python-view.png)

C typy uzlů tohoto zobrazení "[Python zobrazení]" (Pokud je povoleno):

- `PyObject`
- `PyVarObject`
- `PyTypeObject`
- `PyByteArrayObject`
- `PyBytesObject`
- `PyTupleObject`
- `PyListObject`
- `PyDictObject`
- `PySetObject`
- `PyIntObject`
- `PyLongObject`
- `PyFloatObject`
- `PyStringObject`
- `PyUnicodeObject`

"[Python zobrazení]" pro typy, které vytváříte sami nezobrazí automaticky. Při vytváření rozšíření pro jazyk Python 3.x, tento nedostatek obvykle není problém protože libovolného objektu nakonec má `ob_base` pole jednoho z typů výše, což způsobí, že "[Python zobrazení]" se objeví.

Pro jazyk Python 2.x, ale jeho záhlaví pro každý typ objektu obvykle deklaruje jako kolekce vloženého pole a neexistuje žádné přidružení mezi typy vlastní vytvořené a `PyObject` na úrovni systému typu v kódu C/C++. Povolit "[Python zobrazení]" uzly pro vlastní typy, upravte `PythonDkm.natvis` v [nástroje Python tools instalační adresář](installing-python-support-in-visual-studio.md#install-locations)a přidejte jiný element v souboru XML pro struktura C nebo C++ třídy.

Možnost alternativního (a lepší), je splnění [období 3123](http://www.python.org/dev/peps/pep-3123/) a použití explicitního `PyObject ob_base;` pole místo `PyObject_HEAD`, ačkoli, nemusí být vždy možné z důvodů zpětné kompatibility.

### <a name="native-values-view-in-python-code"></a>Zobrazení nativní hodnoty v kódu jazyka Python

Podobně jako v předchozí části, můžete povolit "[C++]"pro zobrazení nativní hodnoty v místní hodnoty – okno když je aktivní snímek Python. Tato funkce není povolena ve výchozím nastavení, takže můžete zapnout tak, že kliknete pravým tlačítkem do místní hodnoty – okno a přepnutím **Python > zobrazit uzly zobrazení C++** možnost nabídky.

![Povolení zobrazení C++](media/mixed-mode-debugging-enable-cpp-view.png)

"[C++ zobrazení]" uzlu poskytuje reprezentace podkladová struktura C/C++ pro hodnotu identické by zobrazit nativní rámce. Například se zobrazí instance `_longobject` (pro které `PyLongObject` je definice typu) pro Python dlouhé celé číslo ale pokusí odvození typů pro nativní třídy, kterou jste vytvořili sami. Podřízené objekty tohoto uzlu se upravovat.

![Zobrazení C++](media/mixed-mode-debugging-cpp-view.png)

Pokud je pole podřízený objekt typu `PyObject`, nebo jednu z dalších podporované typy, pak má "[Python zobrazení]" reprezentace uzlu (pokud jsou povolené tyto reprezentace), což umožňuje přejděte objekt grafů, kde nejsou odkazy zveřejněné přímo do Python.

Na rozdíl od "[Python zobrazení]" uzly, které používají k určení typu objektu metadat objektu Python, neexistuje žádný podobně spolehlivé mechanismus pro "[C++ zobrazení]". Obecně řečeno se zadanou hodnotou Python (to znamená, `PyObject` odkaz) není možné spolehlivě určit, které C/C++ struktura je jejich zálohování. Ladicí program ve smíšeném režimu se pokusí odhadnout typu pohledem na různá pole typu objektu (například `PyTypeObject` odkazuje jeho `ob_type` pole) mají typy ukazatel funkce. Pokud jeden z těchto ukazatelů na funkce odkazuje na funkci, která může být vyřešen a že fungují má `self` parametr s typem podrobnější než `PyObject*`, pak tento typ se považuje za základního typu. Například pokud `ob_type->tp_init` bodů daného objektu na následující funkce:

```c
static int FobObject_init(FobObject* self, PyObject* args, PyObject* kwds) {
    return 0;
}
```

pak ladicího programu správně lze odvodit, že C typ objektu je `FobObject`. Pokud se nepodařilo určit přesnější typu z `tp_init`, přesune jiné pole. Pokud nepodařilo odvodit typ z jakéhokoli z těchto polí, uzel "[C++ zobrazení]" uvede objektu jako `PyObject` instance.

Vždycky získat užitečné znázornění pro vlastní typy vytvořené, je nejvhodnější při registraci typu registrovat aspoň jeden speciální funkce a použít silného typu `self` parametr. Většina typů splnění tohoto požadavku přirozeně; není-li Ano, pak `tp_init` je obvykle nejpohodlnější záznam, který má používat pro tento účel. Fiktivní provádění `tp_init` pro typ, který je k dispozici pouze povolit ladicí program typu odvození právě vrátit nula okamžitě, stejně jako výše uvedený příklad.

## <a name="differences-from-standard-python-debugging"></a>Rozdíl oproti standardní ladění Python

Ladicí program ve smíšeném režimu se liší od [standardní ladicí program Python](debugging-python-in-visual-studio.md) v že zavádí některé další funkce, ale chybí některé Python související možnosti:

- Nepodporované funkce: podmíněné zarážky, ladění interaktivních okna a vzdálené ladění napříč platformami.
- Příkazové podokno: je k dispozici ale s omezenou podmnožinou jeho funkce, včetně všech omezení tady.
- Podporované verze Python: CPython 2.7 a 3.3 + jenom.
- Prostředí sady Visual Studio: Při použití Python s prostředí sady Visual Studio (např. Pokud jste nainstalovali pomocí integrovaného instalační program), Visual Studio se nepodařilo otevřít projekty C++ a možnosti úpravy souborů C++, je pouze základní textový editor. Ladění C/C++ a ladění ve smíšeném režimu jsou však plně podporovány v prostředí se zdrojovým kódem, zanoříte se do nativního kódu a C++ vyhodnocení výrazu v ladicím programu systému windows.
- Zobrazení a rozšiřování objekty: při zobrazení Python objekty v lokální a sledovat ladicího programu nástroje systému windows, ve smíšeném režimu ladicí program zobrazuje pouze struktura objektů. Je automaticky vyhodnotit vlastnosti, nebo zobrazit počítaný atributy. Pro kolekce, se zobrazí pouze elementy pro typy předdefinovanou kolekci (`tuple`, `list`, `dict`, `set`). Vlastní kolekce typy nejsou vizualizuje jako kolekce, pokud se dědí z nějaký typ předdefinované kolekce.
- Vyhodnocení výrazu: viz níže.

### <a name="expression-evaluation"></a>Vyhodnocení výrazu

Standardní ladicí program Python umožňuje vyhodnocení výrazů libovolný Python ve sledování a okamžitou windows při procesu vyladěnou kurzoru v libovolném bodě v kódu, tak dlouho, dokud není blokován v vstupně-výstupní operace nebo jiné podobné systémového volání. Při ladění ve smíšeném režimu, může být libovolný výrazy vyhodnocen jenom v případě, že byl zastaven v kódu jazyka Python, po zarážku, nebo když zanoříte se do kódu. Výrazy lze vyhodnotit pouze na vlákno, na kterém zarážce nebo taktování operace došlo k chybě.

Při zastavení v nativním kódu nebo v kódu jazyka Python, kde výše uvedených podmínek se nevztahují (například po kroku out operaci, nebo v jiném podprocesu), je omezený přístup místní a globální proměnné v oboru aktuálně vybrané vyhodnocení výrazu rámce, přístup k jejich pole a indexování předdefinovanou kolekci typů s literály. Následující výraz například může být vyhodnocen v jakýkoliv kontext (za předpokladu, že všechny identifikátory odkazovat existujících proměnných a polí odpovídající typy):

```python
foo.bar[0].baz['key']
```

Ladicí program ve smíšeném režimu je takové výrazy také překládány jinak. Všechny operace přístup ke členu vyhledat pouze pole, které jsou přímo součástí objektu (například položku v jeho `__dict__` nebo `__slots__`, nebo pole nativní struktura, který je vystaven Python prostřednictvím `tp_members`) a ignorovat jakékoli `__getattr__`, `__getattribute__`nebo popisovač logiku. Podobně, všechny operace indexování Ignorovat `__getitem__`a získat přímo přístup k vnitřní datové struktury kolekcí.

Z důvodu konzistence používá se pro všechny výrazy, které odpovídají omezení pro vyhodnocení výrazů omezená, bez ohledu na to, jestli jsou povolené libovolný výrazy k aktuálnímu bodu zastavení toto schéma rozlišení názvu. Chcete-li vynutit správné Python sémantiku při vyhodnocování se plné je k dispozici, uzavřete výrazu v závorkách:

```python
(foo.bar[0].baz['key'])
```