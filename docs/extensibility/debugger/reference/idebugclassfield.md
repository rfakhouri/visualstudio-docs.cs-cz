---
title: IDebugClassField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField
helpviewer_keywords:
- IDebugClassField interface
ms.assetid: 49358cbc-8973-4862-9dcc-79b1248e6712
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 681a426cc95ead710fbb8dab151bb5a23b6f1206
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703848"
---
# <a name="idebugclassfield"></a>IDebugClassField
Toto rozhraní představuje třídu jako typ.

## <a name="syntax"></a>Syntaxe

```
IDebugClassField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Poskytovatel symbolů implementuje na stejný objekt, který implementuje toto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní. Toto rozhraní je specializací, který představuje typ třídy.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Počet rozhraní mají metody, které můžou vrátit, včetně rozhraní [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md), [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md), a [IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md). Můžete také použít [QueryInterface](/cpp/atl/queryinterface) získat z tohoto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda vrátí příznak `FIELD_TYPE_CLASS`.

## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, toto rozhraní implementuje následující:

|Metoda|Popis|
|------------|-----------------|
|[EnumBaseClasses](../../../extensibility/debugger/reference/idebugclassfield-enumbaseclasses.md)|Vytvoří čítač pro základní třídy této třídy.|
|[DoesInterfaceExist](../../../extensibility/debugger/reference/idebugclassfield-doesinterfaceexist.md)|Určuje, zda určité rozhraní je definována v třídě.|
|[EnumNestedClasses](../../../extensibility/debugger/reference/idebugclassfield-enumnestedclasses.md)|Vytvoří čítač pro vnořené třídy této třídy.|
|[GetEnclosingClass](../../../extensibility/debugger/reference/idebugclassfield-getenclosingclass.md)|Získá třídu, která obklopuje této třídy.|
|[EnumInterfacesImplemented](../../../extensibility/debugger/reference/idebugclassfield-enuminterfacesimplemented.md)|Vytvoří čítač pro rozhraní implementována touto třídou.|
|[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)|Vytvoří čítač pro konstruktory této třídy.|
|[GetDefaultIndexer](../../../extensibility/debugger/reference/idebugclassfield-getdefaultindexer.md)|Získá název výchozímu indexeru.|
|[EnumNestedEnums](../../../extensibility/debugger/reference/idebugclassfield-enumnestedenums.md)|Vytvoří čítač pro vnořené čítačů této třídy.|

## <a name="requirements"></a>Požadavky
 Záhlaví: sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Viz také
- [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)