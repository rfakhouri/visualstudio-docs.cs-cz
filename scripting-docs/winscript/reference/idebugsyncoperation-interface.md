---
title: Idebugsyncoperation – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 7184be62a8ad2b65e81d1ad82f01f0ce3f4668c5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63004893"
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