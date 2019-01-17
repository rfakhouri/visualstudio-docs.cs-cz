---
title: Isetnextstatement – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b570c2e0-a173-4f14-97d8-f39465753115
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac2d6dd0da14be5a624cff0b55985770b8d70fdf
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344054"
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