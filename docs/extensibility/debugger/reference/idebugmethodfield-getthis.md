---
title: IDebugMethodField::GetThis | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugMethodField::GetThis
helpviewer_keywords:
- IDebugMethodField::GetThis method
ms.assetid: cc235bea-e909-4d8c-ab54-936736c803fc
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: af534ee57a68158e3f909ba69a1771a5073320e1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmethodfieldgetthis"></a>IDebugMethodField::GetThis
Získá `this` (`Me` v [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]) ukazatele objektu, který obsahuje metodu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetThis(   
   IDebugClassField** ppClass  
);  
```  
  
```csharp  
int GetThis(  
   out IDebugClassField ppClass  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppClass`  
 [out] Vrátí [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objekt reprezentující ukazatel "this".  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Objektově orientované jazyky má obvykle předpokládané ukazatel na aktuální instance třídy. To se označuje jako `this` v jazyce C# nebo C++ a jako `Me` v [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)].  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)