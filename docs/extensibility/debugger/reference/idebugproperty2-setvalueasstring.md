---
title: IDebugProperty2::SetValueAsString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProperty2::SetValueAsString
helpviewer_keywords:
- IDebugProperty2::SetValueAsString
ms.assetid: 9e6a5054-41b7-4223-b509-b93689d366a5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1fb87f1ad075c0bae10c4d154b2c0e0fa2ceb999
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugproperty2setvalueasstring"></a>IDebugProperty2::SetValueAsString
Nastaví hodnotu vlastnosti ze zadaného řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetValueAsString (   
   LPCOLESTR pszValue,  
   UINT      nRadix,  
   DWORD     dwTimeout  
);  
```  
  
```csharp  
int SetValueAsString (   
   string pszValue,  
   uint   nRadix,  
   uint   dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszValue`  
 [v] Řetězec obsahující nastavit hodnotu.  
  
 `nRadix`  
 [v] Základ – který se má použít při interpretaci všechny číselné informace. To může být 0, budou se pokusí zjistit základ – automaticky.  
  
 `dwTimeout`  
 [v] Určuje maximální dobu v milisekundách pro čekání před návratem od této metody. Použití `INFINITE` čekání po neomezenou dobu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny další možné hodnoty.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Řetězec nelze převést na hodnotu vlastnosti, nebo nelze nastavit hodnotu vlastnosti.|  
|`E_SETVALUE_VALUE_IS_READONLY`|Vlastnost je jen pro čtení.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)