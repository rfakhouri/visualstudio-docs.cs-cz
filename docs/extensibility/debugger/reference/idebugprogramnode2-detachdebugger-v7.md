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
ms.openlocfilehash: 84110c4e7d6a3e940df587811c24d4316f786cf4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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