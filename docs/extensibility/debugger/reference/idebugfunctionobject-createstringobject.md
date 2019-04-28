---
title: IDebugFunctionObject::CreateStringObject | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugFunctionObject::CreateStringObject
helpviewer_keywords:
- IDebugFunctionObject::CreateStringObject method
ms.assetid: fd6070ab-07d4-4ea1-8d71-b16592d6f1a7
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0dd79223d3b51195e9f45490cc8aa95c10aca8e8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62919437"
---
# <a name="idebugfunctionobjectcreatestringobject"></a>IDebugFunctionObject::CreateStringObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vytvoří objekt řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CreateStringObject(   
   LPCOLESTR      pcstrString,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateStringObject(  
   string      pcstrString,   
   out IDebugObject ppOjbect  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcstrString`  
 [in] Řetězcová hodnota pro objekt řetězce.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt, který reprezentuje objekt nově vytvořeného řetězce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volejte tuto metodu za účelem vytvoření objektu, který představuje řetězec, který je parametr funkce, která je reprezentována [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
