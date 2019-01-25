---
title: IDebugField::GetAddress | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugField::GetAddress
helpviewer_keywords:
- IDebugField::GetAddress method
ms.assetid: 6981bf03-66ef-4bf9-87ea-f6c9624486cb
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 518133af302b5082da85cdf6388e83dda649743e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54755782"
---
# <a name="idebugfieldgetaddress"></a>IDebugField::GetAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda načte adresa pole pro ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetAddress(   
   IDebugAddress** ppAddress  
);  
```  
  
```csharp  
int GetAddress(  
   out IDebugAddress ppAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppAddress`  
 [out] Vrátí adresu jako [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)
