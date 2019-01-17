---
title: Iscriptnode – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptNode interface
ms.assetid: cfa76c4a-6543-48e8-a946-d212cd0bf934
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8897d783f8a101b41dd7263061604fb1d82ec56
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344613"
---
# <a name="iscriptnode-interface"></a>IScriptNode – rozhraní
Objekt, který implementuje `IScriptNode` rozhraní představuje webovou stránku.  
  
 Kromě metod zděděných z `IUnknown`, `IScriptNode` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IScriptNode::Alive](../../winscript/reference/iscriptnode-alive.md)|Určuje, zda je objekt stále aktivní.|  
|[IScriptNode:: CreateChildEntry](../../winscript/reference/iscriptnode-createchildentry.md)|Přidá instanci podřízeného `IScriptEntry`.|  
|[IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md)|Přidá skriptletu jako podřízené instance `IScriptNode`.|  
|[IScriptNode::Delete](../../winscript/reference/iscriptnode-delete.md)|Odstraní stromem objektů.|  
|[IScriptNode::GetChild](../../winscript/reference/iscriptnode-getchild.md)|Vrací podřízeného, který je k zadanému indexu v uzlu.|  
|[IScriptNode::GetCookie](../../winscript/reference/iscriptnode-getcookie.md)|Vrátí hodnotu, která slouží k přidružení skriptletu hostitelský objekt definovaného aplikací.|  
|[IScriptNode::GetIndexInParent](../../winscript/reference/iscriptnode-getindexinparent.md)|Vrátí index objektu v seznamu podřízených nadřazeného objektu.|  
|[IScriptNode::GetLanguage](../../winscript/reference/iscriptnode-getlanguage.md)|Vrátí skriptovací jazyk, který používá aktuální uzel skriptu.|  
|[IScriptNode::GetNumberOfChildren](../../winscript/reference/iscriptnode-getnumberofchildren.md)|Vrátí počet podřízených uzlů `IScriptNode` objektu.|  
|[IScriptNode::GetParent](../../winscript/reference/iscriptnode-getparent.md)|Vrátí `IScriptNode` objekt, který je nadřazeného člena objektu.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vytváření aktivních skriptů](../../winscript/reference/active-script-authoring-interfaces.md)