---
title: 'Postupy: Nastavení názvu vlákna v nativním kódu | Dokumentace Microsoftu'
ms.date: 12/17/2018
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [C++], threads
- SetThreadName function
- threading [Visual Studio], names
- thread names
- debugging [Visual Studio], threads
ms.assetid: c85d0968-9f22-4d69-87f4-acca2ae777b8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: acddd39df0c91aeef5c425ffa67cb234d76d0473
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53961345"
---
# <a name="how-to-set-a-thread-name-in-native-code"></a>Postupy: Nastavení názvu vlákna v nativním kódu
Pojmenování vlákna je možné v jakékoli edici sady Visual Studio. Pojmenování vláken je užitečné pro udržování přehledu o vlákna **vlákna** okna.

## <a name="set-a-thread-name"></a>Nastavení názvu vlákna

`SetThreadName` Funkce je užitečná pro nastavení a zobrazení vláken, pokud je připojen ladicí program ke spuštění kódu. Spouští se v sadě Visual Studio 2017 verze 15.6, můžete použít [SetThreadDescription](https://docs.microsoft.com/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreaddescription) funkci pro nastavení a zobrazit názvy vláken.

```C++
#include <windows.h>
#include <processthreadsapi.h>

int main()
{
    HRESULT r;
    r = SetThreadDescription(
        GetCurrentThread(),
        L"ThisIsMyThreadName!"
    );

    return 0;
}
```

## <a name="set-a-thread-name-using-setthreadname"></a>Nastavení názvu vlákna pomocí setthreadname –

K nastavení názvu vlákna ve svém programu, můžete použít také `SetThreadName` fungovat, jak je znázorněno v následujícím příkladu kódu. Všimněte si, že název vlákna je zkopírován do vlákna tak, aby paměti pro `threadName` parametr mohlo být uvolněno.  Tato metoda používá přístup na základě výjimky, který funguje jenom v případě, že v době, kdy se používá metodu založenou na výjimku, je připojen ladicí program. Název vlákna, které jste nastavili pomocí této metody není k dispozici v výpisů paměti nebo nástroje pro analýzu výkonu.

Následující příklad kódu ukazuje, jak používat `SetThreadName`:

```C++
//  
// Usage: SetThreadName ((DWORD)-1, "MainThread");  
//  
#include <windows.h>  
const DWORD MS_VC_EXCEPTION = 0x406D1388;  
#pragma pack(push,8)  
typedef struct tagTHREADNAME_INFO  
{  
    DWORD dwType; // Must be 0x1000.  
    LPCSTR szName; // Pointer to name (in user addr space).  
    DWORD dwThreadID; // Thread ID (-1=caller thread).  
    DWORD dwFlags; // Reserved for future use, must be zero.  
 } THREADNAME_INFO;  
#pragma pack(pop)  
void SetThreadName(DWORD dwThreadID, const char* threadName) {  
    THREADNAME_INFO info;  
    info.dwType = 0x1000;  
    info.szName = threadName;  
    info.dwThreadID = dwThreadID;  
    info.dwFlags = 0;  
#pragma warning(push)  
#pragma warning(disable: 6320 6322)  
    __try{  
        RaiseException(MS_VC_EXCEPTION, 0, sizeof(info) / sizeof(ULONG_PTR), (ULONG_PTR*)&info);  
    }  
    __except (EXCEPTION_EXECUTE_HANDLER){  
    }  
#pragma warning(pop)  
}  
```  

## <a name="see-also"></a>Viz také  
 [Ladění vícevláknových aplikací](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)   
 [Postupy: Nastavení názvu vlákna ve spravovaném kódu](../debugger/how-to-set-a-thread-name-in-managed-code.md)