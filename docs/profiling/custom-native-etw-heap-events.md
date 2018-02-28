---
title: "Události haldy vlastní nativní trasování událostí pro Windows | Microsoft Docs"
ms.custom: 
ms.date: 02/24/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 668a6603-5082-4c78-98e6-f3dc871aa55b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- C++
ms.workload:
- cplusplus
ms.openlocfilehash: 7d55fdb061b9cb2fcd0497b7dde8e5c4255cf5e3
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/05/2018
---
# <a name="custom-native-etw-heap-events"></a>Vlastní nativní ETW – události haldy

Visual Studio obsahuje celou řadu [profilování a diagnostické nástroje](../profiling/profiling-tools.md), včetně nativní paměti profileru.  Tato profileru zachytí [události trasování událostí](/windows-hardware/drivers/devtest/event-tracing-for-windows--etw-) od zprostředkovatele haldy a poskytuje analýzu jak paměti se přidělovány a využívány.  Ve výchozím nastavení tento nástroj můžete analyzovat pouze přidělení z standardní haldy Windows žádost a rozdělení mimo tento nativní haldy by se zobrazit.

Existují mnoho případy, ve kterých chcete použít vlastní vlastní haldy a vyhnout se nároky na přidělení z haldě standardní.  Například můžete použít [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) přidělit velké množství paměti při spuštění aplikace nebo hra, a následně spravovat vlastní bloky v rámci tohoto seznamu.  V tomto scénáři by nástroj paměti profileru vidět jenom tento počáteční přidělení a není vaší vlastní správy provést uvnitř bloku paměti.  Však pomocí vlastního zprostředkovatele nativní ETW haldy, můžete je nechat nástroj vědět o rozdělení, které provádíte mimo standardní halda.

Například v projektu takto kde `MemoryPool` je vlastní haldy, by se zobrazí jenom tehdy jeden přidělování v haldě Windows:

```cpp
class Foo
{
public:
    int x, y;
};

...

// MemoryPool is a custom managed heap, which allocates 8192 bytes 
// on the standard Windows Heap named "Windows NT"
MemoryPool<Foo, 8192> mPool;

// the "allocate" method requests memory from the pool created above
// and is cast to an object of type Foo, shown above
Foo* pFoo1 = (Foo*)mPool.allocate();
Foo* pFoo2 = (Foo*)mPool.allocate();
Foo* pFoo3 = (Foo*)mPool.allocate();
```

Snímek z [využití paměti](../profiling/memory-usage.md) nástroj bez vlastní haldy sledování by zobrazit právě přidělení jednobajtová 8192 a žádné vlastní přidělení prováděné fondem:

![Přidělení haldy Windows](media/heap-example-windows-heap.png)

Provedením následujících kroků používáme k stejný nástroj pro sledování paměti usgae v našem hald.

## <a name="how-to-use"></a>Postup použití

V této knihovně můžete snadno použít jazyka C a C++.

1. Vložit hlavičku pro vlastní haldy zprostředkovatele trasování událostí pro Windows:

   ```cpp
   #include <VSCustomNativeHeapEtwProvider.h>
   ```

1. Přidat `__declspec(allocator)` dekoratéra všechny funkce ve vaší vlastní haldy správci, který vrací ukazatel na nově přidělených halda paměti.  Tato dekoratéra umožňuje nástroj, který správně identifikují typ paměti nebyl vrácen.  Příklad:

   ```cpp
   __declspec(allocator) void *MyMalloc(size_t size);
   ```
   
   > [!NOTE]
   > Tato dekoratéra se tak dozví, kompilátor, tato funkce je volání přidělení.  Výstup každé volání funkce adresu callsite, velikost pokyn volání a typeId nového objektu na nový `S_HEAPALLOCSITE` symbol.  Při přidělení zásobník volání Windows bude generovat událost trasování událostí pro Windows se tyto informace.  Zásobník volání hledání zpáteční adresu odpovídající provede nástroj paměti profileru `S_HEAPALLOCSITE` symbolů a informace ID typu v symbolu se používá k zobrazení runtime typ přidělení.
   >
   > Stručně řečeno, to znamená volání, které vypadá jako `(B*)(A*)MyMalloc(sizeof(B))` se zobrazí v nástroji jako typu `B`, nikoli `void` nebo `A`.

1. Pro jazyk C++, vytvořte `VSHeapTracker::CHeapTracker` objekt, poskytuje název haldě, které se zobrazí v nástroji pro profilaci:

   ```cpp
   auto pHeapTracker = std::make_unique<VSHeapTracker::CHeapTracker>("MyCustomHeap");
   ```

   Pokud používáte C, použijte `OpenHeapTracker` funkce místo.  Tato funkce vrací popisovač, který budete používat při volání jiných funkcí sledování:
  
   ```C
   VSHeapTrackerHandle hHeapTracker = OpenHeapTracker("MyHeap");
   ```

