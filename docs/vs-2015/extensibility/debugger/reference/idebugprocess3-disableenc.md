---
title: IDebugProcess3::DisableENC | Dokumentace Microsoftu
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
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 528f1a6789b09bde6313cdd00fe0cd4974c6cf31
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672779"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProcess3::DisableENC](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess3-disableenc).  
  
Tato metoda explicitně zakáže upravit a pokračovat na tento proces (a všechny programy obsahuje). Dodavatel port. Tento vlastní port byste vždy vrátí `E_NOTIMPL`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DisableENC(  
   EncUnavailableReason reason  
);  
```  
  
```csharp  
   EncUnavailableReason reason  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `reason`  
 [in] Hodnota z [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
> [!NOTE]
>  Dodavatel port. Tento vlastní port byste vždy vrátí `E_NOTIMPL`.  
  
## <a name="remarks"></a>Poznámky  
 Jednou upravit a pokračovat je zakázaná pro proces, ho můžete znovu povolit pouze restartování procesu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)   
 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)

