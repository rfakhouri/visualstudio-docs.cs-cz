---
title: Hledání nevrácené paměti pomocí knihovny CRT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- breakpoints, on memory allocation
- _CrtMemState
- _CrtMemCheckpoint
- memory leaks
- _CrtMemDifference
- memory leaks, detecting and isolating
- _CrtDumpMemoryLeaks
- _CrtSetBreakAlloc
- _crtBreakAlloc
- _CrtSetReportMode
- memory, debugging
- _CrtMemDumpStatistics
- debugging memory leaks
- _CRTDBG_MAP_ALLOC
- _CrtSetDbgFlag
ms.assetid: cf6dc7a6-cd12-4283-b1b6-ea53915f7ed1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c02fea4639d130840f3f5dbbd9e77693c676d304
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="finding-memory-leaks-using-the-crt-library"></a>Hledání nevrácené paměti pomocí knihovny CRT
Nevracení paměti definován jako selhání se správně zrušit přidělení paměti, které již bylo přiděleno, patří mezi nejvíce jemně a pevné zjištění chyby v aplikací C/C++. Nevracení paměti nemusí být si všimli v první, ale v čase, progresivní paměť způsobit příznaky rozsahu snížený výkon k selhání, když je aplikace spuštěná nedostatek paměti. Horší unikající aplikace, která používá všechny dostupnou paměť může způsobit jiná aplikace došlo k chybě, vytváření nejasnostem, která je zodpovědná aplikace. Nevracení paměti neškodné může být i zdánlivě symptomatických z jiných problémů, které by měly být opraveny.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ladicího programu a knihoven C Run-Time (CRT) poskytují prostředky pro zjišťování a identifikaci nevracení paměti.  
  
## <a name="enabling-memory-leak-detection"></a>Povolení zjišťování nevracení paměti  
 Funkce haldy ladění mezi primární nástroje pro zjišťování paměti, že jsou nevracení ladicího programu a knihoven C Run-Time (CRT).  
  
 Pokud chcete povolit funkce haldy ladění, vložte následující příkazy v programu:  
  
```  
#define _CRTDBG_MAP_ALLOC  
#include <stdlib.h>  
#include <crtdbg.h>  
```  
  
 Pro funkce CRT fungovala správně `#include` příkazy musí postupujte podle zde uvedeném pořadí.  
  
 Včetně crtdbg.h mapy `malloc` a [volné](/cpp/c-runtime-library/reference/free) funkce ladicí verze, [_malloc_dbg –](/cpp/c-runtime-library/reference/malloc-dbg) a `free`, který sleduje přidělování paměti a zrušení přidělení. Toto mapování nastane jenom u sestavení ladicí verze, které mají `_DEBUG`. Verze sestavení používat běžném provozu `malloc` a `free` funkce.  
  
 `#define` Příkaz mapuje základní verze funkcí CRT haldy odpovídající ladicí verzi. V případě vynechání `#define` příkaz, bude méně podrobný stav nevracení paměti.  
  
 Po povolení funkce haldy ladění pomocí těchto příkazů, můžete umístit volání `_CrtDumpMemoryLeaks` před bod ukončení aplikace zobrazíte sestavu nevrácená paměť systému při ukončení aplikace:  
  
```  
_CrtDumpMemoryLeaks();  
```  
  
 Pokud aplikace obsahuje více ukončí, není nutné ručně umístit volání [_crtdumpmemoryleaks –](/cpp/c-runtime-library/reference/crtdumpmemoryleaks) v každém bodě ukončení. Volání `_CrtSetDbgFlag` na začátku aplikace způsobí automatické volání `_CrtDumpMemoryLeaks` na každé ukončení bodu. Musíte nastavit dvě bitových polí znázorněno zde:  
  
```  
_CrtSetDbgFlag ( _CRTDBG_ALLOC_MEM_DF | _CRTDBG_LEAK_CHECK_DF );  
```  
  
 Ve výchozím nastavení `_CrtDumpMemoryLeaks` výstupy sestavu nevrácená paměť systému, aby se **ladění** podokně **výstup** okno. Můžete použít `_CrtSetReportMode` přesměrování sestavy do jiného umístění.  
  
 Pokud chcete použít knihovnu, knihovny může resetovat výstup do jiného umístění. V takovém případě můžete nastavit výstupní umístění zpět **výstup** okno, jak je vidět tady:  
  
