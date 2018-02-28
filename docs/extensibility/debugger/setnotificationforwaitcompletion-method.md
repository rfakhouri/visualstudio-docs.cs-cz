---
title: Metoda SetNotificationForWaitCompletion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: f5e35933e59fb4d8ff9f13db4bef8c23891bac2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion – metoda
Nastaví nebo vymaže bit TASK_STATE_WAIT_COMPLETION_NOTIFICATION stavu.  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>Parametry  
 `enabled`  
  
 `true`Chcete-li nastavit bit; `false` na nenastavené bitu.  
  
## <a name="exceptions"></a>Výjimky  
  
## <a name="remarks"></a>Poznámky  
 Ladicí program nastaví tento bit ke kroku mimo asynchronní metoda textu. Pokud `enabled` je `true`, tato metoda musí být volána pouze na úkolu, který dosud nebyl dokončen. Pokud `enabled` je `false`, tato metoda může být volána na dokončené úlohy. V obou případech ho by měl použít pouze pro úlohy promise stylu.  
  
## <a name="requirements"></a>Požadavky  
  
## <a name="see-also"></a>Viz také  
 [Task – třída](../../extensibility/debugger/task-class-internal-members.md)