---
title: Isetnextstatement – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b570c2e0-a173-4f14-97d8-f39465753115
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de300a7af8492e6431f6b8513cde84a15895ad96
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786305"
---
# <a name="isetnextstatement-interface"></a>ISetNextStatement – rozhraní
Toto rozhraní je implementováno interpretu umožňující správce ladění procesu aktualizace aktuální příkaz. Je implementován z objektu rámce zásobníku a PDM získá toto rozhraní prostřednictvím QueryInterface.  
  
 rozhraní poskytuje metody, které jsou užitečné pro nastavení bod provádění, která určuje další příkaz, který se spustí.  
  
 Kromě metod zděděných z `IUnknown`, `ISetNextStatement` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ISetNextStatement::CanSetNextStatement](../../winscript/reference/isetnextstatement-cansetnextstatement.md)|Určuje, zda lze nastavit bod provádění do zadaného umístění.|  
|[ISetNextStatement::SetNextStatement](../../winscript/reference/isetnextstatement-setnextstatement.md)|Bod provádění nastaví do zadaného umístění.|