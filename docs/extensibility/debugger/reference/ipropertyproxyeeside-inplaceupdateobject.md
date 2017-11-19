---
title: IPropertyProxyEESide::InPlaceUpdateObject | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IPropertyProxyEESide::InPlaceUpdateObject
helpviewer_keywords: IPropertyProxyEESide::InPlaceUpdateObject
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 723a24a0a0ce21c7817b5dfcef2680808f9319a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ipropertyproxyeesideinplaceupdateobject"></a>IPropertyProxyEESide::InPlaceUpdateObject
Aktualizuje data objektu s daným objektem daná data a vrátí nové datový objekt reprezentující objektu nová data.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT InPlaceUpdateObject(  
   [in] IEEDataStorage*   dataIn,  
   [out] IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int InPlaceUpdateObject(  
   IEEDataStorage     dataIn,  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dataIn`  
 [v] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt obsahující nová data.  
  
 `dataOut`  
 [out] Vrátí novou `IEEDataStorage` objekt obsahující nahrazené data.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda ve skutečnosti aktualizuje data objektu. Data ve vráceném [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt nemusí být stejný jako data v příchozích `IEEDataStorage` objektu, ale vráceného objektu musí odráží aktuální hodnotu vlastnosti.  
  
 Příchozí datový objekt není obvykle implementované EE. Však tato metoda vrátí objekt vždy implementované EE, která umožní implementace EE `IEEDataStorage` rozhraní na jakémkoli třídy se požaduje.  
  
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) metoda vytvoří objekt dat podle příchozí datový objekt, ale nemá vliv na vlastnosti původní data.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)