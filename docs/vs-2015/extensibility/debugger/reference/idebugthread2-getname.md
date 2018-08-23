---
title: IDebugThread2::GetName | Dokumentace Microsoftu
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
- IDebugThread2::GetName
helpviewer_keywords:
- IDebugThread2::GetName
ms.assetid: eec54b8f-4a0e-4919-b0f9-81d4bd1e0b6f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8bd570c2610a20c3647e530af2bc7b9f916adbe
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633453"
---
# <a name="idebugthread2getname"></a>IDebugThread2::GetName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugThread2::GetName](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugthread2-getname).  
  
Získá název vlákna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetName (   
   BSTR* pbstrName  
);  
```  
  
```csharp  
int GetName (   
   out string pbstrName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrName`  
 [out] Vrátí název vlákna.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Načíst název je vždy název, který je možné zobrazit a popisuje tento název vlákna. Název vlákna mohou být odvozen od za běhu architektury, že podporuje s názvem vláken, nebo může být název odvozený z ladicího stroje. Alternativně lze nastavit název vlákna voláním [setthreadname –](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Setthreadname –](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)

