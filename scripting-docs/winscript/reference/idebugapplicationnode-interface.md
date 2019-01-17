---
title: Idebugapplicationnode – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode interface
ms.assetid: 30be3a97-8191-45ac-8706-3f7056c163d6
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7bd38a0fbbdd596f6a1f6bb040190dddca78bf9
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348994"
---
# <a name="idebugapplicationnode-interface"></a>IDebugApplicationNode – rozhraní
`IDebugApplicationNode` Rozhraní rozšiřuje funkce `IDebugDocumentProvider` rozhraní tím, že poskytuje kontext v rámci stromu projektu.  
  
 Kromě metod zděděných z `IDebugDocumentProvider`, `IDebugApplicationNode` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationNode::EnumChildren](../../winscript/reference/idebugapplicationnode-enumchildren.md)|Vytvoří výčet podřízených uzlů tohoto uzlu aplikace.|  
|[IDebugApplicationNode::GetParent](../../winscript/reference/idebugapplicationnode-getparent.md)|Vrátí nadřazený uzel tohoto uzlu aplikace.|  
|[IDebugApplicationNode::SetDocumentProvider](../../winscript/reference/idebugapplicationnode-setdocumentprovider.md)|Nastaví zprostředkovatele dokumentu pro tento uzel aplikace.|  
|[IDebugApplicationNode::Close](../../winscript/reference/idebugapplicationnode-close.md)|Způsobí, že tato aplikace uvolnit všechny odkazy a zadejte neaktivním stavu.|  
|[IDebugApplicationNode::Attach](../../winscript/reference/idebugapplicationnode-attach.md)|Tento uzel aplikace přidá do stromu zadaný projekt.|  
|[IDebugApplicationNode::Detach](../../winscript/reference/idebugapplicationnode-detach.md)|Tento uzel aplikace odebere ze stromu projektu.|