---
title: Idebughelper – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugHelper interface
ms.assetid: ef5691e0-1d82-42c2-997c-888e31c478dd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba760dc15cc0a3d3f2f0d80f3a16c5621582bc11
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347473"
---
# <a name="idebughelper-interface"></a>IDebugHelper – rozhraní
Slouží jako objekt pro vytváření pro objekt prohlížeče a jednoduché spojovací body. Správce ladění procesu (PDM) implementuje toto rozhraní, která je využívána skriptovací stroje.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugHelper` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugHelper::CreatePropertyBrowser](../../winscript/reference/idebughelper-createpropertybrowser.md)|Vrátí prohlížeč vlastnost, která obaluje hodnotu typu VARIANT.|  
|[IDebugHelper::CreatePropertyBrowserEx](../../winscript/reference/idebughelper-createpropertybrowserex.md)|Vrátí prohlížeč vlastnost, která obtéká hodnotu typu VARIANT a umožňuje vlastní převod hodnot typu VARIANT nebo typy VARTYPE na řetězce.|  
|[IDebugHelper::CreateSimpleConnectionPoint](../../winscript/reference/idebughelper-createsimpleconnectionpoint.md)|Vrátí hodnotu, která obaluje rozhraní události danou `IDispatch` objektu.|