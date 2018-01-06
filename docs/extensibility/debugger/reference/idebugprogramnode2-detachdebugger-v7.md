---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
ms.assetid: d2d4b78e-a2dd-4217-97a6-ab648fd2ee2f
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: af2f9e5851e53c86fb5466e7fc2cdfe515b5fb21
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7
ZASTARALÉ. NEPOUŽÍVEJTE.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DetachDebugger_V7 (   
   void   
);  
```  
  
```csharp  
int DetachDebugger_V7 ();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Implementace musí vracet vždycky `E_NOTIMPL`.  
  
## <a name="remarks"></a>Poznámky  
  
> [!WARNING]
>  Od [!INCLUDE[vsprvslong](../../../code-quality/includes/vsprvslong_md.md)], tato metoda se již nepoužívá a musí vracet vždycky `E_NOTIMPL`.  
  
 Tato metoda je volána, když se neočekávaně ukončí ladicího programu. Když tato metoda je volána, DE by mělo být obnoveno program, jakoby z něho odpojený od uživatele. Žádné další události ladění by měly být odeslány. Program musí být ve stavu, kdy je připojitelné z jiné instance systému ladicího programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)