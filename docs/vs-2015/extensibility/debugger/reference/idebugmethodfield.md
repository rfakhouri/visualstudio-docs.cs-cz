---
title: IDebugMethodField | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMethodField
helpviewer_keywords:
- IDebugMethodField interface
ms.assetid: a7dc9030-fc98-4cf1-b943-37a4003300b6
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4d7f6fc12a3366200ca1e14c0e2d55f4f6d797f5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694352"
---
# <a name="idebugmethodfield"></a>IDebugMethodField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní je popsán způsob.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMethodField : IDebugContainerField  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje na stejný objekt, který implementuje toto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní. Toto rozhraní je specializací, který představuje metodu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) získat z tohoto rozhraní [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, pokud [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) vrátí `FIELD_TYPE_METHOD`. Kromě toho, metody, [GetPropertyGetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertygetter.md), [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md), a [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md), všechny vrácené `IDebugMethodField` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) a [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)|Vytvoří čítač pro parametry metody.|  
|[GetThis](../../../extensibility/debugger/reference/idebugmethodfield-getthis.md)|Získá ukazatel "Tento" objekt obsahující metodu.|  
|[EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)|Vytvoří čítač pro všechny místní proměnné metody.|  
|[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)|Vytvoří čítač pro vybrané místní proměnné metody.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugmethodfield-iscustomattributedefined.md)|Určuje, zda konkrétní vlastního atributu je definována.|  
|[EnumStaticLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumstaticlocals.md)|Vytvoří čítač pro statické lokální proměnné metody.|  
|[GetGlobalContainer](../../../extensibility/debugger/reference/idebugmethodfield-getglobalcontainer.md)|Získá kontejner globální metody.|  
|[EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)|Vytvoří čítač pro typ každého argumentu potřebné k volání metody.|  
  
## <a name="remarks"></a>Poznámky  
 Metoda může obsahovat parametry, stejně jako lokální proměnné.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
