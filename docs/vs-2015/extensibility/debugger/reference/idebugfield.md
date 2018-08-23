---
title: IDebugField | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugField
helpviewer_keywords:
- IDebugField interface
ms.assetid: adecdd1c-b1b9-4027-92da-74cbe910636f
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26bcd1d2a85e547aa733c6a8e7d906a822d0fdc0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678759"
---
# <a name="idebugfield"></a>IDebugField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugField](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfield).  
  
Toto rozhraní představuje pole, to znamená, popis symbol nebo typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugField : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Poskytovatel symbolů implementuje toto rozhraní jako základní třída pro všechna pole.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je základní třída pro všechna pole. Na základě návratové hodnoty [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md), toto rozhraní může vrátit více specializované rozhraní pomocí [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3). Kromě toho mnoho rozhraní vrátit `IDebugField` objekty z různých metod.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugField`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)|Získá zobrazitelný informací o symbolu nebo typu.|  
|[GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)|Získá druh typu pole.|  
|[GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)|Získá typ pole.|  
|[GetContainer](../../../extensibility/debugger/reference/idebugfield-getcontainer.md)|Získá kontejner pole.|  
|[GetAddress](../../../extensibility/debugger/reference/idebugfield-getaddress.md)|Získá adresu pole.|  
|[GetSize](../../../extensibility/debugger/reference/idebugfield-getsize.md)|Získá velikost pole, v bajtech.|  
|[GetExtendedInfo](../../../extensibility/debugger/reference/idebugfield-getextendedinfo.md)|Získá rozšířené informace o pole.|  
|[rovno](../../../extensibility/debugger/reference/idebugfield-equal.md)|Porovná dvě pole.|  
|[GetTypeInfo](../../../extensibility/debugger/reference/idebugfield-gettypeinfo.md)|Získá typ nezávislé na informace o symbolu nebo typu.|  
  
## <a name="remarks"></a>Poznámky  
 Jazyk C odpovídá typu `typedef`.  
  
 V následujícím příkladu jazyka C++ `weather` je typem třídy a `sunny` a `stormy` jsou symboly:  
  
```cpp#  
class weather;  
weather sunny;  
weather stormy;  
```  
  
 Zda symbol představuje pole nebo typu se dají určit pomocí volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) a podíváte [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) výsledek. Pokud `FIELD_KIND_TYPE` bit nastaven, pole je typ a pokud `FIELD_KIND_SYMBOL` bit nastaven, je třeba otazník.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní poskytovatele symbolů ](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)

