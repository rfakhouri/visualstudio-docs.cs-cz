---
title: Notifydebuggerofwaitcompletion – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4429b89be624960b787b51c3fa085f43e412889e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667338"
---
# <a name="notifydebuggerofwaitcompletion-method"></a>NotifyDebuggerOfWaitCompletion – metoda
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [notifydebuggerofwaitcompletion – metoda](https://docs.microsoft.com/visualstudio/extensibility/debugger/notifydebuggerofwaitcompletion-method).  
  
Zástupný symbol metoda použitá jako cíl zarážku ladicím programem. Tato metoda nesmí být vložená ani optimalizované.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>Poznámky  
 Všechny operace spojení s úlohami by měly volat tuto metodu, pokud je nastaven bit oznámení jejich ladicího programu.  
  
## <a name="requirements"></a>Požadavky  
  
## <a name="see-also"></a>Viz také  
 [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)