1. Při přidělování paměti pomocí vlastní funkcí, volání `AllocateEvent` (C++) nebo `VSHeapTrackerAllocateEvent` metody (C) předávání v ukazatele na paměť a její velikost, sledovat přidělení:

   ```cpp
   pHeapTracker->AllocateEvent(memPtr, size);
   ```

   or

   ```C
   VSHeapTrackerAllocateEvent(hHeapTracker, memPtr, size);
   ```

   > [!IMPORTANT]
   > Nezapomeňte značky svoji vlastní allocator funkci s `__declspec(allocator)` dekoratéra popsané výše.

1. Při rušení přidělení paměti pomocí vlastní funkcí, volání `DeallocateEvent` (C++) nebo `VSHeapTracerDeallocateEvent` funkce (C), předávání v ukazatele do paměti, sledovat navrácení:

   ```cpp
   pHeapTracker->DeallocateEvent(memPtr);
   ```

   nebo:

   ```C
   VSHeapTrackerDeallocateEvent(hHeapTracker, memPtr);
   ```

1. Při opětovném přidělování paměti pomocí vlastní funkcí, volání `ReallocateEvent` (C++) nebo `VSHeapReallocateEvent` metody (C) předávání v ukazatel na novou paměť, velikost přidělení a ukazatel na staré paměti:

   ```cpp
   pHeapTracker->ReallocateEvent(memPtrNew, size, memPtrOld);
   ```

   nebo:

   ```C
   VSHeapTrackerReallocateEvent(hHeapTracker, memPtrNew, size, memPtrOld);
   ```

1. Nakonec pokud chcete zavřít a vyčištění sledování vlastní haldy v jazyce C++, použijte `CHeapTracker` destruktor, buď ručně, nebo prostřednictvím standardních pravidel oborů, nebo `CloseHeapTracker` funkce v C:

   ```cpp
   delete pHeapTracker;
   ```

   nebo:

   ```C
   CloseHeapTracker(hHeapTracker);
   ```

## <a name="tracking-memory-usage"></a>Sledování využití paměti
Pomocí těchto volání na místě, vaše vlastní haldy využití lze nyní sledovat přes standardní **využití paměti** nástroje v sadě Visual Studio.  Další informace o tom, jak pomocí tohoto nástroje najdete v tématu [využití paměti](../profiling/memory-usage.md) dokumentaci. Zkontrolujte, zda že jste povolili haldy profilace pomocí snímků, jinak se nezobrazí vaše vlastní haldy využití zobrazí. 

![Povolit haldy profilace](media/heap-enable-heap.png)

Chcete-li zobrazit vaše vlastní haldy sledování, použijte **haldy** rozevírací umístěný v pravém horním rohu **snímku** okna je možné změnit zobrazení z *NT haldy* vlastní haldě, jako s názvem dříve.

![Výběr haldy](media/heap-example-custom-heap.png)

Pomocí výše uvedeného příkladu kódu s `MemoryPool` vytváření `VSHeapTracker::CHeapTracker` objekt a na našem vlastní `allocate` metoda teď volání `AllocateEvent` metoda, se zobrazí výsledek tohoto vlastní přidělení zobrazující 3 instancí součtem 24 bajtů, všechny typu `Foo`.

Výchozí hodnota *NT haldy* haldy vypadá a to stejně jako dříve, a uveďte naše `CHeapTracker` objektu.

![Halda NT s sledovací modul](media/heap-example-windows-heap.png)

I s standardní haldy Windows, můžete také použít tento nástroj porovnat snímky a vyhledejte nevracení a poškození vlastní haldy, který je popsán v hlavní [využití paměti](../profiling/memory-usage.md) dokumentaci.

> [!TIP]
> Visual Studio také obsahuje **využití paměti** nástroj v **profilace výkonu** sada nástrojů, která je povolena z **ladění > výkonu profileru** nabídky, nebo **Alt + F2** klávesové kombinace.  Tato funkce nezahrnuje haldy sledování a nezobrazí vaše vlastní haldy podle postupu popsaného tady.  Pouze **diagnostické nástroje** okno, které můžete povolit **ladění > Windows > zobrazit diagnostické nástroje** nabídky, nebo **Ctrl + Alt + F2** klávesové kombinaci, obsahuje tato funkce.

## <a name="see-also"></a>Viz také
[Nástroje pro profilaci](../profiling/profiling-tools.md)  
[Využití paměti](../profiling/memory-usage.md)
