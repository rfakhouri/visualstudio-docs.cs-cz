---
title: Idebugsyncoperation – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugSyncOperation interface
ms.assetid: 8d714492-1836-462c-980a-c99e91a2c81b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3724ad50771ca49460e130bf93ebc244681bd782
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349597"
---
# <a name="idebugsyncoperation-interface"></a>IDebugSyncOperation – rozhraní
Povoluje skriptovací stroj abstraktní operace (například vyhodnocení výrazu), kterou je potřeba provést v průběhu vnořené v konkrétní vlákno blokované. Rozhraní také poskytuje mechanismus pro zrušení operace reagovat.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugSyncOperation` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugSyncOperation::GetTargetThread](../../winscript/reference/idebugsyncoperation-gettargetthread.md)|Vrátí vlákna aplikace cíl této synchronní operace.|  
|[IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)|Synchronní operace provede a vrátí.|  
|[IDebugSyncOperation::InProgressAbort](../../winscript/reference/idebugsyncoperation-inprogressabort.md)|Zruší probíhající operace v jiném vlákně.|