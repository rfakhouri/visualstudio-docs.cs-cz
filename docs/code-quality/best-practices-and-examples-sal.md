---
title: Doporučené postupy a příklady (poznámky SAL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d8910c9b5d36cecec82bf0e386e294759113c76e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="best-practices-and-examples-sal"></a>Doporučené postupy a příklady (poznámky SAL)
Tady jsou některé způsoby maximum mimo zdrojového kódu poznámky jazyk (SAL) a vyhnout se některé běžné problémy.

## <a name="in"></a>\_V\_

Pokud funkce by měla k zápisu do elementu, použijte `_Inout_` místo `_In_`. To je zvlášť důležité v případech automatizované převod starší makra SAL. Před SAL, používá mnoho programátorů makra jako komentáře – makra, které byly pojmenovány `IN`, `OUT`, `IN_OUT`, nebo variant tyto názvy. Doporučujeme převést tyto makra SAL, ale také doporučujeme vám buďte opatrní, když je převést protože kód byl změněn, protože původní prototypu byla zapsána a už může staré makro odrážet, co kód dělá. Buďte opatrní hlavně o `OPTIONAL` komentář makro, protože je často umístěn nesprávně – například na nesprávný straně čárkou.

```cpp

// Incorrect
void Func1(_In_ int *p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}

// Correct
void Func2(_Inout_ PCHAR p1)
{
    if (p1 == NULL)
        return;

    *p1 = 1;
}
```

## <a name="opt"></a>\_OPT\_

Pokud má volající není povoleno předávat ukazatele null, použijte `_In_` nebo `_Out_` místo `_In_opt_` nebo `_Out_opt_`. To platí i pro funkci, která ověří jeho parametry a vrátí chybu, pokud má hodnotu NULL, pokud by neměl být. I když s funkcí zkontrolovat její parametr neočekávanou hodnotu NULL a elegantně vrátí je vhodné Obranným kódování, neznamená to, že parametr poznámky můžou být nepovinné typu (`_*Xxx*_opt_`).

```cpp

// Incorrect
void Func1(_Out_opt_ int *p1)
{
    *p = 1;
}

// Correct
void Func2(_Out_ int *p1)
{
    *p = 1;
}

```

## <a name="predefensive-and-postdefensive"></a>\_Před\_Obranným\_ a \_Post\_Obranným\_

Pokud funkci se zobrazuje v hranice vztahu důvěryhodnosti, doporučujeme použít `_Pre_defensive_` poznámky.  "Obranným" modifikátor upraví určité poznámky k označení, že, v okamžiku volání, rozhraní zkontrolovat výhradně, ale v těle implementace musí předpokládat, že může být předány nesprávné parametry. V takovém případě `_In_ _Pre_defensive_` upřednostňuje na hranice vztahu důvěryhodnosti indikující, že i když volající dojde k chybě, pokud se pokusí předat hodnotu NULL, tělo funkce bude analyzovat, jako kdyby parametr může mít hodnotu NULL a všechny pokusy o zrušte odkazovat ukazatele bez předchozího budou označeny kontroly hodnotu NULL.  A `_Post_defensive_` poznámky je také k dispozici pro použití v zpětná volání, kde důvěryhodná strana předpokládá se, že volající a nedůvěryhodný kód je názvem kód.

## <a name="outwrites"></a>\_Out\_zapíše\_

Následující příklad ukazuje běžné zneužití `_Out_writes_`.

```cpp

// Incorrect
void Func1(_Out_writes_(size) CHAR *pb,
    DWORD size
);

```

Poznámka `_Out_writes_` označuje, že máte vyrovnávací paměti. Má `cb` bajtů přidělených s prvním bajtem inicializován po ukončení. Tato anotace není výhradně nesprávné a je vhodné express přidělená velikost. Však neobsahuje žádné informace, kolik elementy jsou inicializovány funkcí.

Další příklad ukazuje tři správné způsoby, jak plně určit přesnou velikost části inicializovaného vyrovnávací paměti.

```cpp

// Correct
void Func1(_Out_writes_to_(size, *pCount) CHAR *pb,
    DWORD size,
    PDWORD pCount
);

void Func2(_Out_writes_all_(size) CHAR *pb,
    DWORD size
);

void Func3(_Out_writes_(size) PSTR pb,
    DWORD size
);

```

## <a name="out-pstr"></a>\_Out\_ PSTR

Použití `_Out_ PSTR` téměř vždy je nesprávný. To se interpretuje jako výstupní parametr, který odkazuje na znak vyrovnávací paměť s a je ukončené hodnotou NULL.

```cpp

// Incorrect
void Func1(_Out_ PSTR pFileName, size_t n);

// Correct
void Func2(_Out_writes_(n) PSTR wszFileName, size_t n);

```

Poznámky jako `_In_ PCSTR` je běžné a užitečné. Odkazuje na vstupní řetězec, který má hodnotu NULL ukončení, protože předběžnou z `_In_` umožňuje rozpoznávání řetězce ukončené hodnotou NULL.

## <a name="in-wchar-p"></a>\_V\_ WCHAR * p

`_In_ WCHAR* p` uvádí, zda je vstupní ukazatel `p` který odkazuje na jeden znak. Ve většině případů je to ale pravděpodobně není specifikace, která je určena. Místo toho co je pravděpodobně určený je specifikace ukončené hodnotou NULL pole; Chcete-li provést, použijte `_In_ PWSTR`.

```cpp

// Incorrect
void Func1(_In_ WCHAR* wszFileName);

// Correct
void Func2(_In_ PWSTR wszFileName);

```

Chybí správné specifikaci ukončení NULL je běžné. Použít příslušné `STR` verze nahradit typu, jak je znázorněno v následujícím příkladu.

```cpp

// Incorrect
BOOL StrEquals1(_In_ PCHAR p1, _In_ PCHAR p2)
{
    return strcmp(p1, p2) == 0;
}

// Correct
BOOL StrEquals2(_In_ PSTR p1, _In_ PSTR p2)
{
    return strcmp(p1, p2) == 0;
}

```

## <a name="outrange"></a>\_Out_range\_

Pokud tento parametr ukazatel a chcete express rozsahu hodnota elementu, který je odkazováno pomocí ukazatele, `_Deref_out_range_` místo `_Out_range_`. V následujícím příkladu, rozsahu * pcbFilled vyjádřena, není pcbFilled.

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Out_range_(0, cbSize) DWORD *pcbFilled
);

