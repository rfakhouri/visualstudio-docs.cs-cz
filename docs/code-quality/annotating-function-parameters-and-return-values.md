---
title: "Zadávání poznámek k parametrům funkcí a návratovým hodnotám | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Ouptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e256b519600a983886ac6d21317ef1757d7497f1
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="annotating-function-parameters-and-return-values"></a>Zadávání poznámek k parametrům funkcí a návratovým hodnotám
Tento článek popisuje typické použití anotací jednoduché funkce parametry – skalárních hodnot a ukazatelé na třídy a struktury – a většinou druhů vyrovnávací paměti.  Tento článek také ukazuje obecné vzory využití pro poznámky. Další poznámky, které se vztahují na funkce, najdete v části [zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)  
  
## <a name="pointer-parameters"></a>Parametry ukazatele  
 Pro poznámky v následující tabulce když je právě poznámkou parametr ukazatele, analyzátor nahlásí chybu, pokud je ukazatel hodnotu null.  To platí pro ukazatele a libovolné položky dat, která je nastavena.  
  
 **Poznámky a popisy**  
  
-   `_In_`  
  
     Označí vstupní parametry, které jsou skalárních hodnot, struktury, ukazatele na struktury a podobně.  Explicitně mohou být použity na jednoduchý skalárních hodnot.  Parametr musí být platná v předběžné stavu a se nezmění.  
  
-   `_Out_`  
  
     Označí výstupní parametry, které jsou skalárních hodnot, struktury, ukazatele na struktury a podobně.  Nevztahují to na objekt, který nelze vrátit hodnotu – například skalární hodnota, je předaná hodnota.  Parametr nemusí být ve stavu před platný, ale musí být platná po stavu.  
  
-   `_Inout_`  
  
     Označí parametr, který se změní podle funkce.  Musí být ve stavu před a po stavu platný, ale je předpokládá, že mají různé hodnoty před a po volání. Musíte použít upravitelnými hodnotu.  
  
-   `_In_z_`  
  
     Ukazatel na řetězec ukončené hodnotou null, který se používá jako vstup.  V předběžné stavu musí být platný řetězec.  Varianty `PSTR`, které už mít správný poznámky, jsou upřednostněny.  
  
-   `_Inout_z_`  
  
     Ukazatel na pole znaků ukončené hodnotou null, které budou upraveny.  Musí být platný, před a po volání, ale hodnota se předpokládá, že se změnilo.  Null ukončení může být přesunuta, ale můžete získat přístup pouze elementy až do ukončení původní hodnotu null.  
  
-   `_In_reads_(s)`  
  
     `_In_reads_bytes_(s)`  
  
     Ukazatel na pole, který je pro čtení funkcí.  Toto pole je velikost `s` prvky, které musí být platné.  
  
     `_bytes_` Variant dává velikost v bajtech místo elementy. Používejte jenom v případě, že velikost nesmí být vyjádřena jako elementy.  Například `char` využije řetězce `_bytes_` variant pouze v případě, že podobné funkce, která používá `wchar_t` by.  
  
-   `_In_reads_z_(s)`  
  
     Ukazatel na pole, které je ukončené hodnotou null a má známé velikost. Elementy až null ukončení – nebo `s` Pokud není null nebyl – musí být platná v předběžné stavu.  Pokud je znám velikost v bajtech, škálovat `s` velikostí elementu.  
  
-   `_In_reads_or_z_(s)`  
  
     Ukazatel na pole, které je ukončené hodnotou null, nebo má známé velikost nebo obojí. Elementy až null ukončení – nebo `s` Pokud není null nebyl – musí být platná v předběžné stavu.  Pokud je znám velikost v bajtech, škálovat `s` velikostí elementu.  (Používají pro `strn` rodiny.)  
  
-   `_Out_writes_(s)`  
  
     `_Out_writes_bytes_(s)`  
  
     Ukazatel na pole `s` prvky (odezvy v bajtech), které se zapíšou funkcí.  Elementy pole nemusí být platný v předběžné stavu a je počet elementů, které jsou platné ve stavu po neurčené.  Pokud jsou poznámky na typ parametru, budou použity v po stavu. Zvažte například následující kód.  
  
     `typedef _Null_terminated_ wchar_t *PWSTR; void MyStringCopy(_Out_writes_ (size) PWSTR p1,    _In_ size_t size,    _In_ PWSTR p2);`  
  
     V tomto příkladu volající poskytuje vyrovnávací paměti `size` prvky pro `p1`.  `MyStringCopy`Díky některé z těchto elementů platný. Je důležité `_Null_terminated_` poznámky na `PWSTR` znamená, že `p1` je ukončené hodnotou null v po stavu.  Tímto způsobem je dobře definovaný počet elementů platný, ale počet konkrétní element není povinný.  
  
     `_bytes_` Variant dává velikost v bajtech místo elementy. Používejte jenom v případě, že velikost nesmí být vyjádřena jako elementy.  Například `char` využije řetězce `_bytes_` variant pouze v případě, že podobné funkce, která používá `wchar_t` by.  
  
