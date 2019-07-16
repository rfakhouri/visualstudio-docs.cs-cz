---
title: IDebugEngine2::EnumPrograms | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2::EnumPrograms
helpviewer_keywords:
- IDebugEngine2::EnumPrograms
ms.assetid: 56bf98eb-beec-4e5f-9ebe-46c922e54c56
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: dc004de59b6ae219f47dc0874913c8e6e6ceb0f5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68195994"
---
# <a name="idebugengine2enumprograms"></a>IDebugEngine2::EnumPrograms
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Načte seznam všech programů, které jsou právě laděny ve ladicího stroje (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumPrograms(   
   IEnumDebugPrograms2** ppEnum  
);  
```  
  
```csharp  
int EnumPrograms(   
   out IEnumDebugPrograms2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md) objekt, který obsahuje seznam všech programů, které jsou právě laděny ve Zavedenými.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IEnumDebugPrograms2](../../../extensibility/debugger/reference/ienumdebugprograms2.md)
