---
title: Porozumění SAL
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 59c5dfa3d7e1e47fbcd2b0d11a0671b2594125c9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923800"
---
# <a name="understanding-sal"></a>Porozumění SAL

Jazyk Microsoft Source-Code Annotation (SAL) poskytuje sadu poznámek, které můžete použít k popsání toho, jak funkce používá své parametry, předpoklady, které se o nich týkají, a záruky, které při jejím dokončení vytvoří. Poznámky jsou definovány v hlavičkovém souboru `<sal.h>`. Analýza kódu sady Visual Studio C++ pro použití poznámek SAL pro úpravu své analýzy funkcí. Další informace o SAL 2,0 pro vývoj ovladačů Windows najdete v tématu [poznámky sal 2,0 pro ovladače Windows](http://go.microsoft.com/fwlink/?LinkId=250979).

Nativně, C a C++ poskytují jenom omezené způsoby, jak vývojářům konzistentně vyjádřit a nerovnost. Pomocí poznámek SAL můžete své funkce popsat podrobněji, aby vývojáři, kteří je používají, lépe pochopili, jak je používat.

## <a name="what-is-sal-and-why-should-you-use-it"></a>Co je SAL a proč byste ji měli používat?

SAL je pouze nenákladný způsob, jak nechat kompilátor kontrolovat váš kód.

### <a name="sal-makes-code-more-valuable"></a>SAL dělá kód užitečnější

SAL vám může usnadnit návrh kódu pro lidi i pro nástroje pro analýzu kódu. Vezměte v úvahu tento příklad, který ukazuje běhovou funkci `memcpy`jazyka C:

```cpp

void * memcpy(
   void *dest,
   const void *src,
   size_t count
);
```

Můžete zjistit, co tato funkce dělá? Pokud je funkce implementována nebo volána, je nutné zachovat určité vlastnosti, aby bylo zajištěno správnost programu. Pouhým zobrazením deklarace, jako je například v příkladu, neznáte, co jsou. Bez poznámek SAL byste se museli spoléhat na dokumentaci nebo komentáře ke kódu. V dokumentaci `memcpy` k MSDN se říkáme:

> "Kopíruje počet bajtů src na cíl. Pokud se zdrojový a cílový překrývají, chování memcpy není definováno. Použijte memmove k obsluze překrývajících se oblastí.
> **Poznámka k zabezpečení:** Ujistěte se, že cílová vyrovnávací paměť má stejnou velikost nebo je větší než zdrojová vyrovnávací paměť. Další informace najdete v tématu předcházení přetečení vyrovnávací paměti.

Dokumentace obsahuje několik bitů informací, které naznačují, že váš kód musí udržovat určité vlastnosti, aby bylo zajištěno správné fungování programu:

- `memcpy``count` kopíruje bajty ze zdrojové vyrovnávací paměti do cílové vyrovnávací paměti.

- Cílová vyrovnávací paměť musí být alespoň stejně velká jako zdrojová vyrovnávací paměť.

Kompilátor ale nemůže přečíst dokumentaci nebo neformální komentáře. Neví, že mezi těmito dvěma vyrovnávacími paměťmi a `count`a zároveň nedokáže efektivně odhadnout relaci. SAL může poskytnout přehlednější informace o vlastnostech a implementaci funkce, jak je znázorněno zde:

```cpp

void * memcpy(
   _Out_writes_bytes_all_(count) void *dest,
   _In_reads_bytes_(count) const void *src,
   size_t count
);
```

Všimněte si, že tyto poznámky se podobají informacím v dokumentaci MSDN, ale jsou stručnější a sledují sémantický vzor. Při čtení tohoto kódu můžete rychle porozumět vlastnostem této funkce a vyhnout se problémům se zabezpečením při přetečení vyrovnávací paměti. Ještě lepší, sémantické vzory, které SAL poskytují, můžou zlepšit efektivitu a efektivitu automatizovaných nástrojů pro analýzu kódu v brzkém zjišťování možných chyb. Představte si, že někdo zapisuje `wmemcpy`tuto implementaci ladění:

```cpp

wchar_t * wmemcpy(
   _Out_writes_all_(count) wchar_t *dest,
   _In_reads_(count) const wchar_t *src,
   size_t count)
{
   size_t i;
   for (i = 0; i <= count; i++) { // BUG: off-by-one error
      dest[i] = src[i];
   }
   return dest;
}
```

Tato implementace obsahuje běžnou chybu mimo jednu. Naštěstí autor kódu zahrnoval anotaci velikosti vyrovnávací paměti SAL – Nástroj pro analýzu kódu by mohl zachytit chybu tím, že analyzuje tuto funkci samostatně.

### <a name="sal-basics"></a>Základy SAL
SAL definuje čtyři základní druhy parametrů, které jsou zařazeny do kategorií podle vzorce použití.

|Kategorie|Anotace parametru|Popis|
|--------------|--------------------------|-----------------|
|**Vstup do volané funkce**|`_In_`|Data se předávají volané funkci a jsou považována za jen pro čtení.|
|**Vstup na volanou funkci a výstup do volajícího**|`_Inout_`|Použitelná data se předávají do funkce a můžou se změnit.|
|**Výstup do volajícího**|`_Out_`|Volající poskytuje prostor pro volanou funkci, do které se zapisuje. Volaná funkce zapisuje data do tohoto prostoru.|
|**Výstup ukazatele na volajícího**|`_Outptr_`|Jako **výstup do volajícího**. Hodnota vrácená volanou funkcí je ukazatel.|

Tyto čtyři základní poznámky je možné v různých způsobech považovat za explicitní. Ve výchozím nastavení se předpokládá, že jsou vyžadovány parametry ukazatele s poznámkami, musí být pro funkci nenulové, aby byla funkce úspěšná. Nejčastěji používaná variace základních poznámek znamená, že parametr ukazatele je nepovinný – Pokud má hodnotu NULL, funkce může i nadále úspěšně fungovat.

Tato tabulka ukazuje, jak rozlišovat mezi požadovanými a nepovinnými parametry:

||Parametry jsou povinné.|Parametry jsou volitelné.|
|-|-----------------------------|-----------------------------|
|**Vstup do volané funkce**|`_In_`|`_In_opt_`|
|**Vstup na volanou funkci a výstup do volajícího**|`_Inout_`|`_Inout_opt_`|
|**Výstup do volajícího**|`_Out_`|`_Out_opt_`|
|**Výstup ukazatele na volajícího**|`_Outptr_`|`_Outptr_opt_`|

Tyto poznámky vám pomůžou identifikovat možné neinicializované hodnoty a neplatný ukazatel s hodnotou null používá formálním a přesným způsobem. Předání hodnoty NULL požadovanému parametru může způsobit chybu nebo může způsobit vrácení kódu chyby "neúspěšné". V obou případech nemůže funkce při provádění své úlohy úspěšně fungovat.

## <a name="sal-examples"></a>Příklady SAL
V této části jsou uvedeny příklady kódu pro základní poznámky SAL.

### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Hledání vad pomocí nástroje Visual Studio Code Analysis Tool
V příkladech se nástroj Visual Studio Code Analysis používá společně s poznámkami SAL k nalezení vad kódu. Tady je postup.

#### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>Použití nástrojů pro analýzu kódu a SAL v nástroji Visual Studio

1. V aplikaci Visual Studio otevřete C++ projekt, který obsahuje poznámky SAL.

2. Na panelu nabídek vyberte možnost **sestavit**, **Spustit analýzu kódu v řešení**.

     Vezměte v úvahu\_ příklad v této části. \_ Pokud na něm spustíte analýzu kódu, zobrazí se toto upozornění:

    > **C6387 neplatná hodnota parametru** ' pInt ' může být ' 0 ': to nedodržuje specifikace pro funkci ' InCallee '.

### <a name="example-the-_in_-annotation"></a>Příklad: \_V\_ poznámce

`_In_` Poznámka znamená, že:

- Parametr musí být platný a nebude změněn.

- Funkce bude načtena pouze z vyrovnávací paměti s jedním prvkem.

- Volající musí poskytnout vyrovnávací paměť a inicializovat ji.

- `_In_`Určuje "jen pro čtení". `_In_` Běžnou`_Inout_` chybou je použít na parametr, který má anotaci místo toho.

- `_In_`je povoleno, ale analyzátor ignoruje na skalárních skalárních modulech.

```cpp
void InCallee(_In_ int *pInt)
{
   int i = *pInt;
}

void GoodInCaller()
{
   int *pInt = new int;
   *pInt = 5;

   InCallee(pInt);
   delete pInt;
}

void BadInCaller()
{
   int *pInt = NULL;
   InCallee(pInt); // pInt should not be NULL
}
```

Použijete-li analýzu Visual Studio Code v tomto příkladu, ověří, že volající přecházejí ukazatel, který není null, na inicializovaný buffer pro `pInt`. V takovém případě `pInt` ukazatel nemůže mít hodnotu null.

### <a name="example-the-_in_opt_-annotation"></a>Příklad: \_Anotaceopt\_\_

`_In_opt_`je stejný jako `_In_`s tím rozdílem, že vstupní parametr může mít hodnotu null a proto by funkce měla tuto funkci kontrolovat.

```cpp

void GoodInOptCallee(_In_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
   }
}

void BadInOptCallee(_In_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
}

void InOptCaller()
{
   int *pInt = NULL;
   GoodInOptCallee(pInt);
   BadInOptCallee(pInt);
}
```

Analýza Visual Studio Code ověří, že funkce před přístupem k vyrovnávací paměti kontroluje hodnotu NULL.

### <a name="example-the-_out_-annotation"></a>Příklad: \_VýstupníPoznámka\_

`_Out_`podporuje běžný scénář, ve kterém je předán ukazatel bez hodnoty NULL, který odkazuje na vyrovnávací paměť elementu, a funkce inicializuje element. Volající nemusí před voláním inicializovat vyrovnávací paměť; volaná funkce příslibů k jejímu inicializaci, než se vrátí.

```cpp
void GoodOutCallee(_Out_ int *pInt)
{
   *pInt = 5;
}

void BadOutCallee(_Out_ int *pInt)
{
   // Did not initialize pInt buffer before returning!
}

void OutCaller()
{
   int *pInt = new int;
   GoodOutCallee(pInt);
   BadOutCallee(pInt);
   delete pInt;
}
```

Nástroj pro analýzu Visual Studio Code ověřuje, že volající předává ukazatel bez hodnoty null do vyrovnávací paměti pro `pInt` a zda je vyrovnávací paměť inicializována funkcí před tím, než se vrátí.

### <a name="example-the-_out_opt_-annotation"></a>Příklad: \_Anotaceopt\_\_

`_Out_opt_`je stejný jako `_Out_`s tím rozdílem, že parametr může mít hodnotu null a proto by měla funkce tuto funkci kontrolovat.

```cpp
void GoodOutOptCallee(_Out_opt_ int *pInt)
{
   if (pInt != NULL) {
      *pInt = 5;
   }
}

void BadOutOptCallee(_Out_opt_ int *pInt)
{
   *pInt = 5; // Dereferencing NULL pointer 'pInt'
}

void OutOptCaller()
{
   int *pInt = NULL;
   GoodOutOptCallee(pInt);
   BadOutOptCallee(pInt);
}
```

Analýza Visual Studio Code ověřuje, že tato funkce před tím, než `pInt` se vrátí zpět na odkaz, kontroluje `pInt` , jestli je hodnota null, a pokud není null, tato vyrovnávací paměť je inicializována funkcí.

### <a name="example-the-_inout_-annotation"></a>Příklad: Anotace\_ InOut \_

`_Inout_`slouží k přidání poznámky k parametru ukazatele, který může být změněn funkcí. Ukazatel musí před voláním ukazovat na platná inicializovaná data a i když se změní, musí mít při návratu stále platnou hodnotu. Poznámka určuje, že funkce může volně číst a zapisovat do vyrovnávací paměti s jedním prvkem. Volající musí poskytnout vyrovnávací paměť a inicializovat ji.

> [!NOTE]
> Například `_Out_` ,`_Inout_` se musí vztahovat na upravitelnou hodnotu.

```cpp
void InOutCallee(_Inout_ int *pInt)
{
   int i = *pInt;
   *pInt = 6;
}

void InOutCaller()
{
   int *pInt = new int;
   *pInt = 5;
   InOutCallee(pInt);
   delete pInt;
}

void BadInOutCaller()
{
   int *pInt = NULL;
   InOutCallee(pInt); // 'pInt' should not be NULL
}
```

Visual Studio Code Analysis ověřuje, že volající přecházejí ukazatel, který nemá hodnotu null, do inicializované vyrovnávací `pInt`paměti pro a který před `pInt` vrácením je stále null a je inicializována vyrovnávací paměť.

### <a name="example-the-_inout_opt_-annotation"></a>Příklad: InOut anotace\_ opt \_\_

`_Inout_opt_`je stejný jako `_Inout_`s tím rozdílem, že vstupní parametr může mít hodnotu null a proto by funkce měla tuto funkci kontrolovat.

```cpp
void GoodInOutOptCallee(_Inout_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
      *pInt = 6;
   }
}

void BadInOutOptCallee(_Inout_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
   *pInt = 6;
}

void InOutOptCaller()
{
   int *pInt = NULL;
   GoodInOutOptCallee(pInt);
   BadInOutOptCallee(pInt);
}
```

Visual Studio Code Analysis ověří, že tato funkce před tím, než se vrátí do vyrovnávací paměti, zkontroluje, `pInt` jestli má hodnotu null, a pokud není null, tato vyrovnávací paměť se před vrácením funkce inicializuje.

### <a name="example-the-_outptr_-annotation"></a>Příklad: Anotace\_ Outptr \_

`_Outptr_`slouží k přidání poznámky k parametru, který je určen pro návrat ukazatele.  Samotný parametr by neměl mít hodnotu NULL a volaná funkce vrátí ukazatel, který není NULL, a tento ukazatel ukazuje na inicializovaná data.

```cpp
void GoodOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 5;

   *pInt = pInt2;
}

void BadOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   // Did not initialize pInt buffer before returning!
   *pInt = pInt2;
}

void OutPtrCaller()
{
   int *pInt = NULL;
   GoodOutPtrCallee(&pInt);
   BadOutPtrCallee(&pInt);
}
```

Analýza Visual Studio Code ověřuje, že volající předává ukazatel, který nemá hodnotu null `*pInt`pro, a před tím, než se vrátí, do vyrovnávací paměti je inicializován funkcí.

### <a name="example-the-_outptr_opt_-annotation"></a>Příklad: Outptr anotace\_ opt \_\_

`_Outptr_opt_`je stejná jako `_Outptr_`s tím rozdílem, že parametr je volitelný – volající může předat ukazatel s hodnotou null pro parametr.

```cpp
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;

   if(pInt != NULL) {
      *pInt = pInt2;
   }
}

void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'
}

void OutPtrOptCaller()
{
   int **ppInt = NULL;
   GoodOutPtrOptCallee(ppInt);
   BadOutPtrOptCallee(ppInt);
}
```

Visual Studio Code Analysis ověří, že tato funkce před tím, než `*pInt` se vrátí zpět na odkaz, zkontroluje, jestli je hodnota null, a že se vyrovnávací paměť inicializuje funkcí.

### <a name="example-the-_success_-annotation-in-combination-with-_out_"></a>Příklad: Poznámka k\_úspěchuv kombinaci s \_out \_\_

Poznámky lze použít pro většinu objektů.  Konkrétně můžete opatřit poznámkami celou funkci.  Jednou z nejoblíbenějších vlastností funkce je, že může být úspěšná nebo neúspěšná. Ale podobně jako asociace mezi vyrovnávací pamětí a její velikostí, CC++ /nemůže vyjádřit úspěch nebo neúspěch funkce. Pomocí `_Success_` Anotace můžete říci, jakou úspěšnost funkce vypadá jako.  Parametr `_Success_` anotace je pouze výraz, který je v případě, že je hodnota true, označuje, že funkce byla úspěšná. Výraz může být cokoli, co může analyzátor poznámek zpracovat. Účinky poznámek po návratu funkce jsou použitelné pouze v případě, že funkce bude úspěšná. Tento příklad ukazuje, `_Success_` jak funguje interakce `_Out_` s nástrojem k provedení pravé věci. Můžete použít klíčové slovo `return` pro reprezentaci návratové hodnoty.

```cpp
_Success_(return != false) // Can also be stated as _Success_(return)
bool GetValue(_Out_ int *pInt, bool flag)
{
   if(flag) {
      *pInt = 5;
      return true;
   } else {
      return false;
   }
}
```

Poznámka způsobí, že Visual Studio Code analýza ověří, zda volající předává ukazatel bez hodnoty null do vyrovnávací paměti pro `pInt`a zda je vyrovnávací paměť inicializována funkcí před tím, než se vrátí. `_Out_`

## <a name="sal-best-practice"></a>Osvědčený postup SAL

### <a name="adding-annotations-to-existing-code"></a>Přidávání poznámek k existujícímu kódu

SAL je výkonná technologie, která vám může pomoci zlepšit zabezpečení a spolehlivost kódu. Až se naučíte, můžete tuto novou dovednost použít na každodenní práci. V novém kódu můžete použít specifikace založené na SAL podle návrhu v celém. ve starším kódu můžete přidat poznámky přírůstkově a zvýšit tak výhody pokaždé, když aktualizujete.

Veřejné hlavičky společnosti Microsoft jsou již opatřeny poznámkami. Proto doporučujeme, abyste ve vašich projektech nejprve přiřadíte funkce na úrovni listu a funkce, které volají rozhraní API systému Win32, aby získaly největší užitek.

### <a name="when-do-i-annotate"></a>Kdy se dá opatřit poznámkami?

Tady je několik pokynů:

- Opatřit poznámkami všechny parametry ukazatele.

- Poznámky k rozsahu hodnot můžete opatřit poznámkami, aby analýza kódu mohla zajistit bezpečnost vyrovnávací paměti a ukazatele.

- Opatřit poznámkami pravidla uzamykání a zamykací vedlejší účinky. Další informace najdete v tématu [poznámky k chování při zamykání](../code-quality/annotating-locking-behavior.md).

- Opatřit poznámkami vlastnostmi ovladače a dalšími vlastnostmi specifických pro doménu.

Nebo můžete opatřit všechny parametry tak, aby byl váš záměr jasný a bylo tak snazší zkontrolovat, zda byly poznámky provedeny.

## <a name="related-resources"></a>Související prostředky

[Blog týmu analýzy kódu](http://go.microsoft.com/fwlink/p/?LinkId=251197)

## <a name="see-also"></a>Viz také

- [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Zadávání poznámek k parametrům funkcí a návratovým hodnotám](../code-quality/annotating-function-parameters-and-return-values.md)
- [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)
- [Zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)
- [Zadávání poznámek o chování při zamykání](../code-quality/annotating-locking-behavior.md)
- [Určení, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Doporučené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)