---
title: IDebugStackFrame2::GetInfo | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugStackFrame2::GetInfo
helpviewer_keywords:
- IDebugStackFrame2::GetInfo
ms.assetid: 19c6870b-b94e-453c-bf19-82ce95b79d26
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ac60d775e6ae10d3e689194bb83e433c07165bfa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631597"
---
# <a name="idebugstackframe2getinfo"></a>IDebugStackFrame2::GetInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugStackFrame2::GetInfo](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstackframe2-getinfo).  
  
Získá popis rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetInfo (   
   FRAMEINFO_FLAGS dwFieldSpec,  
   UINT            nRadix,  
   FRAMEINFO*      pFrameInfo  
);  
```  
  
```csharp  
int GetInfo (   
   enum_FRAMEINFO_FLAGS dwFieldSpec,  
   uint                 nRadix,  
   FRAMEINFO[]          pFrameInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwFieldSpec`  
 [in] Kombinace příznaků z [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) výčet, který určuje, jaké pole `pFrameInfo` parametr mají být vyplněna.  
  
 `nRadix`  
 [in] Základ, který se má použít v jakékoli číselné informace o formátování.  
  
 `pFrameInfo`  
 [out] A [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) struktura, která se vyplní popis rámce zásobníku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)

