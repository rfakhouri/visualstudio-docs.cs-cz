---
title: IDebugPortSupplier3::EnumPersistedPorts | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 944159ead89166c8452775bd6522a7c441094ad0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68188195"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda načte objekt, který umožňuje výčet seznamu trvalých porty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `PortNames`  
 [in] A [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) strukturu, která obsahuje seznam názvů port pro vyhledání a vrácení mezi trvalý porty. Vrátí se pouze ty trvalý porty s těmito názvy.  
  
 `ppEnum`  
 [out] Objekt, který implementuje [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Trvalé porty jsou načteny při dodavatele portu je vytvořena instance a uložily v době, kdy je zničen dodavatele portu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)
