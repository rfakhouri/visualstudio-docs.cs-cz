---
title: "Techniky ladění MFC | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AfxEnableMemoryTracking
- CMemoryState
- delayFreeMemDF
- checkAlwaysMemDF
- vs.debug.mfc
- vs.debug.objects.dump
- vs.debug.memory.dump
- allocMemDF
- afxMemDF
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugging [MFC]
ms.assetid: b154fc31-5e90-4734-8cbd-58dd9fe1f750
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 274cd182fa3b9eab23c151a4143c935c24f68fea
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="mfc-debugging-techniques"></a>Techniky ladění MFC
Pokud ladíte aplikaci MFC, může být užitečné tyto techniky ladění.  
  
##  <a name="BKMK_In_this_topic"></a>V tomto tématu  
 [Afxdebugbreak –](#BKMK_AfxDebugBreak)  
  
 [Makro trasování](#BKMK_The_TRACE_macro)  
  
 [Zjišťování nevracení paměti v prostředí MFC](#BKMK_Memory_leak_detection_in_MFC)  
  
-   [Přidělení paměti pro sledování](#BKMK_Tracking_memory_allocations)  
  
-   [Povolení diagnostiky paměti](#BKMK_Enabling_memory_diagnostics)  
  
-   [Pořizování snímků paměti](#BKMK_Taking_memory_snapshots)  
  
-   [Zobrazení statistiky paměti](#BKMK_Viewing_memory_statistics)  
  
-   [Vezme objekt výpisy paměti](#BKMK_Taking_object_dumps)  
  
    -   [Interpretace paměti výpisy paměti](#BKMK_Interpreting_memory_dumps)  
  
    -   [Přizpůsobení objektu výpisy paměti](#BKMK_Customizing_object_dumps)  
  
     [Zmenšení velikosti sestavení pro ladění MFC](#BKMK_Reducing_the_size_of_an_MFC_Debug_build)  
  
    -   [Vytvoření aplikace MFC s informace o ladění pro vybrané moduly](#BKMK_Building_an_MFC_app_with_debug_information_for_selected_modules)  
  
##  <a name="BKMK_AfxDebugBreak"></a>Afxdebugbreak –  
 Knihovna MFC poskytuje speciální [afxdebugbreak –](http://msdn.microsoft.com/Library/c4cd79b9-9327-4db5-a9d6-c4004a92aa30) funkce pro pevně kódováno zarážky ve zdrojovém kódu:  
  
```  
AfxDebugBreak( );  
  
```  
  
 Na platformách Intel `AfxDebugBreak` vytváří následující kód, který zalomení ve zdroji code místo jádra kódu:  
  
```  
_asm int 3  
```  
  
 Na jiných platformách `AfxDebugBreak` jenom volá `DebugBreak`.  
  
 Nezapomeňte odebrat `AfxDebugBreak` příkazy při vytváření verze sestavení nebo použijte `#ifdef _DEBUG` k jejich uzavřete.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_The_TRACE_macro"></a>Makro trasování  
 Chcete-li zobrazit zprávy z vaší aplikace v ladicím programu [výstup – okno](../ide/reference/output-window.md), můžete použít [ATLTRACE](http://msdn.microsoft.com/Library/c796baa5-e2b9-4814-a27d-d800590b102e) makro nebo knihovny MFC [trasování](http://msdn.microsoft.com/Library/7b6f42d8-b55a-4bba-ab04-c46251778e6f) – makro. Jako [kontrolní výrazy](../debugger/c-cpp-assertions.md), makra trasování jsou aktivní pouze ve verzi ladění vašeho programu a při zkompilovat ve verzi zmizí.  
  
 Následující příklady ukazují způsoby, kterými můžete **trasování** makro. Jako `printf`, **trasování** makro dokáže zpracovat počet argumentů.  
  
```  
int x = 1;  
int y = 16;  
float z = 32.0;  
TRACE( "This is a TRACE statement\n" );  
  
TRACE( "The value of x is %d\n", x );  
  
TRACE( "x = %d and y = %d\n", x, y );  
  
TRACE( "x = %d and y = %x and z = %f\n", x, y, z );  
```  
  
 Makro trasování správně zpracovává char * i wchar_t\* parametry. Následující příklady ukazují použití trasování makro společně s různé typy parametrů řetězce.  
  
```  
TRACE( "This is a test of the TRACE macro that uses an ANSI string: %s %d\n", "The number is:", 2);  
  
TRACE( L"This is a test of the TRACE macro that uses a UNICODE string: %s %d\n", L"The number is:", 2);  
  
TRACE( _T("This is a test of the TRACE macro that uses a TCHAR string: %s %d\n"), _T("The number is:"), 2);  
  
```  
  
 Další informace o **trasování** makro, najdete v části [diagnostické služby](/cpp/mfc/reference/diagnostic-services).  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Memory_leak_detection_in_MFC"></a>Zjišťování nevracení paměti v prostředí MFC  
 Knihovna MFC poskytuje třídy a funkce pro zjišťování paměti, která je přidělena, ale nikdy navrácena.  
  
###  <a name="BKMK_Tracking_memory_allocations"></a>Přidělení paměti pro sledování  
 V prostředí MFC, můžete použít makro [debug_new –](http://msdn.microsoft.com/Library/9b379344-4093-4bec-a3eb-e0d8a63ada9d) místě **nové** nevracení operátor pro usnadnění vyhledání paměti. V ladicí verze vašeho programu `DEBUG_NEW` uchovává informace o číslo, pro každý objekt, který přiděluje název a řádek souboru. Když zkompilujete verzi vašeho programu `DEBUG_NEW` přeloží na jednoduchý **nové** operaci bez název a řádek číslo informací o souboru. Tedy platit žádné snížení rychlosti ve verzi vašeho programu.  
  
 Pokud nechcete přepsání celý váš program používat `DEBUG_NEW` místě **nové**, toto makro můžete definovat ve zdrojových souborech:  
  
```  
#define new DEBUG_NEW  
```  
  
 Když to uděláte [objekt výpisu](#BKMK_Taking_object_dumps), každého objektu je přiřazen `DEBUG_NEW` se zobrazí číslo souborové služby a řádku, kde byl přidělen, abyste mohli přesně určit zdroje nevracení paměti.  
  
 Ladicí verze rozhraní MFC Framework používá `DEBUG_NEW` automaticky, ale nemá kódu. Pokud chcete, aby výhody `DEBUG_NEW`, je nutné použít `DEBUG_NEW` explicitně nebo **#define nové** jako v příkladu nahoře.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Enabling_memory_diagnostics"></a>Povolení diagnostiky paměti  
 Než budete moct použít zařízení diagnostiky paměti, je nutné povolit diagnostické trasování.  
  
 **K povolení nebo zakázání diagnostiky paměti**  
  
-   Volání globální funkce [afxenablememorytracking –](http://msdn.microsoft.com/Library/0a40e0c4-855d-46e2-9577-a8f2346f47db) k povolení nebo zakázání přidělení paměti diagnostiky. Protože Diagnostika paměti jsou ve výchozím v knihovně ladění, obvykle použijete tuto funkci, chcete-li je dočasně vypnout, což zvyšuje rychlost provádění programu a snižuje výstup diagnostiky.  
  
 **Chcete-li vybrat konkrétní paměti diagnostické funkce s afxmemdf –**  
  
-   Pokud chcete přesnější kontrolu nad diagnostické funkce paměti, můžete selektivně zapnout diagnostické funkce jednotlivých paměti zapnout a vypnout nastavením hodnoty globální proměnné MFC [afxmemdf –](http://msdn.microsoft.com/Library/cf117501-5446-4fce-81b3-f7194bc95086). Tato proměnná může mít následující hodnoty podle specifikace Výčtový typ **afxmemdf –**.  
  
    |Hodnota|Popis|  
    |-----------|-----------------|  
    |**allocmemdf –**|Zapněte přidělení diagnostiky paměti (výchozí).|  
    |**delayfreememdf –**|Zpoždění při volání metody uvolnění paměti `delete` nebo `free` až do konce programu. To způsobí, že je váš program přidělit maximální množství paměti.|  
    |**checkalwaysmemdf –**|Volání [afxcheckmemory –](http://msdn.microsoft.com/Library/4644da71-7d14-41dc-adc0-ee9558fd7a28) pokaždé, když je paměti přidělené nebo vydání.|  
  
     Tyto hodnoty můžete použít v kombinaci provedením operace logické OR, jak je vidět tady:  
  
    ```C++  
    afxMemDF = allocMemDF | delayFreeMemDF | checkAlwaysMemDF;  
    ```  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Taking_memory_snapshots"></a>Pořizování snímků paměti  
  
1.  Vytvoření [CMemoryState](http://msdn.microsoft.com/en-us/8fade6e9-c6fb-4b2a-8565-184a912d26d2) objekt a volání [CMemoryState::Checkpoint](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Checkpoint) – členská funkce. Tím se vytvoří první snímku paměti.  
  
2.  Poté, co váš program provede jeho operací přidělení a zrušení přidělení paměti, vytvořte další `CMemoryState` objekt a volání `Checkpoint` pro tento objekt. To získá druhý snímku využití paměti.  
  
3.  Vytvoření třetí `CMemoryState` objekt a volání jeho [CMemoryState::Difference](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Difference) – členská funkce, jako argumenty zadávání předchozí dva `CMemoryState` objekty. Pokud je rozdíl mezi stavy dvě paměti `Difference` funkce vrátí nenulovou hodnotu. To znamená, že, nebyly bylo zrušeno některé bloky paměti.  
  
     Tento příklad ukazuje, jak vypadá kód:  
  
    ```  
    // Declare the variables needed  
    #ifdef _DEBUG  
        CMemoryState oldMemState, newMemState, diffMemState;  
        oldMemState.Checkpoint();  
    #endif  
  
        // Do your memory allocations and deallocations.  
        CString s("This is a frame variable");  
        // The next object is a heap object.  
       CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
  
    #ifdef _DEBUG  
        newMemState.Checkpoint();  
        if( diffMemState.Difference( oldMemState, newMemState ) )  
        {  
            TRACE( "Memory leaked!\n" );  
        }  
    #endif  
    ```  
  
     Všimněte si, že příkazy Kontrola paměti jsou v závorkách podle **_DEBUG #ifdef – / #endif** blokuje tak, že se kompilují pouze v ladicí verze vašeho programu.  
  
     Nyní když znáte nevrácená paměť systému existuje, můžete použít jiné členské funkce [CMemoryState::DumpStatistics](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpStatistics) který vám pomůže ho najít.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Viewing_memory_statistics"></a>Zobrazení statistiky paměti  
 [CMemoryState::Difference](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Difference) funkce porovná dva objekty stav paměti a zjišťuje všechny objekty, které není zrušeno přidělení haldy mezi stavy začátek a konec. Poté, co jste pořídili snímky paměti a porovná je s pomocí `CMemoryState::Difference`, můžete volat [CMemoryState::DumpStatistics](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpStatistics) získat informace o objektech, které nebyly bylo zrušeno.  
  
 Podívejte se na následující příklad:  
  
```  
if( diffMemState.Difference( oldMemState, newMemState ) )  
{  
   TRACE( "Memory leaked!\n" );  
   diffMemState.DumpStatistics();  
}  
```  
  
 Ukázka výpis z příkladu vypadá takto:  
  
```  
0 bytes in 0 Free Blocks  
22 bytes in 1 Object Blocks  
45 bytes in 4 Non-Object Blocks  
Largest number used: 67 bytes  
Total allocations: 67 bytes  
```  
  
 Bloky, jejichž navrácení je zpožděno. Pokud jsou volné bloky `afxMemDF` byla nastavena na `delayFreeMemDF`.  
  
 Obyčejnou objekt bloky, zobrazí na druhém řádku zůstat přidělené v haldě.  
  
 Bloky non-object zahrnout pole a struktury přidělený `new`. V takovém případě čtyři bloky jiný objekt byly přiděleny na haldě, ale není navrácena.  
  
 `Largest number used`poskytuje maximální množství paměti používané program kdykoli.  
  
 `Total allocations`poskytuje celkovém množství paměti, které program.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Taking_object_dumps"></a>Vezme objekt výpisy paměti  
 V aplikaci MFC můžete použít [CMemoryState::DumpAllObjectsSince](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpAllObjectsSince) vypsat popis všech objektů v haldě, které nebyly bylo zrušeno. `DumpAllObjectsSince`Vypíše všechny objekty přidělené od minulého [CMemoryState::Checkpoint](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__Checkpoint). Pokud žádné `Checkpoint` volání neproběhla, `DumpAllObjectsSince` vypíše všechny objekty a nonobjects aktuálně v paměti.  
  
> [!NOTE]
>  Než budete moct použít MFC vypsání objektu, musíte [zapnout diagnostické trasování](#BKMK_Enabling_Memory_Diagnostics).  
  
> [!NOTE]
>  Při ukončení aplikace MFC automaticky vypíše všechny uniklé objekty, proto není nutné vytvořit kód pro výpis objekty v daném okamžiku.  
  
 Následující kód testů pro nevrácená paměť systému srovnáním dvou stavů – stav paměti a vypíše všechny objekty, pokud je zjištěn nevrácenou.  
  
```  
if( diffMemState.Difference( oldMemState, newMemState ) )  
{  
   TRACE( "Memory leaked!\n" );  
   diffMemState.DumpAllObjectsSince();  
}  
```  
  
 Obsah výpisu vypadat takto:  
  
```  
Dumping objects ->  
  
{5} strcore.cpp(80) : non-object block at $00A7521A, 9 bytes long  
{4} strcore.cpp(80) : non-object block at $00A751F8, 5 bytes long  
{3} strcore.cpp(80) : non-object block at $00A751D6, 6 bytes long  
{2} a CPerson at $51A4  
  
Last Name: Smith  
First Name: Alan  
Phone #: 581-0215  
  
{1} strcore.cpp(80) : non-object block at $00A7516E, 25 bytes long  
```  
  
 Čísla v závorkách na začátku většina řádků určit pořadí, ve které byly přiděleny objekty. Objekt nedávno přidělené má nejvyšší číslo a zobrazí se v horní části výpisu.  
  
 Pokud chcete získat maximální množství informací mimo výpisu objekt, můžete přepsat `Dump` – členská funkce všech `CObject`-odvozené objekt, který chcete přizpůsobit výpisu objektu.  
  
 Můžete nastavit zarážky na přidělení paměti konkrétní nastavením globální proměnné `_afxBreakAlloc` na číslo zobrazené ve složených závorkách. Znovu spusťte program, bude ladicí program této přidělení probíhá porušit provádění. Potom můžete zobrazit v zásobníku volání, které chcete zobrazit, jak váš program tu pro tento bod.  
  
 Běhové knihovny jazyka C má podobné funkce [_crtsetbreakalloc –](/cpp/c-runtime-library/reference/crtsetbreakalloc), že můžete použít pro přidělení běhové C.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
####  <a name="BKMK_Interpreting_memory_dumps"></a>Interpretace paměti výpisy paměti  
 Podívejte se na tento objekt výpisu podrobněji:  
  
```  
{5} strcore.cpp(80) : non-object block at $00A7521A, 9 bytes long  
{4} strcore.cpp(80) : non-object block at $00A751F8, 5 bytes long  
{3} strcore.cpp(80) : non-object block at $00A751D6, 6 bytes long  
{2} a CPerson at $51A4  
  
Last Name: Smith  
First Name: Alan  
Phone #: 581-0215  
  
{1} strcore.cpp(80) : non-object block at $00A7516E, 25 bytes long  
```  
  
 Program, který vygeneroval tento výpis měl pouze dva explicitní přidělení – jednu v zásobníku a jeden v haldě:  
  
```  
// Do your memory allocations and deallocations.  
CString s("This is a frame variable");  
// The next object is a heap object.  
CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
```  
  
 `CPerson` Konstruktor přijímá tři argumenty, které jsou ukazatele na `char`, které se používají k inicializaci `CString` proměnné členů. V výpis stavu paměti, se zobrazí `CPerson` objekt spolu s tři nonobject bloky (3, 4 a 5). Tyto znaky pro uložení `CString` členské proměnné a nebude možné odstranit, když `CPerson` destruktoru objektu je volána.  
  
 Blok číslo 2 je `CPerson` samotného objektu. `$51A4`představuje adresu bloku a následuje obsah objektu, které byly výstupem `CPerson`::`Dump` při volání [DumpAllObjectsSince](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpAllObjectsSince).  
  
 Snadno uhodnout je přidružen blok číslo 1 `CString` proměnné rámce z důvodu jeho pořadové číslo a velikost, která odpovídá počet znaků v rámečku `CString` proměnné. Proměnné přidělené rámec jsou automaticky zrušeno při rámečku ocitne mimo rozsah.  
  
 **Proměnné rámce**  
  
 Obecně platí by neměl starat o haldy objekty přidružené proměnné rámce, protože jsou automaticky navrácena při proměnné rámce se dostala mimo rozsah. Abyste se vyhnuli zbytečné soubory ve vašem diagnostiky výpisy paměti, měli umístit vaše volání `Checkpoint` , aby byly mimo rozsah proměnné rámce. Například do hranatých závorek oboru v předchozí kód přidělení, jak je vidět tady:  
  
```  
oldMemState.Checkpoint();  
{  
    // Do your memory allocations and deallocations ...  
    CString s("This is a frame variable");  
    // The next object is a heap object.  
    CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
}  
newMemState.Checkpoint();  
```  
  
 Do závorek oboru na místě výpis stavu paměti v tomto příkladu je následující:  
  
```  
Dumping objects ->  
  
{5} strcore.cpp(80) : non-object block at $00A7521A, 9 bytes long  
{4} strcore.cpp(80) : non-object block at $00A751F8, 5 bytes long  
{3} strcore.cpp(80) : non-object block at $00A751D6, 6 bytes long  
{2} a CPerson at $51A4  
  
Last Name: Smith  
First Name: Alan  
Phone #: 581-0215  
```  
  
 **Nonobject přidělení**  
  
 Všimněte si, že některé přidělení jsou objekty (například `CPerson`) a některé jsou nonobject přidělení. "Nonobject přidělení" jsou přidělení pro objekty, které není odvozen od `CObject` nebo přidělení primitivní typy C jako `char`, `int`, nebo `long`. Pokud **CObject -**odvozené třídy přiděluje další prostor, například pro vnitřní vyrovnávací paměti, zobrazí ty objekty, objekt a nonobject přidělení.  
  
 **Brání nevracení paměti**  
  
 Ve výše uvedeném kódu všimněte, že bloku paměti přidružené `CString` proměnné rámce bylo zrušeno automaticky a nezobrazuje jako nevrácenou pamětí. Většina nevracení paměti, které jsou přidružené k proměnné rámce postará automatické zrušení přidělení související s rozsahu pravidla.  
  
 Pro objekty přidělené v haldě ale musíte explicitně odstranit objekt, aby se zabránilo nevrácenou pamětí. Chcete-li vyčistit poslední nevrácená paměť systému v předchozím příkladu, odstraňte `CPerson` objekt přidělené v haldě, následujícím způsobem:  
  
```  
{  
    // Do your memory allocations and deallocations.  
    CString s("This is a frame variable");  
    // The next object is a heap object.  
    CPerson* p = new CPerson( "Smith", "Alan", "581-0215" );  
    delete p;  
}  
```  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
####  <a name="BKMK_Customizing_object_dumps"></a>Přizpůsobení objektu výpisy paměti  
 Pokud odvodíte třídu od [CObject](/cpp/mfc/reference/cobject-class), můžete přepsat `Dump` – členská funkce můžete poskytnout dodatečné informace, pokud používáte [DumpAllObjectsSince](/cpp/mfc/reference/cmemorystate-structure.md#cmemorystate__DumpAllObjectsSince) k výpisu objekty, které se [Výstup – okno](../ide/reference/output-window.md).  
  
 `Dump` Funkce zapíše textovou reprezentaci objektu členské proměnné na kontext výpisu ([CDumpContext](/cpp/mfc/reference/cdumpcontext-class)). Kontext výpisu je podobný datovému proudu vstupně-výstupních operací. Můžete použít operátor připojení (**<<**) pro odesílání dat na `CDumpContext`.  
  
 Při přepsání `Dump` funkce, měli byste nejprve volat základní třída verzi `Dump` Vypsat obsah objektu základní třídy. Ve výstupu textový popis a hodnotu pro každou proměnnou člen vaší odvozené třídy.  
  
 Prohlášení o `Dump` funkce vypadá takto:  
  
```  
class CPerson : public CObject  
{  
public:  
#ifdef _DEBUG  
    virtual void Dump( CDumpContext& dc ) const;  
#endif  
  
    CString m_firstName;  
    CString m_lastName;  
    // And so on...  
};  
```  
  
 Vzhledem k tomu, že objekt vypsání smysl pouze při ladění programu, deklaraci `Dump` funkce je v závorkách s **_DEBUG #ifdef – / #endif** bloku.  
  
 V následujícím příkladu `Dump` první volání funkce `Dump` funkce pro základní třídu. Pak zapíše krátký popis jednotlivých členské proměnné společně s hodnotu člena s hodnotou diagnostiky datového proudu.  
  
```  
#ifdef _DEBUG  
void CPerson::Dump( CDumpContext& dc ) const  
{  
    // Call the base class function first.  
    CObject::Dump( dc );  
  
    // Now do the stuff for our specific class.  
    dc << "last name: " << m_lastName << "\n"  
        << "first name: " << m_firstName << "\n";  
}  
#endif  
```  
  
 Je nutné zadat `CDumpContext` argument k určení, kde bude výstup dump přejděte. Ladicí verze knihovny MFC poskytuje i předdefinovanou `CDumpContext` objekt s názvem `afxDump` který odesílá výstup na ladicího programu.  
  
```  
CPerson* pMyPerson = new CPerson;  
// Set some fields of the CPerson object.  
//...  
// Now dump the contents.  
#ifdef _DEBUG  
pMyPerson->Dump( afxDump );  
#endif  
```  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
##  <a name="BKMK_Reducing_the_size_of_an_MFC_Debug_build"></a>Zmenšení velikosti sestavení pro ladění MFC  
 Informace o ladění pro rozsáhlé aplikace MFC může trvat až velké množství místa na disku. Jeden z následujících postupů můžete použít ke snížení velikosti:  
  
1.  Opětovné sestavení knihovny MFC pomocí [/Z7, / zi, /ZI (formát informace ladění)](/cpp/build/reference/z7-zi-zi-debug-information-format) možnost, místo **/Z7**. Tyto možnosti vytvořit soubor databáze (PDB) jeden program, který obsahuje informace o ladění pro celou knihovnu, snižuje redundance a ukládání místa.  
  
2.  Opětovné sestavení knihovny MFC bez informace o ladění (žádné [/Z7, / zi, /ZI (formát informace ladění)](/cpp/build/reference/z7-zi-zi-debug-information-format) možnost). V takovém případě chybí informace o ladění bude bránit v použití většina zařízení ladicí program kódu knihovny MFC, ale protože knihovny MFC jsou již důkladně ladit, nemusí to být problém.  
  
3.  Vytvoříte vlastní aplikace s informace o ladění pro vybrané moduly, jak je popsáno níže.  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
###  <a name="BKMK_Building_an_MFC_app_with_debug_information_for_selected_modules"></a>Vytvoření aplikace MFC s informace o ladění pro vybrané moduly  
 Vytváření vybraného modulů s ladění knihovny MFC umožňuje použití krokování a jiných ladění zařízení v těchto modulů. Tento postup využívá obou ladění a vydání režimy makefile Visual C++, proto očekávání změn popsaných v následující kroky (a také využívajícího "znovu vytvořit všechny" nezbytné, pokud je potřeba úplné sestavení pro vydání).  
  
1.  V Průzkumníku řešení vyberte projekt.  
  
2.  Z **zobrazení** nabídce vyberte možnost **stránky vlastností**.  
  
3.  Nejdřív vytvoříte novou konfiguraci projektu.  
  
    1.  V  **\<projektu > stránky vlastností** dialogové okno, klikněte **nástroje Configuration Manager** tlačítko.  
  
    2.  V [dialogové okno nástroje Configuration Manager](http://msdn.microsoft.com/en-us/fa182dca-282e-4ae5-bf37-e155344ca18b), vyhledejte projektu v mřížce. V **konfigurace** sloupce, vyberte  **\<nová... >**.  
  
    3.  V [dialogové okno Nový projekt konfigurace](http://msdn.microsoft.com/en-us/cca616dc-05a6-4fe3-bdc1-40c72a66f2be), zadejte název pro novou konfiguraci, jako je například "Částečné Debug", **název konfigurace projektu** pole.  
  
    4.  V **Kopírovat nastavení z** vyberte **verze**.  
  
    5.  Klikněte na tlačítko **OK** zavřete **novou konfiguraci projektu**dialogové okno.  
  
    6.  Zavřít **nástroje Configuration Manager** dialogové okno.  
  
4.  Nyní bude nastavení možností pro celý projekt.  
  
    1.  V **stránky vlastností** dialogovém **vlastnosti konfigurace** složky, vyberte **Obecné** kategorie.  
  
    2.  V mřížce nastavení projektu, rozbalte položku **výchozí nastavení projektu** (v případě potřeby).  
  
    3.  V části **výchozí projekt**, Najít **použití knihovny MFC**. Aktuální nastavení se zobrazí v pravém sloupci mřížky. Klikněte na aktuální nastavení a změňte ji na **MFC použití statické knihovny**.  
  
    4.  V levém podokně **vlastnosti stránky** dialogové okno, otevřete **C/C++** složky a vyberte **preprocesor**. V mřížce vlastnosti najít **Definice preprocesoru** a nahraďte "NDEBUG" _DEBUG "–".  
  
    5.  V levém podokně **vlastnosti stránky** dialogové okno, otevřete **Linkeru** složky a vyberte **vstup** kategorie. V mřížce vlastnosti najít **Další závislosti**. V **Další závislosti** nastavení, zadejte "NAFXCWD. LIB"a"LIBCMT."  
  
    6.  Klikněte na tlačítko **OK** nové možnosti sestavení uložte a zavřete **stránky vlastností** dialogové okno.  
  
5.  Z **sestavení** nabídce vyberte možnost **znovu sestavit**. Odebere všechny informace o ladění moduly, ale nemá vliv na knihovny MFC.  
  
6.  Nyní je nutné přidat informace o ladění zpět na vybrané modulů v aplikaci. Mějte na paměti, že můžete nastavit zarážky a provádět další funkce ladicí program pouze v moduly, které mají kompilovat s ladicími informacemi. Pro každý soubor projektu, ve které chcete zahrnout informace o ladění, provede následující kroky:  
  
    1.  V Průzkumníku řešení otevřete **zdrojové soubory** složky umístěné v projektu.  
  
    2.  Vyberte soubor, který chcete nastavit informace o ladění pro.  
  
    3.  Z **zobrazení** nabídce vyberte možnost **stránky vlastností**.  
  
    4.  V **stránky vlastností** dialogovém **nastavení konfigurace** složku, otevřete **C/C++** vyberte složku **Obecné** kategorie.  
  
    5.  V mřížce vlastnosti najít **ladění formátu informací.**  
  
    6.  Klikněte **Debug Information Format** nastavení a vyberte požadovanou možnost (obvykle **/ZI**) pro informace o ladění.  
  
    7.  Pokud používáte aplikace generované v Průvodci aplikace nebo mít předkompilovaných hlaviček, je potřeba vypnout předkompilovaných hlaviček nebo je znovu zkompiluje před kompilování dalších modulů. Jinak zobrazí se upozornění C4650 a chybová zpráva C2855. Předkompilované hlavičky můžete vypnout změnou **vytvoření/použití předkompilovaných hlaviček** nastavení v  **\<Projekt > vlastnosti** dialogové okno (**vlastnosti konfigurace**  složky, **C/C++** podsložku, **předkompilovaných hlaviček** kategorie).  
  
7.  Z **sestavení** nabídce vyberte možnost **sestavení** znovu sestavit soubory projektu, které jsou zastaralé.  
  
 Jako alternativu k technik popsaných v tomto tématu, můžete zadat jednotlivé možnosti pro každý soubor externí soubor pravidel. V takovém případě propojení s knihovny MFC ladění, je nutné definovat [_DEBUG –](/cpp/c-runtime-library/debug) příznak pro každý modul. Pokud chcete používat verzi knihovny MFC, je nutné zadat NDEBUG. Další informace o zápisu externí soubory pravidel najdete v tématu [NMAKE – odkaz](/cpp/build/running-nmake).  
  
 [V tomto tématu](#BKMK_In_this_topic)  
  
## <a name="see-also"></a>Viz také  
 [Ladění jazyka Visual C++](../debugger/debugging-native-code.md)