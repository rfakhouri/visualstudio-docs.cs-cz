---
title: IDebugProgram2::CanDetach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::CanDetach
helpviewer_keywords: IDebugProgram2::CanDetach
ms.assetid: dcd9ab6c-49e5-447e-aa7c-89f571f4a052
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a3a057e0f2f735f18076c166eff5d62655493b43
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprogram2candetach"></a>IDebugProgram2::CanDetach
Určuje, pokud modul ladění (DE), můžete odpojení od programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanDetach(  
   void  
);  
```  
  
```csharp  
int CanDetach();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud můžete odpojit, vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `S_FALSE` Pokud DE nelze odpojit programu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)