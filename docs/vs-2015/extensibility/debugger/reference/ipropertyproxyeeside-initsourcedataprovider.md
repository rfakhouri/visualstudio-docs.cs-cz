---
title: IPropertyProxyEESide::InitSourceDataProvider | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::InitSourceDataProvider
helpviewer_keywords:
- IPropertyProxyEESide::InitSourceDataProvider
ms.assetid: 5156f593-5052-4e3a-9d02-081916fb342d
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f5e067a0b93656eecd1fe47d5b192c70916b672d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199503"
---
# <a name="ipropertyproxyeesideinitsourcedataprovider"></a>IPropertyProxyEESide::InitSourceDataProvider
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Inicializuje zdrojová data pro tento objekt a vrátí objekt, který obsahuje původní data.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT InitSourceDataProvider(  
   IEEDataStorage** dataOut  
);  
```  
  
```csharp  
int InitSourceDataProvider(  
   out IEEDataStorage dataOut  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dataOut`  
 [out] Vrátí [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) objektu  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda provádí všechno, co je potřeba inicializovat objekt, abyste ji mohli vrátit [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) rozhraní pro data objektu. To umožňuje objektu data k zobrazení a, pokud je povoleno, změnil(a) vizualizér typů.  
  
## <a name="see-also"></a>Viz také  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
