---
title: IDebugReference2::SetReferenceType | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugReference2::SetReferenceType
helpviewer_keywords:
- IDebugReference2::SetReferenceType
ms.assetid: 5854a172-ea82-481c-97d9-c7fc16923d44
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a1afe99bddcb7932699538ba8388d8c1ea96d4cc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49839918"
---
# <a name="idebugreference2setreferencetype"></a>IDebugReference2::SetReferenceType
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví typ odkazu. Vyhrazeno pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT SetReferenceType (   
   REFERENCE_TYPE dwRefType  
);  
```  
  
```csharp  
int SetReferenceType (   
   enum_REFERENCE_TYPE dwRefType  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwRefType`  
 [in] Hodnota z [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md) výčet, který určuje typ odkazu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE_TYPE](../../../extensibility/debugger/reference/reference-type.md)

