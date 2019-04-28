---
title: IDebugCustomViewer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCustomViewer
helpviewer_keywords:
- IDebugCustomViewer interface
ms.assetid: 7aca27d3-c7b8-470f-b42c-d1e9d9115edd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5c576de860183353831eb9cc33293ead11123c59
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921774"
---
# <a name="idebugcustomviewer"></a>IDebugCustomViewer
Toto rozhraní umožňuje vyhodnocovače výrazů (EE) k zobrazení hodnoty vlastnosti v libovolné formát je nezbytné.

## <a name="syntax"></a>Syntaxe

```
IDebugCustomViewer : IUknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
EE implementuje toto rozhraní k zobrazení hodnoty vlastnosti ve vlastním formátu.

## <a name="notes-for-callers"></a>Poznámky pro volající
Volání do modelu COM `CoCreateInstance` funkce vytvoří instanci tohoto rozhraní. `CLSID` Předán `CoCreateInstance` získal z registru. Volání [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md) získá umístění v registru. Viz poznámky pro podrobnosti, stejně jako v příkladu.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
Toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[DisplayValue](../../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md)|Provede cokoli, co je nutné zobrazit danou hodnotou.|

## <a name="remarks"></a>Poznámky
Toto rozhraní se používá při hodnoty vlastnosti nelze zobrazit běžné způsoby – třeba index Mei tabulku dat nebo jiný typ komplexní vlastnost. Vlastní prohlížeč, jako je znázorněn `IDebugCustomViewer` rozhraní, se liší od typu vizualizéru, což je externí program pro zobrazení dat určitého typu bez ohledu na to, EE. EE implementuje vlastní prohlížeč, který je specifický pro tento EE. Uživatel vybere typu vizualizéru chcete použít, už to jsou vizualizér typů nebo vlastní prohlížeč. Zobrazit [Visualizing a zobrazení dat](../../../extensibility/debugger/visualizing-and-viewing-data.md) podrobnosti o tomto procesu.

Vlastní prohlížeč je registrován v stejným způsobem jako EE a proto vyžadují identifikátor GUID jazyka a dodavatele identifikátor GUID. Přesně metrikou (nebo název položky registru) znáte jenom EE. Tato metrika se vrátí v [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md) struktury, který je pak vrácen voláním [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md). Je hodnota uložená v metriku `CLSID` , který je předán do modelu COM `CoCreateInstance` funkci (viz příklad).

[Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) funkci `SetEEMetric`, je možné zaregistrovat vlastní prohlížeč. Najdete v části "Vyhodnocovače výrazů" registru `Debugging SDK Helpers` pro konkrétní registru klíče, které potřebuje vlastní prohlížeč. Všimněte si, že vlastní prohlížeč potřebuje pouze jednu metriku (který je definovaný EE implementátora), zatímco vyhodnocovače výrazů vyžaduje řadu předdefinovaných metrik.

Za normálních okolností vlastní prohlížeč poskytuje zobrazení jen pro čtení dat, protože [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) předaná rozhraní [položky DisplayValue](../../../extensibility/debugger/reference/idebugcustomviewer-displayvalue.md) nemá žádné metody při změně hodnoty vlastnosti s výjimkou jako řetězec. Aby bylo možné podporovat změnu libovolného bloků dat, EE implementuje vlastní rozhraní pro stejný objekt, který implementuje `IDebugProperty3` rozhraní. Toto vlastní rozhraní by pak poskytují metody potřeba změnit libovolné blok dat.

## <a name="requirements"></a>Požadavky
Záhlaví: msdbg.h

Obor názvů: Microsoft.VisualStudio.Debugger.Interop

Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="example"></a>Příklad
Tento příklad ukazuje, jak získat z vlastnosti první vlastní prohlížeč, pokud tuto vlastnost má všechny vlastních prohlížečů.

```cpp
IDebugCustomViewer *GetFirstCustomViewer(IDebugProperty2 *pProperty)
{
    // This string is typically defined globally.  For this example, it
    // is defined here.
    static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0Exp";
    IDebugCustomViewer *pViewer = NULL;
    if (pProperty != NULL) {
        CComQIPtr<IDebugProperty3> pProperty3(pProperty);
        if (pProperty3 != NULL) {
            HRESULT hr;
            ULONG viewerCount = 0;
            hr = pProperty3->GetCustomViewerCount(&viewerCount);
            if (viewerCount > 0) {
                ULONG viewersFetched = 0;
                DEBUG_CUSTOM_VIEWER viewerInfo = { 0 };
                hr = pProperty3->GetCustomViewerList(0,
                                                     1,
                                                     &viewerInfo,
                                                     &viewersFetched);
                if (viewersFetched == 1) {
                    CLSID clsidViewer = { 0 };
                    CComPtr<IDebugCustomViewer> spCustomViewer;
                    // Get the viewer's CLSID from the registry.
                    ::GetEEMetric(viewerInfo.guidLang,
                                  viewerInfo.guidVendor,
                                  viewerInfo.bstrMetric,
                                  &clsidViewer,
                                  strRegistrationRoot);
                    if (!IsEqualGUID(clsidViewer,GUID_NULL)) {
                        // Instantiate the custom viewer.
                        spCustomViewer.CoCreateInstance(clsidViewer);
                        if (spCustomViewer != NULL) {
                            pViewer = spCustomViewer.Detach();
                        }
                    }
                }
            }
        }
    }
    return(pViewer);
}
```

## <a name="see-also"></a>Viz také
- [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)
- [GetCustomViewerList](../../../extensibility/debugger/reference/idebugproperty3-getcustomviewerlist.md)
- [Pomocníci sad SDK pro ladění](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
