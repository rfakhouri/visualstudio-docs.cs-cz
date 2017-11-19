---
title: "Idiainjectedsource – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaInjectedSource interface
ms.assetid: 75192c5c-812d-4675-9dc5-4c2cff3ba503
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7beda305bbe0673b6e1b47f0e11eb641ab8aa0d5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiainjectedsource"></a>IDiaInjectedSource
Přístupy vložit uložené ve zdroji dat DIA zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaInjectedSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDiaInjectedSource`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiainjectedsource::get_crc –](../../debugger/debug-interface-access/idiainjectedsource-get-crc.md)|Načte kontrolu cyklické redundance (CRC) vypočítaných z bajtů zdrojového kódu.|  
|[Idiainjectedsource::get_length –](../../debugger/debug-interface-access/idiainjectedsource-get-length.md)|Získá počet bajtů kódu.|  
|[Idiainjectedsource::get_filename –](../../debugger/debug-interface-access/idiainjectedsource-get-filename.md)|Načte název souboru pro zdroj.|  
|[Idiainjectedsource::get_objectfilename –](../../debugger/debug-interface-access/idiainjectedsource-get-objectfilename.md)|Načte název souboru objektů, ke kterému bylo kompilováno zdroji.|  
|[Idiainjectedsource::get_virtualfilename –](../../debugger/debug-interface-access/idiainjectedsource-get-virtualfilename.md)|Načte název přidělený nepocházející ze souborů zdrojového kódu; To znamená, kód, který byl vložit.|  
|[Idiainjectedsource::get_sourcecompression –](../../debugger/debug-interface-access/idiainjectedsource-get-sourcecompression.md)|Načte indikátoru komprese zdroj použít.|  
|[Idiainjectedsource::get_source –](../../debugger/debug-interface-access/idiainjectedsource-get-source.md)|Načte bajtů zdrojového kódu.|  
  
## <a name="remarks"></a>Poznámky  
 Vložený zdroj je text, který je vložit během kompilace. To neznamená preprocesor `#include` použít v jazyce C++.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní [idiaenuminjectedsources::Item –](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md) nebo [idiaenuminjectedsources::Next –](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md) metody. Najdete v článku [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) rozhraní pro získání příklad `IDiaInjectedSource` rozhraní.  
  
## <a name="example"></a>Příklad  
 Tento příklad zobrazí dostupná z data `IDiaInjectedSource` rozhraní. Použití alternativní způsob [idiapropertystorage –](../../debugger/debug-interface-access/idiapropertystorage.md) rozhraní, podívejte se na příklad v [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) rozhraní.  
  
```C++  
void PrintInjectedSource(IDiaInjectedSource* pSource)  
{  
    ULONGLONG codeLength      = 0;  
    DWORD     crc             = 0;  
    DWORD     compressionType = 0;  
    BSTR      sourceFilename  = NULL;  
    BSTR      objectFilename  = NULL;  
    BSTR      virtualFilename = NULL;  
  
    std::cout << "Injected Source:" << std::endl;  
    if (pSource != NULL)  
    {  
        if (pSource->get_crc(&crc) == S_OK &&  
            pSource->get_sourceCompression(&compressionType) == S_OK &&  
            pSource->get_length(&codeLength) == S_OK)  
        {  
            wprintf(L"  crc = %lu\n", crc);  
            wprintf(L"  code length = %I64u\n",codeLength);  
            wprintf(L"  compression type code = %lu\n", compressionType);  
        }  
  
        wprintf(L"  source filename: ");  
        if (pSource->get_filename(&sourceFilename) == S_OK)  
        {  
            wprintf(L"%s", sourceFilename);  
        }  
        else  
        {  
            wprintf(L"<none>");  
        }  
        wprintf(L"\n");  
  
        wprintf(L"  object filename: ");  
        if (pSource->get_filename(&objectFilename) == S_OK)  
        {  
            wprintf(L"%s", objectFilename);  
        }  
        else  
        {  
            wprintf(L"<none>");  
        }  
        wprintf(L"\n");  
  
        wprintf(L"  virtual filename: ");  
        if (pSource->get_filename(&virtualFilename) == S_OK)  
        {  
            wprintf(L"%s", virtualFilename);  
        }  
        else  
        {  
            wprintf(L"<none>");  
        }  
        wprintf(L"\n");  
  
        SysFreeString(sourceFilename);  
        SysFreeString(objectFilename);  
        SysFreeString(virtualFilename);  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenuminjectedsources::Item –](../../debugger/debug-interface-access/idiaenuminjectedsources-item.md)   
 [Idiaenuminjectedsources::Next –](../../debugger/debug-interface-access/idiaenuminjectedsources-next.md)   
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)