-   `_Out_writes_z_(s)`  
  
     Ukazatel na pole `s` elementy.  Elementy nemusí být platný v předběžné stavu.  V následující po stavu, prvků až prostřednictvím null ukončení – které musí být přítomen – musí být platné.  Pokud je znám velikost v bajtech, škálovat `s` velikostí elementu.  
  
-   `_Inout_updates_(s)`  
  
     `_Inout_updates_bytes_(s)`  
  
     Ukazatel na pole, která je číst a zapisovat do ve funkci.  Je velikost `s` prvky a ve stavu před a po stavu platná.  
  
     `_bytes_` Variant dává velikost v bajtech místo elementy. Používejte jenom v případě, že velikost nesmí být vyjádřena jako elementy.  Například `char` využije řetězce `_bytes_` variant pouze v případě, že podobné funkce, která používá `wchar_t` by.  
  
-   `_Inout_updates_z_(s)`  
  
     Ukazatel na pole, které je ukončené hodnotou null a má známé velikost. Elementy až prostřednictvím null ukončení – které musí být přítomen – musí být ve stavu před a po stavu platná.  Hodnota v po stavu se předpokládá, že se liší od hodnoty v předběžné stavu; To zahrnuje umístění ukončení hodnotu null. Pokud je znám velikost v bajtech, škálovat `s` velikostí elementu.  
  
-   `_Out_writes_to_(s,c)`  
  
     `_Out_writes_bytes_to_(s,c)`  
  
     `_Out_writes_all_(s)`  
  
     `_Out_writes_bytes_all_(s)`  
  
     Ukazatel na pole `s` elementy.  Elementy nemusí být platný v předběžné stavu.  V následující po stavu, prvky, které se mají `c`- tý element musí být platný.  Pokud je znám velikost v bajtech, škálovat `s` a `c` element velikost nebo použití `_bytes_` variant, která je definována jako:  
  
     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`  
  
     Jinými slovy, každý element, který existuje ve vyrovnávací paměti až `s` v předběžné stavu je platný po stavu.  Příklad:  
  
     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`  
  
-   `_Inout_updates_to_(s,c)`  
  
     `_Inout_updates_bytes_to_(s,c)`  
  
     Ukazatel na pole, která je číst a zapisovat funkcí.  Je velikost `s` prvky, které musí být platný v předběžné stavu, a `c` elementy musí být platný v po stavu.  
  
     `_bytes_` Variant dává velikost v bajtech místo elementy. Používejte jenom v případě, že velikost nesmí být vyjádřena jako elementy.  Například `char` využije řetězce `_bytes_` variant pouze v případě, že podobné funkce, která používá `wchar_t` by.  
  
-   `_Inout_updates_z_(s)`  
  
     Ukazatel na pole, které je ukončené hodnotou null a má známé velikost. Elementy až prostřednictvím null ukončení – které musí být přítomen – musí být ve stavu před a po stavu platná.  Hodnota v po stavu se předpokládá, že se liší od hodnoty v předběžné stavu; To zahrnuje umístění ukončení hodnotu null. Pokud je znám velikost v bajtech, škálovat `s` velikostí elementu.  
  
-   `_Out_writes_to_(s,c)`  
  
     `_Out_writes_bytes_to_(s,c)`  
  
     `_Out_writes_all_(s)`  
  
     `_Out_writes_bytes_all_(s)`  
  
     Ukazatel na pole `s` elementy.  Elementy nemusí být platný v předběžné stavu.  V následující po stavu, prvky, které se mají `c`- tý element musí být platný.  Pokud je znám velikost v bajtech, škálovat `s` a `c` element velikost nebo použití `_bytes_` variant, která je definována jako:  
  
     `_Out_writes_to_(_Old_(s), _Old_(s))    _Out_writes_bytes_to_(_Old_(s), _Old_(s))`  
  
     Jinými slovy, každý element, který existuje ve vyrovnávací paměti až `s` v předběžné stavu je platný po stavu.  Příklad:  
  
     `void *memcpy(_Out_writes_bytes_all_(s) char *p1,    _In_reads_bytes_(s) char *p2,    _In_ int s); void * wordcpy(_Out_writes_all_(s) DWORD *p1,     _In_reads_(s) DWORD *p2,    _In_ int s);`  
  
