---
title: IDebugPointerObject::Dereference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPointerObject::Dereference
helpviewer_keywords: IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 3e743f5a312e437ca48a5e36fb202783f41b934d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
Získá objekt ukazuje.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwIndex`  
 [v] Ukazuje jednoduchý bajtů posun od začátku objektu.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující objekt ukazuje plus posun, pokud existuje.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby. Vrátí E_FAIL, pokud tento objekt neodkazuje na jiný objekt.  
  
## <a name="remarks"></a>Poznámky  
 Objekt, který ukazuje může být jednoduchého typu nebo typu složitější například třídu nebo strukturu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)