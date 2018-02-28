---
title: IDebugReference2::SetValueAsString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugReference2::SetValueAsString
helpviewer_keywords:
- IDebugReference2::SetValueAsString
ms.assetid: 9a508ced-fd54-44f5-bb42-ec15c80384d7
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 8a5c5bca596ebf463841c0e2dcb1c6ba1cce71b2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugreference2setvalueasstring"></a>IDebugReference2::SetValueAsString
Nastaví hodnotu odkaz z řetězce. Vyhrazeno pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetValueAsString (   
   LPCOLESTR pszValue,  
   DWORD     dwRadix,  
   DWORD     dwTimeout  
);  
```  
  
```csharp  
int SetValueAsString (   
   string pszValue,  
   uint   dwRadix,  
   uint   dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszValue`  
 [v] Hodnota jako řetězec.  
  
 `dwRadix`  
 [v] Základ – který se má použít při formátování všechny číselné informace.  
  
 `dwTimeout`  
 [v] Maximální doba v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí hodnotu `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)