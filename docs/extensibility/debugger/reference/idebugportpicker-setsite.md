---
title: IDebugPortPicker::SetSite | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugPortPicker::SetSite
ms.assetid: 7319e187-adfe-4b3f-aec9-521356fb5a8a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: a307c2b387905706d229d7811f490f109f14c78f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportpickersetsite"></a>IDebugPortPicker::SetSite
Nastaví poskytovatele služeb.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetSite(  
   IServiceProvider * pSP  
);  
```  
  
```csharp  
public int SetSite(  
   IServiceProvider pSP  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pSP`  
 [v] Odkaz na rozhraní poskytovatele služeb.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda bude volána předtím, než se označují jako jiné metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortPicker](../../../extensibility/debugger/reference/idebugportpicker.md)