-   `_Inout_updates_to_(s,c)`  
  
     `_Inout_updates_bytes_to_(s,c)`  
  
     Ukazatel na pole, která je číst a zapisovat funkcí.  Je velikost `s` prvky, které musí být platný v předběžné stavu, a `c` elementy musí být platný v po stavu.  
  
     `_bytes_` Variant dává velikost v bajtech místo elementy. Používejte jenom v případě, že velikost nesmí být vyjádřena jako elementy.  Například `char` využije řetězce `_bytes_` variant pouze v případě, že podobné funkce, která používá `wchar_t` by.  
  
-   `_Inout_updates_all_(s)`  
  
     `_Inout_updates_bytes_all_(s)`  
  
     Ukazatel na pole, která je číst a zapisovat funkcí velikosti `s` elementy. Definovaný jako ekvivalentní:  
  
     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`  
  
     Jinými slovy, každý element, který existuje ve vyrovnávací paměti až `s` v předběžné stavu je platný do stavu před a po stavu.  
  
     `_bytes_` Variant dává velikost v bajtech místo elementy. Používejte jenom v případě, že velikost nesmí být vyjádřena jako elementy.  Například `char` využije řetězce `_bytes_` variant pouze v případě, že podobné funkce, která používá `wchar_t` by.  
  
-   `_In_reads_to_ptr_(p)`  
  
     Ukazatel na pole pro kterou výraz `p`  -  `_Curr_` (tedy `p` minus `_Curr_`) je definované standardní příslušný jazyk.  Elementy před `p` musí být platná v předběžné stavu.  
  
-   `_In_reads_to_ptr_z_(p)`  
  
     Ukazatel na pole ukončené hodnotou null, pro kterou výraz `p`  -  `_Curr_` (to znamená, `p` minus `_Curr_`) je definován standardní příslušný jazyk.  Elementy před `p` musí být platná v předběžné stavu.  
  
-   `_Out_writes_to_ptr_(p)`  
  
     Ukazatel na pole pro kterou výraz `p`  -  `_Curr_` (tedy `p` minus `_Curr_`) je definované standardní příslušný jazyk.  Elementy před `p` nemusí být platný v předběžné stavu a musí být v po stavu platná.  
  
-   `_Out_writes_to_ptr_z_(p)`  
  
     Ukazatel na pole ukončené hodnotou null, pro kterou výraz `p`  -  `_Curr_` (to znamená, `p` minus `_Curr_`) je definován standardní příslušný jazyk.  Elementy před `p` nemusí být platný v předběžné stavu a musí být v po stavu platná.  
  
## <a name="optional-pointer-parameters"></a>Ukazatel volitelné parametry  
 Když parametr anotaci ukazatel zahrnuje `_opt_`, označuje, že parametr může mít hodnotu null. Jinak hodnota stejná jako verze, která nezahrnuje anotace provede `_opt_`. Tady je seznam `_opt_` variant anotací parametr ukazatele:  
  
||||  
|-|-|-|  
|`_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`|`_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`|`_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`|  
  
## <a name="output-pointer-parameters"></a>Výstupní parametry ukazatele  
 Výstupní parametry ukazatel vyžadují speciální zápis k rozlišení větší hodnotu null na parametr a odkazoval na umístění.  
  
 **Poznámky a popisy**  
  
-   `_Outptr_`  
  
     Parametr nemůže mít hodnotu null a v po stavu odkazoval na umístění nemůže mít hodnotu null a musí být platné.  
  
-   `_Outptr_opt_`  
  
     Parametr může mít hodnotu null, ale v po stavu odkazoval na umístění nemůže mít hodnotu null a musí být platné.  
  
-   `_Outptr_result_maybenull_`  
  
     Parametr nemůže mít hodnotu null a v po stavu odkazoval na umístění může mít hodnotu null.  
  
-   `_Outptr_opt_result_maybenull_`  
  
     Parametr může mít hodnotu null a v po stavu odkazoval na umístění může mít hodnotu null.  
  
 V následující tabulce jsou další dílčích řetězců vložena do název poznámky pro další kvalifikaci význam anotace.  Jsou různé dílčích řetězců `_z`, `_COM_`, `_buffer_`, `_bytebuffer_`, a `_to_`.  
  
> [!IMPORTANT]
>  Pokud rozhraní, které jsou zadávání poznámek k modelu COM, použijte COM formu tyto poznámky. Nepoužívejte poznámky COM s další typ rozhraní.  
  
 **Poznámky a popisy**  
  
-   `_Outptr_result_z_`  
  
     `_Outptr_opt_result_z_`  
  
     `_Outptr_result_maybenull_z_`  
  
     `_Ouptr_opt_result_maybenull_z_`  
  
     Vrácený ukazatel `_Null_terminated_` poznámky.  
  
-   `_COM_Outptr_`  
  
     `_COM_Outptr_opt_`  
  
     `_COM_Outptr_result_maybenull_`  
  
     `_COM_Outptr_opt_result_maybenull_`  
  
     Vrácený ukazatel má sémantiku COM a proto přináší `_On_failure_` po podmínka, vrácený ukazatel má hodnotu null.  
  
-   `_Outptr_result_buffer_(s)`  
  
     `_Outptr_result_bytebuffer_(s)`  
  
     `_Outptr_opt_result_buffer_(s)`  
  
     `_Outptr_opt_result_bytebuffer_(s)`  
  
     Vrácený ukazatel odkazuje na platný vyrovnávací paměti o velikosti `s` elementy nebo bajtů.  
  
-   `_Outptr_result_buffer_to_(s, c)`  
  
     `_Outptr_result_bytebuffer_to_(s, c)`  
  
     `_Outptr_opt_result_buffer_to_(s,c)`  
  
     `_Outptr_opt_result_bytebuffer_to_(s,c)`  
  
     Vrácený ukazatel ukazuje do vyrovnávací paměti o velikosti `s` elementy nebo bajtů, které první `c` jsou platné.  
  
 Konvence určitých rozhraní se předpokládá, že jsou při selhání vynulován výstupní parametry.  S výjimkou explicitně COM kódu jsou upřednostněny formuláře v následující tabulce.  Pro kód modelu COM použijte odpovídající COM formuláře, které jsou uvedeny v předchozí části.  
  
 **Poznámky a popisy**  
  
-   `_Result_nullonfailure_`  
  
     Upravuje dalších poznámek. Výsledek je nastaven na hodnotu null, pokud se nezdaří funkce.  
  
-   `_Result_zeroonfailure_`  
  
     Upravuje dalších poznámek. Výsledek je nastaven na hodnotu nula, pokud se nezdaří funkce.  
  
-   `_Outptr_result_nullonfailure_`  
  
     Vrácený ukazatel odkazuje na platný vyrovnávací paměti, je-li funkci úspěšné, nebo hodnota null, pokud se nezdaří funkce. Tato anotace je pro parametr volitelné.  
  
-   `_Outptr_opt_result_nullonfailure_`  
  
     Vrácený ukazatel odkazuje na platný vyrovnávací paměti, je-li funkci úspěšné, nebo hodnota null, pokud se nezdaří funkce. Tato anotace je volitelný parametr.  
  
-   `_Outref_result_nullonfailure_`  
  
     Vrácený ukazatel odkazuje na platný vyrovnávací paměti, je-li funkci úspěšné, nebo hodnota null, pokud se nezdaří funkce. Tato anotace je pro parametr odkazu.  
  
## <a name="output-reference-parameters"></a>Výstupní parametry odkaz  
 Běžně se používají parametr odkazu je pro výstupní parametry.  Pro jednoduché výstupní parametry odkaz – například `int&`–`_Out_` poskytuje sémantiku správné.  Ale pokud je výstupní hodnotu ukazatel – například `int *&`– jako ekvivalentní ukazatel poznámky `_Outptr_ int **` neposkytují správné sémantiku.  Chcete-li výstižně express sémantika výstupních odkaz parametrů pro typy ukazatelů, použijte tyto složené poznámky:  
  
 **Poznámky a popisy**  
  
-   `_Outref_`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null.  
  
-   `_Outref_result_maybenull_`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null v po stavu.  
  
-   `_Outref_result_buffer_(s)`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null. Odkazuje na platný vyrovnávací paměti o velikosti `s` elementy.  
  
-   `_Outref_result_bytebuffer_(s)`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null. Odkazuje na platný vyrovnávací paměti o velikosti `s` bajtů.  
  
-   `_Outref_result_buffer_to_(s, c)`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null. Odkazuje na vyrovnávací paměť `s` elementy, které první `c` jsou platné.  
  
-   `_Outref_result_bytebuffer_to_(s, c)`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null. Odkazuje na vyrovnávací paměť `s` bajtů, které první `c` jsou platné.  
  
-   `_Outref_result_buffer_all_(s)`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null. Odkazuje na platný vyrovnávací paměti o velikosti `s` platné prvky.  
  
-   `_Outref_result_bytebuffer_all_(s)`  
  
     Výsledek musí být platná po stavu a nemůže mít hodnotu null. Odkazuje na platný vyrovnávací paměti `s` bajtů platný elementů.  
  
-   `_Outref_result_buffer_maybenull_(s)`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null v po stavu. Odkazuje na platný vyrovnávací paměti o velikosti `s` elementy.  
  
-   `_Outref_result_bytebuffer_maybenull_(s)`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null v po stavu. Odkazuje na platný vyrovnávací paměti o velikosti `s` bajtů.  
  
-   `_Outref_result_buffer_to_maybenull_(s, c)`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null v po stavu. Odkazuje na vyrovnávací paměť `s` elementy, které první `c` jsou platné.  
  
-   `_Outref_result_bytebuffer_to_maybenull_(s,c)`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null ve stavu post. Odkazuje na vyrovnávací paměť `s` bajtů, které první `c` jsou platné.  
  
-   `_Outref_result_buffer_all_maybenull_(s)`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null ve stavu post. Odkazuje na platný vyrovnávací paměti o velikosti `s` platné prvky.  
  
-   `_Outref_result_bytebuffer_all_maybenull_(s)`  
  
     Výsledek musí být ve stavu po platný, ale může mít hodnotu null ve stavu post. Odkazuje na platný vyrovnávací paměti `s` bajtů platný elementů.  
  
## <a name="return-values"></a>Návratové hodnoty  
 Návratová hodnota funkce se podobá `_Out_` parametr, ale je na jiné úrovni de-reference a nemáte vzít v úvahu koncept má ukazatel na výsledek.  Pro následující poznámky návratová hodnota je objekt s poznámkami – skalární hodnota, ukazatel na struktury nebo ukazatel do vyrovnávací paměti. Tyto poznámky mají stejnou sémantiku jako odpovídající `_Out_` poznámky.  
  
|||  
|-|-|  
|`_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`|`_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`|  
  
## <a name="other-common-annotations"></a>Další běžné poznámky  
 **Poznámky a popisy**  
  
-   `_In_range_(low, hi)`  
  
     `_Out_range_(low, hi)`  
  
     `_Ret_range_(low, hi)`  
  
     `_Deref_in_range_(low, hi)`  
  
     `_Deref_out_range_(low, hi)`  
  
     `_Deref_inout_range_(low, hi)`  
  
     `_Field_range_(low, hi)`  
  
     Parametr, pole nebo výsledek je v rozsahu (včetně) z `low` k `hi`.  Ekvivalentní `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` který se použije pro objekt s poznámkami společně s příslušnou podmínek předem stavu nebo po stavu.  
  
    > [!IMPORTANT]
    >  I když se názvy obsahovat "v" a "na", sémantika `_In_` a `_Out_` provést **není** platí pro tyto poznámky.  
  
-   `_Pre_equal_to_(expr)`  
  
     `_Post_equal_to_(expr)`  
  
     S poznámkami hodnota je přesně `expr`.  Ekvivalentní `_Satisfies_(_Curr_ == expr)` který se použije pro objekt s poznámkami společně s příslušnou podmínek předem stavu nebo po stavu.  
  
-   `_Struct_size_bytes_(size)`  
  
     Platí pro deklaraci třídy nebo struktury.  Označuje, že platný objekt daného typu může být větší než deklarovaný typ, počet bajtů, o `size`.  Příklad:  
  
     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`  
  
     Velikost vyrovnávací paměti v bajtech parametru `pM` typu `MyStruct *` je nutno jako:  
  
     `min(pM->nSize, sizeof(MyStruct))`  
  
## <a name="related-resources"></a>Související informační zdroje  
 [Blog týmu analýzy kódu](http://go.microsoft.com/fwlink/?LinkId=251197)  
  
## <a name="see-also"></a>Viz také  
 [Použití poznámek SAL k snížení míry výskytu závad kódu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)   
 [Porozumění SAL](../code-quality/understanding-sal.md)   
 [Zadávání poznámek k chování funkcí](../code-quality/annotating-function-behavior.md)   
 [Zadávání poznámek ke strukturám a třídám](../code-quality/annotating-structs-and-classes.md)   
 [Zadávání poznámek k chování při zamykání](../code-quality/annotating-locking-behavior.md)   
 [Určení, kdy a kde se má poznámka použít](../code-quality/specifying-when-and-where-an-annotation-applies.md)   
 [Vnitřní funkce](../code-quality/intrinsic-functions.md)   
 [Osvědčené postupy a příklady](../code-quality/best-practices-and-examples-sal.md)