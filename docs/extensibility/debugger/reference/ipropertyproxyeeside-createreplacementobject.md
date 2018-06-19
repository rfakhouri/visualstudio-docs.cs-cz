---
title: IPropertyProxyEESide::CreateReplacementObject | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IPropertyProxyEESide::CreateReplacementObject
helpviewer_keywords:
- IPropertyProxyEESide::CreateReplacementObject
ms.assetid: 0cfe79b8-c3f1-48b0-a225-e39dee2c92fe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56e5001d7abd498982361a51d0386db4b2624cf7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135590"
---
# <a name="ipropertyproxyeesidecreatereplacementobject"></a>IPropertyProxyEESide::CreateReplacementObject
Vytvoří kopii datový objekt specifické pro vyhodnocení výrazu (EE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateReplacementObject(  
   IEEDataStorage*  dataIn,  
   IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int CreateReplacementObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dataIn`  
 [v] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt, který obsahuje data, které se mají zkopírovat.  
  
 `dataOut`  
 [out] Vrátí novou `IEEDataStorage` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je uvedena [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objektu, který představuje pole bajtů. Tato příchozí datový objekt není obvykle implementované EE. Však tato metoda vrátí objekt vždy implementované EE, která umožní implementace EE `IEEDataStorage` rozhraní na jakémkoli třídy se požaduje.  
  
 Všimněte si, že data zadaná příchozí `IEEDataStorage` objekt musí být stejná data v odchozích `IEEDataStorage` objektu.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)