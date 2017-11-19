---
title: "Podrobnosti haldy ladění CRT | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debug heap, accessing
- heap functions
- _CRTDBG_CHECK_ALWAYS_DF macro
- _CrtMemDumpStatistics function
- debugging [C++], debug heap
- _CRT_BLOCK macro
- DBGINT.H file
- _CrtMemDumpAllObjectsSince function
- _crtBreakAlloc global variable
- _CrtMemState function
- _CLIENT_BLOCK macro
- _FREE_BLOCK block
- _CrtMemBlockHeader function
- heap state reporting functions
- _CRTDBG_ALLOC_MEM_DF macro
- _CrtSetBreakAlloc function
- memory blocks, allocation types on debug heap
- debugging [C++], CRT debug support
- debug heap, tracking heap allocation requests
- memory allocation, debug heap
- _NORMAL_BLOCK block
- crtBreakAlloc global variable
- _CrtDoForAllClientObjects function
- new operator, using debug heap from C++
- _CrtSetDumpClient function
- debugging [CRT], heap-related problems
- debug heap, solving memory allocation problems
- _CrtMemCheckpoint function
- debug builds, linking to debug heap
- _IGNORE_BLOCK block
- _crtDbgFlag function
- client blocks, specifying subtypes
- memory leaks, tracking
- _CrtSetDbgFlag function
- nBlockUse method
- memory leaks, CRT debug library functions
- _CRTDBG_DELAY_FREE_MEM_DF macro
- allocation request numbers
- _CRTDBG_LEAK_CHECK_DF macro
- debug heap
- memory, debugging
- _CrtReportBlockType function
- _CrtDumpMemoryLeaks function
- _CrtCheckMemory function
- debug heap, CRT
- memory blocks, free
- _BLOCK_TYPE macro
- debug heap, memory blocks
- heap allocation, debug
- debugging memory leaks
- _BLOCK_SUBTYPE macro
- debug heap, using from C++
- _CrtMemDifference function
- heap allocation, tracking requests
- debugging [Visual Studio], debug heap
- delete operator, using debug heap from C++
- blocks, types of on the debug heap
- _CRTDBG_CHECK_CRT_DF macro
- debug heap, reporting functions
ms.assetid: bf78ace6-28e4-4a04-97c6-39e0cdd00ba4
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 947da9ccdbf67a71edfaa122de8861912a9e9596
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="crt-debug-heap-details"></a>Podrobnosti haldy ladění CRT
Toto téma poskytuje podrobný pohled haldy ladění CRT.  
  
