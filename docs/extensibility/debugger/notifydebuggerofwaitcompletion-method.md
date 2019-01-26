---
title: Notifydebuggerofwaitcompletion – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 29657a85b72fa57f37a3932465b5aeb874e9a672
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55012388"
---
# <a name="notifydebuggerofwaitcompletion-method"></a>Notifydebuggerofwaitcompletion – metoda
Zástupný symbol metoda použitá jako cíl zarážku ladicím programem. Tato metoda nesmí být vložená ani optimalizované.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v *mscorlib.dll*)  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>Poznámky  
 Všechny operace spojení s úlohami by měly volat tuto metodu, pokud je nastaven bit oznámení jejich ladicího programu.  
  
## <a name="requirements"></a>Požadavky  
  
## <a name="see-also"></a>Viz také:  
 [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)