---
title: IDiaImageData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData interface
ms.assetid: b696f350-fc08-4352-9287-a15e87512c1e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1e3dd8c395c59bc3255c1c9ee55837466c1cef7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62828508"
---
# <a name="idiaimagedata"></a>IDiaImageData
Poskytuje podrobnosti o základní posuny umístění a paměti modulu nebo image.

## <a name="syntax"></a>Syntaxe

```
IDiaImageData : IUnknown
```

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
V následující tabulce jsou uvedeny metody objektu `IDiaImageData`.

|Metoda|Popis|
|------------|-----------------|
|[IDiaImageData::get_relativeVirtualAddress](../../debugger/debug-interface-access/idiaimagedata-get-relativevirtualaddress.md)|Získá umístění ve virtuální paměti modulu vzhledem k aplikaci.|
|[IDiaImageData::get_virtualAddress](../../debugger/debug-interface-access/idiaimagedata-get-virtualaddress.md)|Získá umístění ve virtuální paměti bitové kopie.|
|[IDiaImageData::get_imageBase](../../debugger/debug-interface-access/idiaimagedata-get-imagebase.md)|Získá umístění v paměti, kde by měla být založena na obrázku.|

## <a name="remarks"></a>Poznámky
Některé datové proudy debug (XDATA, PDATA) obsahují kopie dat také uložených v bitové kopii. Tyto datové objekty je možné zadávat dotazy pro datový proud stream `IDiaImageData` rozhraní. V tomto tématu podrobnosti v části "Poznámky pro volající".

## <a name="notes-for-callers"></a>Poznámky pro volající
Získat po zavolání tohoto rozhraní `QueryInterface` na [idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md) objektu. Podporu streamuje Všimněte si, že ne všechny ladění `IDiaImageData` rozhraní. Například aktuálně podporují pouze XDATA a PDATA datové proudy `IDiaImageData` rozhraní.

## <a name="example"></a>Příklad
Tento příklad vyhledá všechny datové proudy debug pro datový proud, který podporuje `IDiaImageData` rozhraní. Pokud není nalezen takový stream, zobrazí se nějaké informace týkající se tohoto datového proudu.

```C++
void ShowImageData(IDiaSession *pSession)
{
    if (pSession != NULL)
    {
        CComPtr<IDiaEnumDebugStreams> pStreamsList;
        HRESULT hr;

        hr = pSession->getEnumDebugStreams(&pStreamsList);
        if (SUCCEEDED(hr))
        {
            LONG numStreams = 0;
            hr = pStreamsList->get_Count(&numStreams);
            if (SUCCEEDED(hr))
            {
                ULONG fetched = 0;
                for (LONG i = 0; i < numStreams; i++)
                {
                    CComPtr<IDiaEnumDebugStreamData> pStream;
                    hr = pStreamsList->Next(1,&pStream,&fetched);
                    if (fetched == 1)
                    {
                        CComPtr<IDiaImageData> pImageData;
                        hr = pStream->QueryInterface(__uuidof(IDiaImageData),
                                                     (void **)&pImageData);
                        if (SUCCEEDED(hr))
                        {
                            CComBSTR name;
                            hr = pStream->get_name(&name);
                            if (SUCCEEDED(hr))
                            {
                                wprintf(L"Stream %s:\n",(BSTR)name);
                            }
                            else
                            {
                                wprintf(L"Failed to get name of stream\n");
                            }

                            ULONGLONG imageBase = 0;
                            if (pImageData->get_imageBase(&imageBase) == S_OK)
                            {
                                wprintf(L"  image base = 0x%0I64x\n",imageBase);
                            }

                            DWORD relVA = 0;
                            if (pImageData->get_relativeVirtualAddress(&relVA) == S_OK)
                            {
                                wprintf(L"  relative virtual address = 0x%08lx\n",relVA);
                            }

                            ULONGLONG va = 0;
                            if (pImageData->get_virtualAddress(&va) == S_OK)
                            {
                                wprintf(L"  virtual address = 0x%0I64x\n", va);
                            }
                        }
                    }
                }
            }
        }
    }
}
```

## <a name="requirements"></a>Požadavky
Záhlaví: Dia2.h

Knihovna: diaguids.lib

DLL: msdia80.dll

## <a name="see-also"></a>Viz také
- [Rozhraní (Přístup k rozhraní ladění SDK)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