```  
_CrtSetReportMode( _CRT_ERROR, _CRTDBG_MODE_DEBUG );  
```  
  
## <a name="interpreting-the-memory-leak-report"></a>Interpretace sestavy nevracení paměti  
 Pokud vaše aplikace nedefinuje `_CRTDBG_MAP_ALLOC`, [_crtdumpmemoryleaks –](/cpp/c-runtime-library/reference/crtdumpmemoryleaks) zobrazí zprávu o nevracení paměti, že vypadá podobně jako tento:  
  
```  
Detected memory leaks!  
Dumping objects ->  
{18} normal block at 0x00780E80, 64 bytes long.  
 Data: <                > CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD  
Object dump complete.  
```  
  
 Pokud vaše aplikace definuje `_CRTDBG_MAP_ALLOC`, nevrácená paměť systému sestava vypadá takto:  
  
```  
Detected memory leaks!  
Dumping objects ->  
c:\users\username\documents\projects\leaktest\leaktest.cpp(20) : {18}   
normal block at 0x00780E80, 64 bytes long.  
 Data: <                > CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD CD  
Object dump complete.  
```  
  
 Rozdílem je, že druhá sestava zobrazuje název souboru a číslo řádku kde je nevrácená paměť nejprve přiděleny.  
  
 Jestli definujete `_CRTDBG_MAP_ALLOC` nebo Ne, sestava bude výrobce OEM nevrácená paměť systému zobrazovat následující informace:  
  
-   Číslo přidělení paměti, což je `18` v tomto příkladu  
  
