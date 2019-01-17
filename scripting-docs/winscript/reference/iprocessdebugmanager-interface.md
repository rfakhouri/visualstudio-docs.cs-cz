---
title: Iprocessdebugmanager – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProcessDebugManager interface
ms.assetid: b6ecb2bd-a4d1-4857-9232-036c154d0cb1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5feb67b1a616eeaa855b27cb12ea9b3146545ebd
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345120"
---
# <a name="iprocessdebugmanager-interface"></a>IProcessDebugManager – rozhraní
Primární rozhraní pro správce ladění procesu. Toto rozhraní můžete vytvořit, přidat nebo odebrat virtuální aplikace z procesu. Můžete ho zobrazit výčet rámců zásobníku a vlákna aplikace.  
  
 Kromě metod zděděných z `IUnknown`, `IProcessDebugManager` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IProcessDebugManager::CreateApplication](../../winscript/reference/iprocessdebugmanager-createapplication.md)|Vytvoří nový objekt ladění aplikací pro tuto aplikaci.|  
|[IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)|Vrátí výchozí objekt aplikace pro aktuální proces.|  
|[IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)|Přidá aplikaci do seznamu Správce ladění počítače spuštěných aplikací.|  
|[IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)|Odebere aplikaci ze spuštění seznam aplikací.|  
|[IProcessDebugManager::CreateDebugDocumentHelper](../../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md)|Vytvoří nového pomocníka dokumentu ladění pro tuto aplikaci.|