// Correct
void Func2(
    _Out_writes_bytes_to_(cbSize, *pcbFilled) BYTE *pb,
    DWORD cbSize,
    _Deref_out_range_(0, cbSize) _Out_ DWORD *pcbFilled
);

```

 `_Deref_out_range_(0, cbSize)` není nezbytně nutné pro některé nástroje, protože ho lze odvodit z `_Out_writes_to_(cbSize,*pcbFilled)`, ale pro úplnost je zde zobrazen.

## <a name="wrong-context-in-when"></a>Nesprávný kontextu \_při\_

Další běžné chybou je použít po stavu vyhodnocení pro předběžné podmínky. V následujícím příkladu `_Requires_lock_held_` je předběžné podmínky.

```cpp

// Incorrect
_When_(return == 0, _Requires_lock_held_(p->cs))
int Func1(_In_ MyData *p, int flag);

// Correct
_When_(flag == 0, _Requires_lock_held_(p->cs))
int Func2(_In_ MyData *p, int flag);

```

 Výraz `result` odkazuje na hodnotu po stavu, která není k dispozici v předběžné stavu.

## <a name="true-in-success"></a>Hodnota TRUE, v \_úspěch\_

Pokud funkci úspěšné po nenulové hodnoty vrácené hodnoty, použijte `return != 0` jako podmínka pro úspěch místo `return == TRUE`. NonZero nemusí nezbytně znamenat, ekvivalenční na skutečnou hodnotu, která kompilátor poskytuje pro `TRUE`. Parametr pro `_Success_` je výraz, a těchto výrazů, jsou vyhodnoceny jako ekvivalentní: `return != 0`, `return != false`, `return != FALSE`, a `return` bez parametrů a porovnání.

```cpp

// Incorrect
_Success_(return == TRUE, _Acquires_lock_(*lpCriticalSection))
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);

// Correct
_Success_(return != 0, _Acquires_lock_(*lpCriticalSection))
BOOL WINAPI TryEnterCriticalSection(
  _Inout_ LPCRITICAL_SECTION lpCriticalSection
);

```

## <a name="reference-variable"></a>Odkaz na proměnnou

Pro odkaz na proměnnou, předchozí verzi SAL předpokládané ukazatele použít jako cíl poznámky a požadované přidání `__deref` pro poznámky, které jsou připojené k odkaz na proměnnou. Tato verze používá samotného objektu a nevyžaduje další `_Deref_`.

```cpp

// Incorrect
void Func1(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Deref_ _Out_range_(0, 2) _Out_ DWORD &cbSize
);

// Correct
void Func2(
    _Out_writes_bytes_all_(cbSize) BYTE *pb,
    _Out_range_(0, 2) _Out_ DWORD &cbSize
);

```

## <a name="annotations-on-return-values"></a>Poznámky na vrácených hodnotách

Následující příklad ukazuje častých problémů v poznámky návratovou hodnotu.

```cpp

// Incorrect
_Out_opt_ void *MightReturnNullPtr1();

// Correct
_Ret_maybenull_ void *MightReturnNullPtr2();

```

V tomto příkladu `_Out_opt_` říká, že ukazatele může mít hodnotu NULL jako součást předběžnou podmínku. Předběžné podmínky však nelze použít k návratovou hodnotu. V takovém případě je správný Poznámka `_Ret_maybenull_`.

## <a name="see-also"></a>Viz také

[Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
[porozumění SAL](../code-quality/understanding-sal.md)
[zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md) 
 [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)
[zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)
[zadávání poznámek k chování při zamykání](../code-quality/annotating-locking-behavior.md) 
 [Určující, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)
[vnitřní funkce](../code-quality/intrinsic-functions.md)