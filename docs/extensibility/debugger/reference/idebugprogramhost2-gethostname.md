---
title: IDebugProgramHost2::GetHostName | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramHost2::GetHostName
helpviewer_keywords: IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 17cb56589f9f045b2f478626c47857d5c951494c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
Získá název, popisný název nebo název souboru proces hostování tohoto programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```csharp  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwType`  
 [v] Hodnota z [GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) výčtu.  
  
 `pbstrHostName`  
 [out] Vrátí název požadovaného hostitelského procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 V typické implementace této metody `dwType` parametr je ignorován a je vrácen popisný název hostitele počítače. Další možné implementace je předat `dwType` parametr pro volání [gethostname –](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) metoda získat název.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [Gethostname –](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)