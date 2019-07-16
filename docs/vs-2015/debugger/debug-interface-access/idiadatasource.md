---
title: Idiadatasource – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a02eb9048c0e9338e6300fc63666af4db535b3ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198594"
---
# <a name="idiadatasource"></a>IDiaDataSource
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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
  
```cpp#  
  
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
 Záhlaví: dia2.h  
  
 Knihovna: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
