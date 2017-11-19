---
title: IDebugGenericFieldInstance::TypeArgumentCount | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TypeArgumentCount
- IDebugGenericFieldInstance::TypeArgumentCount
ms.assetid: e662c5ea-a5c1-478e-a268-5980dadffcd1
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ddaf2ff3323bb7e4e1da55eb1b8ad8cd8931f9c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebuggenericfieldinstancetypeargumentcount"></a>IDebugGenericFieldInstance::TypeArgumentCount
Vrátí číslo typu argumenty parametrů pro tuto instanci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT TypeArgumentCount(  
   ULONG32* pcArgs  
);  
```  
  
```csharp  
int TypeArgumentCount(  
   ref uint pcArgs  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcArgs`  
 [ve out] Počet argumentů parametr typu pro tuto instanci.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Například pokud seznamu\<int >, tato metoda vrátí hodnotu 1 a pokud seznamu\<int, float2 > Tato metoda vrátí hodnotu 2. Tato metoda vrátí hodnotu 0, pokud nejsou žádné argumenty typu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugGenericFieldInstance](../../../extensibility/debugger/reference/idebuggenericfieldinstance.md)