---
title: IScriptEntry::SetSignature | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.SetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::SetSignature
ms.assetid: 8513587d-9df2-4621-afe7-56eacbb5e688
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 660f667d3542ff2cb9a7e96444d98b3082218a2a
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089502"
---
# <a name="iscriptentrysetsignature"></a>IScriptEntry::SetSignature
Nastaví typ informace pro `IScriptEntry` objektu funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetSignature(  
   ITypeInfo          *pti  
   ULONG              iMethod  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pti`  
 [in] Informace o typu.  
  
 `iMethod`  
 [in] Metoda index `ITypeInfo` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Nastavení informací o typu s použitím `IScriptEntry::SetSignature` nebo [IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md). Informace o typu může být také generován položku založenou na reprezentaci vnitřního funkce.  
  
## <a name="see-also"></a>Viz také  
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)