-   [Blok typem](http://msdn.microsoft.com/en-us/e2f42faf-0687-49e7-aa1f-916038354f97), což je `normal` v tomto příkladu.  
  
-   Umístění hexadecimální paměti, což je `0x00780E80` v tomto příkladu.  
  
-   Velikost bloku `64 bytes` v tomto příkladu.  
  
-   První 16 bajtů dat v bloku, v šestnáctkovém formátu.  
  
 Nevrácená paměť systému Sestava identifikuje bloku paměti jako normální, klienta nebo CRT. A *normální bloku* je obyčejnou paměti přidělené vašeho programu. A *klientský blok* , je zvláštním typem bloku paměti používané MFC programy pro objekty, které vyžadují destruktor. MFC `new` operátor vytvoří blok normální nebo blok klienta podle potřeby vytváří objektu. A *CRT bloku* je přidělena knihovny CRT pro vlastní použití. Knihovna CRT zpracovává navrácení pro tyto bloky. Je tedy nepravděpodobné, že zobrazí se v sestavě nevracení paměti Pokud něco výrazně je nesprávný, například knihovny CRT je poškozený.  
  
 Existují dva typy bloky paměti, které se nikdy zobrazují v sestavách nevrácená paměť systému. A *volné bloku* je paměť, která byla vydána. To znamená, že není úniku podle definice. *Ignorovat bloku* je paměti, které jste označili vyloučit ze sestavy nevrácená paměť systému explicitně.  
  
 Tyto postupy fungovat v paměti přidělené pomocí standardní CRT `malloc` funkce. Pokud váš program přidělí paměť pomocí C++ `new` operátor, ale se zobrazí pouze soubor a řádku číslo kde implementace globální `operator new` volání `_malloc_dbg` v sestavě nevrácená paměť systému. Vzhledem k tomu, že chování není velmi užitečná, můžete změnit její sestavy na řádku, které k přidělení pomocí makro, které vypadá takto: 
 
```C++  
#ifdef _DEBUG
    #define DBG_NEW new ( _NORMAL_BLOCK , __FILE__ , __LINE__ )
    // Replace _NORMAL_BLOCK with _CLIENT_BLOCK if you want the
    // allocations to be of _CLIENT_BLOCK type
#else
    #define DBG_NEW new
#endif
```  
  
Teď můžete nahradit `new` operátor pomocí `DBG_NEW` makro ve vašem kódu. V sestavení pro ladění, tato služba využívá přetížení globální `operator new` dalších parametrů pro typ bloku, souboru a číslo řádku, která má. Toto přetížení `new` volání `_malloc_dbg` k zaznamenání doplňující informace. Při použití `DBG_NEW`, nevrácená paměť systému sestavy zobrazit číslo a název souboru a řádku, které byly přiděleny uniklé objekty. V sestavení pro maloobchodní použije výchozí `new`. (Není doporučeno vytvořit makro preprocesoru s názvem `new`, nebo jakékoli jiné klíčové slovo jazyka.) Tady je příklad techniky:  
  
```C++  
// debug_new.cpp
// compile by using: cl /EHsc /W4 /D_DEBUG /MDd debug_new.cpp
#define _CRTDBG_MAP_ALLOC
#include <cstdlib>
#include <crtdbg.h>

#ifdef _DEBUG
    #define DBG_NEW new ( _NORMAL_BLOCK , __FILE__ , __LINE__ )
    // Replace _NORMAL_BLOCK with _CLIENT_BLOCK if you want the
    // allocations to be of _CLIENT_BLOCK type
#else
    #define DBG_NEW new
#endif

struct Pod {
    int x;
};

void main() {
    Pod* pPod = DBG_NEW Pod;
    pPod = DBG_NEW Pod; // Oops, leaked the original pPod!
    delete pPod;

    _CrtDumpMemoryLeaks();
}
```  
  
Když spustíte tento kód v ladicím programu v sadě Visual Studio, volání `_CrtDumpMemoryLeaks` generuje sestavy v **výstup** okno, které vypadá podobně jako tento:  
  
```Output  
Detected memory leaks!
Dumping objects ->
c:\users\username\documents\projects\debug_new\debug_new.cpp(20) : {75}
 normal block at 0x0098B8C8, 4 bytes long.
 Data: <    > CD CD CD CD 
Object dump complete.
```  
  
Znamená to, že bylo na řádku 20 debug_new.cpp uniklé přidělení.  
  
## <a name="setting-breakpoints-on-a-memory-allocation-number"></a>Nastavení zarážek na několika přidělení paměti  
 Číslo přidělení paměti zjistíte, kdy byl přidělen blok nevrácené paměti. Blok s číslem přidělení paměti 18, například je 18 bloku paměti přidělené během spuštění aplikace. Sestava CRT spočítá všechny přidělení bloků paměti při spuštění. To zahrnuje přidělení knihovny CRT a další knihovny například MFC. Blok s počtem přidělení paměti 18 proto nemusí být 18 bloku paměti přidělené vašeho kódu. Obvykle se nebude.  
  
 Číslo přidělení můžete nastavit zarážky přidělení paměti.  
  
#### <a name="to-set-a-memory-allocation-breakpoint-using-the-watch-window"></a>Pro nastavení zarážky přidělení paměti pomocí okna kukátka  
  
1.  Nastavit zarážky téměř spuštění vaší aplikace a pak spusťte aplikaci.  
  
2.  Pokud aplikace dělí u zarážky, **sledovat** okno.  
  
3.  V **sledovat** zadejte `_crtBreakAlloc` v v **název** sloupce.  
  
     Pokud používáte vícevláknové knihovny DLL verze knihovny CRT (/MD možnost), zahrnují kontext operátor: `{,,ucrtbased.dll}_crtBreakAlloc`  
  
4.  Stiskněte klávesu **vrátit**.  
  
     Ladicí program vyhodnocuje volání a umístí výsledek v **hodnotu** sloupce. Tato hodnota bude mít hodnotu -1, pokud jste nenastavili žádné zarážky na přidělení paměti.  
  
5.  V **hodnotu** sloupci a nahraďte hodnotu zobrazí s přidělení počet přidělení paměti, které chcete rozdělit.  
  
 Po nastavení boru přerušení na několika přidělení paměti, můžete pokračovat k ladění. Dávejte pozor, ke spuštění programu za stejných podmínek jako předchozí spustit tak, aby pořadí přidělení paměti se nemění. Pokud váš program dělí na přidělení paměti zadaný, můžete použít **zásobníkem volání** okno a dalších ladicího programu k určení podmínek, za kterých byl přidělen do paměti. Pak můžete pokračovat v provádění, abyste viděli, co se stane, že k objektu a zjistit, proč není navrácena správně.  
  
 Nastavení zarážek dat v objektu může být také užitečné. Další informace najdete v tématu [pomocí zarážek](../debugger/using-breakpoints.md).  
  
 Můžete také nastavit zarážky přidělení paměti v kódu. Toto lze provést dvěma způsoby:  
  
```  
_crtBreakAlloc = 18;  
```  
  
 nebo:  
  
```  
_CrtSetBreakAlloc(18);  
```  
  
## <a name="comparing-memory-states"></a>Porovnání stavy paměti  
 Jiná metoda vyhledání nevracení paměti zahrnuje pořizování snímků stav paměti aplikace na klíčové body. Pořízení snímku je stav paměti k danému bodu v aplikaci, vytvořte **_crtmemstate –** struktury a předejte jej `_CrtMemCheckpoint` funkce. Tato funkce vyplní struktura s snímek aktuální stav paměti:  
  
```  
_CrtMemState s1;  
_CrtMemCheckpoint( &s1 );  
  
```  
  
 `_CrtMemCheckpoint` vyplní struktura s snímek aktuální stav paměti.  
  
 K vypsání obsah **_crtmemstate –** struktury, předat k strukturu `_ CrtMemDumpStatistics` funkce:  
  
```  
_CrtMemDumpStatistics( &s1 );  
  
```  
  
 `_ CrtMemDumpStatistics` výstupy výpis stavu paměti, které vypadá takto:  
  
```  
0 bytes in 0 Free Blocks.  
0 bytes in 0 Normal Blocks.  
3071 bytes in 16 CRT Blocks.  
0 bytes in 0 Ignore Blocks.  
0 bytes in 0 Client Blocks.  
Largest number used: 3071 bytes.  
Total allocations: 3764 bytes.  
  
```  
  
 Chcete-li zjistit, zda nevrácené paměti došlo k chybě v části kódu, můžete pořízení snímků je stav paměti před a po části a pak použijte `_ CrtMemDifference` k porovnání dvou stavů:  
  
```  
_CrtMemCheckpoint( &s1 );  
// memory allocations take place here  
_CrtMemCheckpoint( &s2 );  
  
if ( _CrtMemDifference( &s3, &s1, &s2) )  
   _CrtMemDumpStatistics( &s3 );  
```  
  
 `_CrtMemDifference` porovná stavy paměti `s1` a `s2` a vrátí výsledek v (`s3`) tedy rozdíl `s1` a `s2`.  
  
 Jeden postup pro vyhledání nevrácené paměti začne tím, že umístíte `_CrtMemCheckpoint` volání na začátku a konci aplikace, pak pomocí `_CrtMemDifference` porovnání výsledků. Pokud `_CrtMemDifference` ukazuje nevrácenou pamětí, můžete přidat více `_CrtMemCheckpoint` volání k rozdělení váš program pomocí binární vyhledávání, dokud zdroj nevracení paměti mají izolované.  
  
## <a name="false-positives"></a>Falešně pozitivních zjištění  
 V některých případech `_CrtDumpMemoryLeaks` můžete udělit false indikace nevracení paměti. Tato situace může nastat, pokud používáte knihovnu označí interních přidělování _NORMAL_BLOCKs místo `_CRT_BLOCK`s nebo `_CLIENT_BLOCK`s. V takovém případě `_CrtDumpMemoryLeaks` se nepodařilo zjistit rozdíl mezi uživatele přidělení a přidělení interní knihovna. Pokud globální destruktory pro přidělení knihovny spustit po bodě, kde volání `_CrtDumpMemoryLeaks`, každý knihovny interních přidělování se hlásí jako nevrácená paměť systému. Starší verze standardní šablona knihovny, dříve než Visual Studio .NET způsobila `_CrtDumpMemoryLeaks` nahlásit takové false byl opraven pozitivních, ale v posledních verzích.  
  
## <a name="see-also"></a>Viz také  
 [Podrobnosti haldy ladění CRT](../debugger/crt-debug-heap-details.md)   
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
