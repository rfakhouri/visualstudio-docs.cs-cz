---
title: Iprocessdebugmanager – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: d68c044cdc3d523841cc56814b8ca34bcd8aa037
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157227"
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