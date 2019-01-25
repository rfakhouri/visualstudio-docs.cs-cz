---
title: IEEDataStorage | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEEDataStorage
helpviewer_keywords:
- IEEDataStorage interface
ms.assetid: 704e932d-2325-410e-89c4-ce88c6ec19da
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a5d102a4a9cf7946e135ec8f6cdbff44015d3b47
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54782985"
---
# <a name="ieedatastorage"></a>IEEDataStorage
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní představuje pole bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEEDataStorage : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Chyba při vyhodnocování výrazu (EE) implementuje toto rozhraní představující pole bajtů (používané vizualizérů typů a načíst data prostřednictvím změny [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) rozhraní). EE obvykle implementuje toto rozhraní pro podporu externí vizualizéry.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Metody `IPropertyProxyEESide` rozhraní všechny vrátit toto rozhraní. Volání [GetPropertyProxy](../../../extensibility/debugger/reference/ipropertyproxyprovider-getpropertyproxy.md) získat [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md) rozhraní. Volání [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md) rozhraní získat [IPropertyProxyProvider](../../../extensibility/debugger/reference/ipropertyproxyprovider.md) rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 `IEEDataStorage` Rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)|Načte zadaný počet bajtů dat do zadané vyrovnávací paměti.|  
|[GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)|Získá počet bajtů dat, které jsou k dispozici.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je používá typ vizualizéru pro přístup k data ukládaná společností s určitým objektem. Data je považován za pole bajtů, což vizualizér typů s nimi manipulovat v dle svého je potřeba poskytnout uživateli.  
  
 Vlastní prohlížeč můžete také použít toto rozhraní v případě potřeby, i když vlastní prohlížeč by se používat vlastní rozhraní [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) nebo [GetStringChars](../../../extensibility/debugger/reference/idebugproperty3-getstringchars.md) (pro data orientovaná na řetězec).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [Vizualizér typů a vlastní prohlížeč](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)
