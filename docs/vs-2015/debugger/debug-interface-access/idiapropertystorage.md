---
title: Idiapropertystorage – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage interface
ms.assetid: d3197a38-5973-4e56-873e-4f1b84c3f674
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 29832934b848729879ee1ba802c70f85117efd2a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60080375"
---
# <a name="idiapropertystorage"></a>IDiaPropertyStorage
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Umožňuje číst trvalou vlastnosti sady DIA vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaPropertyStorage : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDiaPropertyStorage`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDiaPropertyStorage::Enum](../../debugger/debug-interface-access/idiapropertystorage-enum.md)|Získá ukazatel na enumerátor pro vlastnosti v rámci této sady.|  
|[IDiaPropertyStorage::ReadBOOL](../../debugger/debug-interface-access/idiapropertystorage-readbool.md)|Přečte `BOOL` hodnoty v sadu vlastností.|  
|[IDiaPropertyStorage::ReadBSTR](../../debugger/debug-interface-access/idiapropertystorage-readbstr.md)|Přečte `BSTR` hodnoty v sadu vlastností.|  
|[IDiaPropertyStorage::ReadDWORD](../../debugger/debug-interface-access/idiapropertystorage-readdword.md)|Přečte `DWORD` hodnoty v sadu vlastností.|  
|[IDiaPropertyStorage::ReadLONG](../../debugger/debug-interface-access/idiapropertystorage-readlong.md)|Přečte `LONG` hodnoty v sadu vlastností.|  
|[IDiaPropertyStorage::ReadMultiple](../../debugger/debug-interface-access/idiapropertystorage-readmultiple.md)|Načte hodnoty vlastností v sadu vlastností.|  
|[IDiaPropertyStorage::ReadPropertyNames](../../debugger/debug-interface-access/idiapropertystorage-readpropertynames.md)|Získá odpovídající názvů řetězce pro daný vlastnost identifikátory.|  
|[IDiaPropertyStorage::ReadULONGLONG](../../debugger/debug-interface-access/idiapropertystorage-readulonglong.md)|Přečte `ULONGLONG` hodnoty v sadu vlastností.|  
  
## <a name="remarks"></a>Poznámky  
 Každou vlastnost v rámci sady vlastností je identifikován identifikátor vlastnosti (ID), čtyř bajtů `ULONG` hodnoty, které jsou jedinečné pro tuto sadu. Vlastnosti zveřejněné přes `IDiaPropertyStorage` rozhraní odpovídají dostupné vlastnosti v nadřazené rozhraní. Například vlastnosti [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) rozhraní je přístupný podle názvu prostřednictvím `IDiaPropertyStorage` rozhraní (Upozorňujeme, že i v případě, že vlastnost může být přístupné, neznamená to je platný pro vlastnost konkrétní `IDiaSymbol` objekt).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získat voláním toto rozhraní `QueryInterface` metodu na jiné rozhraní. Následující rozhraní může být dotázán na `IDiaPropertyStorage` rozhraní:  
  
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)  
  
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)  
  
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)  
  
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)  
  
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
  
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)  
  
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje funkci, která se zobrazí všechny vlastnosti, které jsou vystavené `IDiaPropertyStorage` objektu. Zobrazit [idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md) rozhraní pro příklad, jak `IDiaPropertyStorage` rozhraní se získávají z [idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md) rozhraní.  
  
```cpp#  
void PrintPropertyStorage(IDiaPropertyStorage* pPropertyStorage)  
{  
    IEnumSTATPROPSTG* pEnumProps;  
    STATPROPSTG       prop;  
    DWORD             celt = 1;  
  
    if (pPropertyStorage->Enum(&pEnumProps) == S_OK)  
    {  
        while (pEnumProps->Next(celt, &prop, &celt) == S_OK)  
        {  
            PROPSPEC pspec = { PRSPEC_PROPID, prop.propid };  
            PROPVARIANT vt = { VT_EMPTY };  
  
            if (pPropertyStorage->ReadMultiple( 1, &pspec, &vt) == S_OK)  
            {  
                switch( vt.vt ){  
                    case VT_BOOL:  
                        wprintf( L"%32s:\t %s\n", prop.lpwstrName, vt.bVal ? L"true" : L"false" );  
                        break;  
                    case VT_I2:  
                        wprintf( L"%32s:\t %d\n", prop.lpwstrName, vt.iVal );  
                        break;  
                    case VT_UI2:  
                        wprintf( L"%32s:\t %d\n", prop.lpwstrName, vt.uiVal );  
                        break;  
                    case VT_I4:  
                        wprintf( L"%32s:\t %d\n", prop.lpwstrName, vt.intVal );  
                        break;  
                    case VT_UI4:  
                        wprintf( L"%32s:\t 0x%0x\n", prop.lpwstrName, vt.uintVal );  
                        break;  
                    case VT_UI8:  
                        wprintf( L"%32s:\t 0x%x\n", prop.lpwstrName, vt.uhVal.QuadPart );  
                        break;  
                    case VT_BSTR:  
                        wprintf( L"%32s:\t %s\n", prop.lpwstrName, vt.bstrVal );  
                        break;  
                    case VT_UNKNOWN:  
                        wprintf( L"%32s:\t %p\n", prop.lpwstrName, vt.punkVal );  
                        break;  
                    case VT_SAFEARRAY:  
                        break;  
                    default:  
                       break;  
                }  
                VariantClear((VARIANTARG*) &vt);  
            }  
        }  
        pEnumProps->Release();  
    }  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (Debug Interface Access SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiasession::getenumtables –](../../debugger/debug-interface-access/idiasession-getenumtables.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [Idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)
