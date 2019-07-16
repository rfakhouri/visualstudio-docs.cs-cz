---
title: IPropertyProxyEESide::InPlaceUpdateObject | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
helpviewer_keywords:
- IPropertyProxyEESide::InPlaceUpdateObject
ms.assetid: abf89411-1853-4f23-b244-d5e0afa197b1
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c91497815dd18dc138b2eadc462c43785830a033
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199512"
---
# <a name="ipropertyproxyeesideinplaceupdateobject"></a>IPropertyProxyEESide::InPlaceUpdateObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Aktualizuje data objektu s danou datový objekt a vrátí nový datový objekt reprezentující objektu nová data.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
