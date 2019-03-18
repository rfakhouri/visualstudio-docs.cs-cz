---
title: IDebugAsyncOperation Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugAsyncOperation interface
ms.assetid: ebb2ea75-1443-4d8a-812d-171a166f5f9d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 820ecc40924ace4153b76f46c8b8fd1603512ebb
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150813"
---
# <a name="idebugasyncoperation-interface"></a>IDebugAsyncOperation – rozhraní
Správce ladění procesu implementuje `IDebugAsyncOperation` rozhraní. Zavolá jazyk modul `IDebugApplication::CreateAsyncDebugOperation` metodu k získání odkazu na toto rozhraní. Můžete použít modul jazyka `IDebugAsyncOperation` rozhraní k poskytování asynchronní přístup k ladění synchronní operace.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugAsyncOperation` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugAsyncOperation::GetSyncDebugOperation](../../winscript/reference/idebugasyncoperation-getsyncdebugoperation.md)|Vrátí synchronní ladění operace spojené s tímto objektem.|  
|[IDebugAsyncOperation::Start](../../winscript/reference/idebugasyncoperation-start.md)|Způsobí, že na začátek asynchronní operace.|  
|[IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)|Slouží ke zrušení operace.|  
|[IDebugAsyncOperation::QueryIsComplete](../../winscript/reference/idebugasyncoperation-queryiscomplete.md)|Určuje, pokud byla dokončena operace ladění.|  
|[IDebugAsyncOperation::GetResult](../../winscript/reference/idebugasyncoperation-getresult.md)|Poskytuje návratovou hodnotu a parametr vrácený objekt z ladění synchronní operace.|