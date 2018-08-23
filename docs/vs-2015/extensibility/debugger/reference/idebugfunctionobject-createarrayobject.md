---
title: IDebugFunctionObject::CreateArrayObject | Dokumentace Microsoftu
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
- IDebugFunctionObject::CreateArrayObject
helpviewer_keywords:
- IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f996e7b58150f1340bf7a47790696a54f4cbc7fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631470"
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugFunctionObject::CreateArrayObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject-createarrayobject).  
  
Vytvoří objekt typu pole. Toto pole může obsahovat buď primitivní nebo hodnot instance objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ot`  
 [in] Určuje hodnotu z [OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md) výčet určující typ nového objektu pole.  
  
 `pClassField`  
 [in] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objekt představující třídu objektu, pokud vytvoření instance hodnoty pole objektu. Při vytváření pole objektů primitivní, je tento parametr hodnotu null.  
  
 `dwRank`  
 [in] Pořadí nebo počet rozměrů pole.  
  
 `dwDims`  
 [in] Velikost každého rozměru pole.  
  
 `dwLowBounds`  
 [in] Počátek každé dimenze (obvykle 0 nebo 1).  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt představující nově vytvořené pole. Ve skutečnosti se jedná [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Volejte tuto metodu za účelem vytvoření objektu, který představuje funkci, která je reprezentována jako parametr pole [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

