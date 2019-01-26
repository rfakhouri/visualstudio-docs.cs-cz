---
title: IPropertyProxyEESide::InPlaceUpdateObject | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
helpviewer_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 15e2e3382484040be4117b355fb93f48788c7b18
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54952987"
---
# <a name="ipropertyproxyeesideinplaceupdateobject"></a>IPropertyProxyEESide::InPlaceUpdateObject
Aktualizuje data objektu s danou datový objekt a vrátí nový datový objekt reprezentující objektu nová data.  
  
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
 [in] [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objekt, který obsahuje nová data.  
  
 `dataOut`  
 [out] Vrátí nový `IEEDataStorage` objekt, který obsahuje data nahrazené.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda ve skutečnosti aktualizuje data objektu. Data ve vráceném [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objektu nemusí být stejné jako data v příchozí `IEEDataStorage` objektu, ale vráceného objektu musí odpovídat aktuální hodnota vlastnosti.  
  
 Příchozí datový objekt není většinou implementují moduly EE. Ale objekt vrácený touto metodou je vždy implementované EE, který umožňuje implementovat EE `IEEDataStorage` rozhraní na libovolné třídy je žádoucí.  
  
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md) metoda vytvoří datový objekt na základě příchozích dat objektu, ale nemá vliv na původní data vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [CreateReplacementObject](../../../extensibility/debugger/reference/ipropertyproxyeeside-createreplacementobject.md)