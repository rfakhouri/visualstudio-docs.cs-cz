---
title: Setnotificationforwaitcompletion – metoda | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a5d9bee2579cc3a93f657291551955f0c9b7565b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348584"
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion – metoda
Nastaví nebo vymaže stav bit TASK_STATE_WAIT_COMPLETION_NOTIFICATION.

 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **Sestavení:** mscorlib (v *mscorlib.dll*)

## <a name="syntax"></a>Syntaxe

```vb
internal void SetNotificationForWaitCompletion(bool enabled)
```

### <a name="parameters"></a>Parametry
 `enabled`

 `true` Chcete-li nastavit bit; `false` na Zrušit nastavení bitu.

## <a name="exceptions"></a>Výjimky

## <a name="remarks"></a>Poznámky
 Ladicí program nastaví tento bit ke kroku mimo tělo metody na asynchronní. Pokud `enabled` je `true`, tato metoda musí být volána pouze na úkol, který dosud nebyl dokončen. Když `enabled` je `false`, tuto metodu lze volat pro dokončené úlohy. V obou případech to by měla sloužit pouze pro příslib – vizuální styl úlohy.

## <a name="requirements"></a>Požadavky

## <a name="see-also"></a>Viz také:
- [Třída úlohy](../../extensibility/debugger/task-class-internal-members.md)