##  <a name="BKMK_Contents"></a>Obsah  
 [Přetečení vyrovnávací paměti s haldy ladění najít](#BKMK_Find_buffer_overruns_with_debug_heap)  
  
 [Typy bloků v haldě ladění](#BKMK_Types_of_blocks_on_the_debug_heap)  
  
 [Kontrola haldy integrity a nevrácená paměť](#BKMK_Check_for_heap_integrity_and_memory_leaks)  
  
 [Konfigurace haldě ladění](#BKMK_Configure_the_debug_heap)  
  
 [nové, odstranění a _CLIENT_BLOCKs v jazyce C++ halda ladění](#BKMK_new__delete__and__CLIENT_BLOCKs_in_the_C___debug_heap)  
  
 [Funkce vytváření sestav stavu haldy](#BKMK_Heap_State_Reporting_Functions)  
  
 [Sledování požadavků na přidělení haldy](#BKMK_Track_Heap_Allocation_Requests)  
  
##  <a name="BKMK_Find_buffer_overruns_with_debug_heap"></a>Přetečení vyrovnávací paměti s haldy ladění najít  
 Dva nejčastějších a intractable problémů, které programátory v jazyce jsou přepsání konec přidělené vyrovnávací paměti a nevrácená paměť (selhání po už nejsou potřeba uvolnit přidělení). Halda ladění poskytuje výkonné nástroje pro řešení problémů s přidělováním paměti druhu.  
  
 Ladicí verze funkcí haldy volání použité ve verzi standard nebo základní verze sestavení. Pokud budete požadovat blok paměti, správce haldy ladění přiděluje z základní haldy mírně větší blok paměti, než požadovaná a vrací ukazatel na vaše část tohoto bloku. Předpokládejme například, že vaše aplikace obsahuje volání: `malloc( 10 )`. V sestavení pro vydání [malloc](/cpp/c-runtime-library/reference/malloc) by volání rutiny přidělení haldy základní žádají o přidělení 10 bajtů. V sestavení ladicí verze, ale `malloc` by volání [_malloc_dbg –](/cpp/c-runtime-library/reference/malloc-dbg), které by pak volání rutiny přidělení haldy základní žádají o přidělení 10 bajtů plus přibližně 36 bajtů další paměť. Všechny výsledné bloky paměti v haldě ladění jsou připojeny v jednom odkazovaného seznamu, seřazené podle když byly přiděleny.  
  
 Další paměti přidělené rutiny haldy ladění se používá pro informace o účetnictví pro ukazatele, že bloky paměti ladění odkaz společně a pro malé vyrovnávací paměti na obou stranách vašich dat k zachycení přepíše přidělené oblasti.  
  
 Struktura hlavičky bloku, který se používá k ukládání informací účetnictví haldy ladění je v současné době deklarována takto v DBGINT. Soubor hlaviček H:  
  
```  
typedef struct _CrtMemBlockHeader  
{  
// Pointer to the block allocated just before this one:  
    struct _CrtMemBlockHeader *pBlockHeaderNext;  
// Pointer to the block allocated just after this one:  
    struct _CrtMemBlockHeader *pBlockHeaderPrev;  
    char *szFileName;    // File name  
    int nLine;           // Line number  
    size_t nDataSize;    // Size of user block  
    int nBlockUse;       // Type of block  
    long lRequest;       // Allocation number  
// Buffer just before (lower than) the user's memory:  
    unsigned char gap[nNoMansLandSize];  
} _CrtMemBlockHeader;  
  
/* In an actual memory block in the debug heap,  
 * this structure is followed by:  
 *   unsigned char data[nDataSize];  
 *   unsigned char anotherGap[nNoMansLandSize];  
 */  
```  
  
 `NoMansLand` Vyrovnávací paměti na obou stranách oblasti dat uživatele bloku jsou aktuálně 4 bajtů velikostí a jsou vyplněny hodnoty známé byte používají rutiny haldy ladění k ověření, že omezení bloku paměti uživatele nebyly přepsán. Halda ladění také doplní nové bloky paměti s hodnotou známé. Pokud se rozhodnete zachovat uvolněné bloky v odkazovaného seznamu do haldy, jak je popsáno níže, jsou tyto uvolněné bloky také vyplněny známé hodnotě. Skutečného bajtů hodnoty používané v současné době jsou následující:  
  
 NoMansLand (0xFD)  
 0xFD aktuálně hodnotu "NoMansLand" vyrovnávací paměti na obou stranách množství paměti používané aplikace.  
  
 Uvolněné bloky (0xDD)  
 Uvolněné bloky zachovány nepoužívané v haldě ladění je propojená seznamu, kdy `_CRTDBG_DELAY_FREE_MEM_DF` nastaven příznak jsou aktuálně vyplněny 0xDD.  
  
 Nové objekty (0xCD)  
 Nové objekty jsou vyplněny 0xCD při jejich přidělení.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop")  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Types_of_blocks_on_the_debug_heap"></a>Typy bloků v haldě ladění  
 Každý blok paměti v haldě ladění je přiřazený k jeden z pěti typů přidělení. Tyto typy jsou sledovány a hlášené jinak za účelem zjištění paměti a vytváření sestav stavu. Můžete zadat typ bloku přidělování pomocí přímého volání jedna z funkcí přidělení haldy ladění, jako [_malloc_dbg –](/cpp/c-runtime-library/reference/malloc-dbg). Pět typů bloky paměti v haldě ladění (nastavit **nblockuse –** členem **_crtmemblockheader –** struktura) jsou následující:  
  
 **_NORMAL_BLOCK –**  
 Volání [malloc –](/cpp/c-runtime-library/reference/malloc) nebo [calloc –](/cpp/c-runtime-library/reference/calloc) vytvoří normální blok. Pokud máte v úmyslu používat jenom normální bloky a mít nemusí klientské bloky, můžete chtít definovat [_crtdbg_map_alloc –](/cpp/c-runtime-library/crtdbg-map-alloc), což způsobí, že všechny přidělení haldy volá nejde mapovat na jejich ladění ekvivalenty v sestavení pro ladění. To vám umožní soubor název a řádek číslo informace o každém volání přidělení k uložení v hlavičce odpovídající bloku.  
  
 `_CRT_BLOCK`  
 Bloky paměti přidělené interně mnoho funkcí běhové knihovny jsou označeny jako CRT bloky tak může zpracovat samostatně. V důsledku toho úniku detekce a nemusí mít vliv jiné operace je. Přidělení musí nikdy přidělit, znovu přidělte nebo uvolněte všechny bloky CRT typu.  
  
 `_CLIENT_BLOCK`  
 Aplikace můžete sledovat speciální dané skupiny přidělených pro účely ladění přidělí je jako tento typ bloku paměti, pomocí explicitního volání funkcí haldy ladění. MFC, například přiděluje všechny **objektů CObject** jako klientské bloky; jiné aplikace může mějte na paměti různé objekty klientské bloky. Klientské bloky podtypů lze zadat také pro podrobnější nastavení sledování. Pokud chcete zadat podtypů klientské bloky, posunutí číslo zanechaný 16 bitů a `OR` její `_CLIENT_BLOCK`. Příklad:  
  
```  
#define MYSUBTYPE 4  
freedbg(pbData, _CLIENT_BLOCK|(MYSUBTYPE<<16));  
```  
  
 Funkce háku klient zadané pro vypsání objekty uložené v blocích klienta můžete nainstalovat pomocí [_crtsetdumpclient –](/cpp/c-runtime-library/reference/crtsetdumpclient)a bude se volat potom vždy, když klient blok vypsána funkcí ladění. Navíc [_crtdoforallclientobjects –](/cpp/c-runtime-library/reference/crtdoforallclientobjects) lze použít pro volání dané funkce poskytl aplikace pro každý klientský blok v haldě ladění.  
  
 **_FREE_BLOCK –**  
 Za normálních okolností jsou bloků, které jsou uvolněny odebrat ze seznamu. Zkontroluje, jestli uvolněné paměti není nadále vrácení zapsána do nebo k simulaci nedostatek paměti, můžete zachovat uvolněné bloky na odkazovaného seznamu označeny jako volné a plná známé bajtovou hodnotu (aktuálně 0xDD).  
  
 **_IGNORE_BLOCK –**  
 Je možné vypnout operace haldy ladění pro určitou dobu. Během této doby bloky paměti jsou uchovány v seznamu, ale jsou označené jako ignorovat bloky.  
  
 Chcete-li zjistit, typ a podtyp daného bloku, použijte funkci [_crtreportblocktype –](/cpp/c-runtime-library/reference/crtreportblocktype) a makra **_block_type –** a **_block_subtype –**. Makra jsou definovány (v crtdbg.h) následujícím způsobem:  
  
```  
#define _BLOCK_TYPE(block)          (block & 0xFFFF)  
#define _BLOCK_SUBTYPE(block)       (block >> 16 & 0xFFFF)  
```  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Check_for_heap_integrity_and_memory_leaks"></a>Kontrola haldy integrity a nevrácená paměť  
 Mnoho funkcí haldy ladění musí přistupovat z vašeho kódu. Následující část popisuje některé funkce a jejich použití.  
  
 `_CrtCheckMemory`  
 Můžete použít volání [_crtcheckmemory –](/cpp/c-runtime-library/reference/crtcheckmemory), například pro kontrolu integrity haldy v libovolném bodě. Tato funkce zkontroluje každý blok paměti v haldě, ověřuje, že informace ze záhlaví bloku paměti je platná a potvrdí, že nebyly upraveny vyrovnávací paměti.  
  
 `_CrtSetDbgFlag`  
 Můžete řídit, jak haldy ladění uchovává informace o přidělení pomocí interní příznaku, [_crtdbgflag –](/cpp/c-runtime-library/crtdbgflag), který může číst a nastavit pomocí [_crtsetdbgflag –](/cpp/c-runtime-library/reference/crtsetdbgflag) funkce. Změníte-li tento příznak, můžete určit, aby haldy ladění pro kontrolu nevracení paměti při ukončení programu a nahlásit případné úniky, které jsou zjištěny. Podobně můžete určit, že bloky uvolněné paměti nelze odebrat ze seznamu propojené k simulaci situacích nedostatku paměti. Při kontrole haldě, jsou tyto uvolněné bloky prozkoumá celé zajistit, že nebyly narušen.  
  
 **_Crtdbgflag –** příznak obsahuje následující bitová pole:  
  
|Bitová pole|Výchozí<br /><br /> value|Popis|  
|---------------|-----------------------|-----------------|  
|**_CRTDBG_ALLOC_MEM_DF –**|On|Zapne ladění přidělení. Pokud tento bit je vypnutý, zůstanou přidělení zřetězen dohromady, ale je jejich typ bloku **_ignore_block –**.|  
|**_CRTDBG_DELAY_FREE_MEM_DF –**|Off|Paměť zabrání ve skutečnosti uvolnění, jako simulaci nedostatku paměti. Pokud tato verze je zapnutý, uvolněné bloky udržovaly v haldě ladění odkazovaného seznamu, ale jsou označené jako **_free_block –** a hodnotu, speciální bajtů.|  
|**_CRTDBG_CHECK_ALWAYS_DF –**|Off|Způsobí, že **_crtcheckmemory –** má být volána v každé přidělené a odebrané. To zpomalí spuštění, ale zachytí chyby rychle.|  
|**_CRTDBG_CHECK_CRT_DF –**|Off|Způsobí, že bloky, které jsou označeny jako typ **_crt_block –** mají být zahrnuty do operace zjištění paměti a stavu rozdíl. Pokud tato verze je vypnuto, paměť používaná interně k běhové knihovny se ignoruje během těchto operací.|  
|**_CRTDBG_LEAK_CHECK_DF –**|Off|Způsobí, že kontrola úniku má provést v ukončení programu prostřednictvím volání **_crtdumpmemoryleaks –**. Pokud aplikace se nezdařilo uvolnit všechny paměti, která je přidělena, je vygenerována zprávu o chybách.|  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Configure_the_debug_heap"></a>Konfigurace haldě ladění  
 Všechna volání funkce hald jako `malloc`, `free`, `calloc`, `realloc`, `new`, a `delete` odkazující na ladicí verze těchto funkcí, které fungují v haldě ladění. Pokud jste volné paměti blok, haldy ladění automaticky ověří integritu vyrovnávací paměti na obou stranách vaší přidělené oblasti a vydá zprávu o chybách v případě, že došlo k přepsání.  
  
 **Použití haldy ladění**  
  
-   Odkaz sestavení ladicí verze vaší aplikace s verzí ladicí běhové knihovny jazyka C.  
  
 **Vytvoření nového stavu pro příznak a změnit jeden nebo více _crtdbgflag – bitová pole**  
  
1.  Volání `_CrtSetDbgFlag` s `newFlag` parametr nastaven na `_CRTDBG_REPORT_FLAG` (získat aktuální `_crtDbgFlag` stavu) a uložit vrácená hodnota v dočasné proměnné.  
  
2.  Zapnout všechny služby bits pomocí `OR`- ing (bitové &#124; symbol) dočasné proměnné s odpovídající bitovou masku (určená v kódu aplikace pomocí manifestu konstanty).  
  
3.  Vypnout službu bits podle `AND`- ing (bitové & symbol) proměnnou pomocí `NOT` (bitové ~ symbol) z příslušné bitovou masku.  
  
4.  Volání `_CrtSetDbgFlag` s `newFlag` nastavit parametr s hodnotou uloženou v dočasné proměnné vytvořit nový stav pro `_crtDbgFlag`.  
  
 Například následující řádky kódu zapnout automatické úniku detekce a vypnout nastavení kontrola bloky typu `_CRT_BLOCK`:  
  
```  
// Get current flag  
int tmpFlag = _CrtSetDbgFlag( _CRTDBG_REPORT_FLAG );  
  
// Turn on leak-checking bit.  
tmpFlag |= _CRTDBG_LEAK_CHECK_DF;  
  
// Turn off CRT block checking bit.  
tmpFlag &= ~_CRTDBG_CHECK_CRT_DF;  
  
// Set flag to the new value.  
_CrtSetDbgFlag( tmpFlag );  
```  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_new__delete__and__CLIENT_BLOCKs_in_the_C___debug_heap"></a>nové, odstranění a _CLIENT_BLOCKs v jazyce C++ halda ladění  
 Ladicí verze běhové knihovny jazyka C obsahovat ladicí verze C++ `new` a `delete` operátory. Pokud použijete `_CLIENT_BLOCK` přidělení typu, musí volat ladicí verze `new` operátor přímo nebo maker, které nahrazují `new` operátor v režimu ladění, jak je znázorněno v následujícím příkladu:  
  
```  
/* MyDbgNew.h  
 Defines global operator new to allocate from  
 client blocks  
*/  
  
#ifdef _DEBUG  
   #define DEBUG_CLIENTBLOCK   new( _CLIENT_BLOCK, __FILE__, __LINE__)  
#else  
   #define DEBUG_CLIENTBLOCK  
#endif // _DEBUG  
  
/* MyApp.cpp  
        Use a default workspace for a Console Application to  
 *      build a Debug version of this code  
*/  
  
#include "crtdbg.h"  
#include "mydbgnew.h"  
  
#ifdef _DEBUG  
#define new DEBUG_CLIENTBLOCK  
#endif  
  
int main( )   {  
    char *p1;  
    p1 =  new char[40];  
    _CrtMemDumpAllObjectsSince( NULL );  
}  
```  
  
 Ladicí verze `delete` operátor funguje s blokem všechny typy a nevyžaduje žádné změny v programu při kompilaci prodejní verzi.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Heap_State_Reporting_Functions"></a>Funkce vytváření sestav stavu haldy  
 **_Crtmemstate –**  
  
 K zachycení snímku souhrnu stavu haldy v daném okamžiku, použijte _crtmemstate – struktura definované v CRTDBG. V:  
  
```  
typedef struct _CrtMemState  
{  
    // Pointer to the most recently allocated block:  
    struct _CrtMemBlockHeader * pBlockHeader;  
    // A counter for each of the 5 types of block:  
    size_t lCounts[_MAX_BLOCKS];  
    // Total bytes allocated in each block type:  
    size_t lSizes[_MAX_BLOCKS];  
    // The most bytes allocated at a time up to now:  
    size_t lHighWaterCount;  
    // The total bytes allocated at present:  
    size_t lTotalCount;  
} _CrtMemState;  
```  
  
 Tato struktura uloží ukazatel na první (většina přidělené nedávno) blok v haldě ladění odkazovaného seznamu. Potom v dvěma poli zaznamenává kolik každého typu paměti blokovat (_normal_block –, `_CLIENT_BLOCK`, _free_block –, a tak dále) jsou v seznamu a počet bajtů přidělených v každý typ bloku. Nakonec zaznamenává největší počet bajtů přidělených v haldě jako celek až tento bod a počet bajtů, které jsou aktuálně přidělené.  
  
 **Jiné funkce vytváření sestav CRT**  
  
 Následující funkce hlášení o stavu a velikosti halda a využít tyto informace pomáhají zjišťovat nevracení paměti a jiné problémy.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[_Crtmemcheckpoint –](/cpp/c-runtime-library/reference/crtmemcheckpoint)|Uloží snímek haldy v **_crtmemstate –** struktura poskytl aplikace.|  
|[_Crtmemdifference –](/cpp/c-runtime-library/reference/crtmemdifference)|Porovná dva struktury stavu paměti, uloží rozdíl mezi nimi ve struktuře třetí stav a vrátí hodnotu TRUE, pokud se dva stavy liší.|  
|[_Crtmemdumpstatistics –](/cpp/c-runtime-library/reference/crtmemdumpstatistics)|Výpisy paměti danou **_crtmemstate –** struktura. Struktura může obsahovat snímek stavu haldy ladění v daném okamžiku nebo rozdíl mezi dvěma snímky.|  
|[_Crtmemdumpallobjectssince –](/cpp/c-runtime-library/reference/crtmemdumpallobjectssince)|Vypíše informace o všech objektech přidělené od doby pořízení snímku dané, haldy nebo od začátku spuštění. Pokaždé, když ho výpisy paměti **_client_block –** bloku, zavolá funkce háku poskytl aplikace, pokud jeden byl nainstalován pomocí **_crtsetdumpclient –**.|  
|[_Crtdumpmemoryleaks –](/cpp/c-runtime-library/reference/crtdumpmemoryleaks)|Určuje, zda všechny paměti nevracení došlo k od spuštění tohoto programu a pokud ano, vypíše všechny přidělené objekty. Pokaždé, když **_crtdumpmemoryleaks –** výpisy paměti **_client_block –** bloku, zavolá funkce háku poskytl aplikace, pokud jeden byl nainstalován pomocí **_crtsetdumpclient –**.|  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
##  <a name="BKMK_Track_Heap_Allocation_Requests"></a>Sledování požadavků na přidělení haldy  
 I když přesným rozpoznáním číslo zdrojového souboru název a řádek, na což vyhodnocení nebo generování sestav makro provede je často velmi užitečné při hledání příčinu problému, stejné není jako mohou být true funkcí přidělení haldy. Zatímco makra lze vložit v mnoha odpovídající bodů ve stromu aplikace logiky, přidělení často ukryty ve speciální rutiny, která je volána z mnoha různých místech v mnoha různých časech. Otázka se obvykle není co řádek kódu provedené chybný přidělení, ale spíš které jedna z tisíců přidělených provedené tohoto řádku kódu byla chybná a proč.  
  
 **Počty požadavků na přidělení jedinečné a _crtbreakalloc –**  
  
 Nejjednodušší způsob, jak identifikovat volání přidělení haldy konkrétní, které se chybný je využít výhod číslo žádost o přidělení jedinečné u každého bloku v haldě ladění. Při hlášení informace o blok jedna z funkcí výpisu, je toto číslo žádost o přidělení uzavřené do složených závorek (například "{36}").  
  
 Jakmile znáte číslo žádost o přidělení nesprávně přidělené bloku, můžete předat toto číslo na [_crtsetbreakalloc –](/cpp/c-runtime-library/reference/crtsetbreakalloc) vytvořit zarážky. Provádění rozbije těsně před přidělování bloku a můžete zpětný krok určit, jaké rutiny je zodpovědná za chybný volání. Abyste se vyhnuli nutnosti rekompilace, můžete provést nastavením samé v ladicím programu **_crtbreakalloc –** počtu žádost o přidělení vás zajímá.  
  
 **Vytvoření ladění verzí vaše rutiny přidělení**  
  
 Trochu složitější přístupu je vytvoření ladicí verze vlastní rutiny přidělení, srovnatelná **_dbg** verzích [funkce přidělení haldy](../debugger/debug-versions-of-heap-allocation-functions.md). Potom můžete předat zdrojový soubor a řádku číslo argumenty prostřednictvím na základní rutiny přidělení haldy a okamžitě bude moci zobrazit, kde chybný přidělení vytvořena.  
  
 Předpokládejme například, že vaše aplikace obsahuje běžně používané rutinu, která je podobný následujícímu:  
  
```  
int addNewRecord(struct RecStruct * prevRecord,  
                 int recType, int recAccess)  
{  
    // ...code omitted through actual allocation...   
    if ((newRec = malloc(recSize)) == NULL)  
    // ... rest of routine omitted too ...   
}  
```  
  
 V záhlaví souboru můžete přidat například následující kód:  
  
```  
#ifdef _DEBUG  
#define  addNewRecord(p, t, a) \  
            addNewRecord(p, t, a, __FILE__, __LINE__)  
#endif  
```  
  
 Dále můžete změnit přidělení v rutině vaší vytvoření záznamu následujícím způsobem:  
  
```  
int addNewRecord(struct RecStruct *prevRecord,  
                int recType, int recAccess  
#ifdef _DEBUG  
               , const char *srcFile, int srcLine  
#endif  
    )  
{  
    /* ... code omitted through actual allocation ... */  
    if ((newRec = _malloc_dbg(recSize, _NORMAL_BLOCK,  
            srcFile, scrLine)) == NULL)  
    /* ... rest of routine omitted too ... */  
}  
```  
  
 Nyní číslo zdrojového souboru název a řádek, kde `addNewRecord` byla volána se uloží v každém výsledné bloku přidělené v haldě ladění a bude hlášena, když je zkontrolován tomto bloku.  
  
 ![Zpět na začátek](../debugger/media/pcs_backtotop.png "PCS_BackToTop") [obsah](#BKMK_Contents)  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu](../debugger/debugging-native-code.md)