---
title: Idiadatasource – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 97b55dad4ba557e85291d572ef24b1ad12e08a3c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54930677"
---
# <a name="idiadatasource"></a>IDiaDataSource
Iniciuje přístup ke zdroji symboly ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaDataSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaDataSource`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaDataSource::get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|Načte název souboru pro poslední chyba načtení.|  
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|Otevře a připraví soubor databáze (PDB) programu jako zdroj dat ladění.|  
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|Otevře a ověřuje, že soubor databáze (PDB) programu odpovídá podpisu údaje; připraví soubor typu .pdb jako zdroj dat ladění.|  
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|Otevře a připraví data ladění přidružené k souboru.exe/.dll.|  
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|Připraví data ladění uložených v souboru databáze (PDB) programu přistupovat prostřednictvím proud dat v paměti.|  
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|Otevře relaci pro dotazování na symboly.|  
  
## <a name="remarks"></a>Poznámky  
 Volání do jedné z metod zatížení `IDiaDataSource` rozhraní otevře zdroj symbol. Úspěšné volání [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) vrátí metoda [idiasession –](../../debugger/debug-interface-access/idiasession.md) rozhraní, které podporuje dotazování na zdroj dat. Pokud metoda zatížení vrátí chybu týkající se souborů pak bude [idiadatasource::get_lasterror –](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md) metoda vrátit hodnota obsahuje název souboru, který je přidružený k chybě.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je získán voláním `CoCreateInstance` funkce s identifikátorem třídy `CLSID_DiaSource` a interface ID `IID_IDiaDataSource`. Příklad ukazuje, jak získat toto rozhraní.  
  
## <a name="example"></a>Příklad  
  
```C++  
  
      IDiaDataSource* pSource;  
HRESULT hr = CoCreateInstance(CLSID_DiaSource,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaDataSource,  
                              (void**) &pSource);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)