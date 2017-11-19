---
title: IDebugProperty::GetParent | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugProperty.GetParent
apilocation: scrobj.dll
helpviewer_keywords: IDebugProperty::GetParent
ms.assetid: 673d625b-acca-45c4-88f4-b72275042f8f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8559f7c7d5baa5144449f67850d2fe882c379e94
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="idebugpropertygetparent"></a>IDebugProperty::GetParent
Získá vlastnost nadřazené vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetParent (  
   IDebugProperty** ppParent  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParent`  
 [out] Vrátí `IDebugProperty` rozhraní, které představuje nadřazené vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrací platnou `HRESULT`, obvykle `S_OK`.  
  
## <a name="see-also"></a>Viz také  
 [Idebugproperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)