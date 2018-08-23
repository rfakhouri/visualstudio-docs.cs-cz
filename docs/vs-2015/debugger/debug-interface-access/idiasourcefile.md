---
title: Idiasourcefile – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSourceFile interface
ms.assetid: 6e9be757-797f-4960-ba62-c14092620bbd
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8b43eeda2111052eda355f3b04fa0e2c5087dc07
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674661"
---
# <a name="idiasourcefile"></a>IDiaSourceFile
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasourcefile –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasourcefile).  
  
Reprezentuje zdrojový soubor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaSourceFile : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaSourceFile`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaSourceFile::get_uniqueId](../../debugger/debug-interface-access/idiasourcefile-get-uniqueid.md)|Načte hodnotu klíče jednoduché celé číslo, které jsou jedinečné pro tuto bitovou kopii.|  
|[IDiaSourceFile::get_fileName](../../debugger/debug-interface-access/idiasourcefile-get-filename.md)|Načte název zdrojového souboru.|  
|[IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)|Načte typ kontrolního součtu.|  
|[IDiaSourceFile::get_compilands](../../debugger/debug-interface-access/idiasourcefile-get-compilands.md)|Získá enumerátor souborech určených ke kompilaci s čísly řádků odkazující na tento soubor.|  
|[IDiaSourceFile::get_checksum](../../debugger/debug-interface-access/idiasourcefile-get-checksum.md)|Načte kontrolní součet bajtů.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní [idiaenumsourcefiles::Item –](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md) nebo [idiaenumsourcefiles::Next –](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md) metody. Podívejte se na příklad podrobnosti.  
  
## <a name="example"></a>Příklad  
 Tato funkce zobrazí názvy všech zdrojových souborů, které přispívají k zadané tabulky.  
  
```cpp#  
void ShowSourceFiles(IDiaTable *pTable)  
{  
    CComPtr<IDiaEnumSourceFiles> pSourceFiles;  
    if ( SUCCEEDED( pTable->QueryInterface(  
                                _uuidof( IDiaEnumSourceFiles ),  
                               (void**)&pSourceFiles )  
                  )  
       )  
    {  
        CComPtr<IDiaSourceFile> pSourceFile;  
        while ( SUCCEEDED( hr = pSourceFiles->Next( 1, &pSourceFile, &celt ) ) &&  
                celt == 1 )  
        {  
            CDiaBSTR fileName;  
            if ( pSourceFile->get_fileName( &fileName) == S_OK )  
            {  
                printf( "file name: %ws\n", fileName );  
            }  
            pSourceFile = NULL;  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsourcefiles::Item –](../../debugger/debug-interface-access/idiaenumsourcefiles-item.md)   
 [Idiaenumsourcefiles::Next –](../../debugger/debug-interface-access/idiaenumsourcefiles-next.md)   
 [Idialinenumber::get_sourcefile –](../../debugger/debug-interface-access/idialinenumber-get-sourcefile.md)   
 [Idiasession::findfilebyid –](../../debugger/debug-interface-access/idiasession-findfilebyid.md)   
 [Idiasession::findlines –](../../debugger/debug-interface-access/idiasession-findlines.md)   
 [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)



