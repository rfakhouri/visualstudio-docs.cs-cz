---
title: IScriptEntry::GetSignature | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptEntry.GetSignature
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptEntry::GetSignature
ms.assetid: 8cbf37ac-b14c-4e15-a613-06f34857da9b
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 245b5806006ad94740e09e23f881e26e071a3bc1
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092726"
---
# <a name="iscriptentrygetsignature"></a>IScriptEntry::GetSignature
Vrátí informace o typu `IScriptEntry` objektu funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSignature(  
   ITypeInfo          **ppti  
   ULONG              *piMethod  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppti`  
 [out] Informace o přidružený k tomuto typu `IScriptEntry` objektu funkce.  
  
 `piMethod`  
 [out] Metoda index `ITypeInfo` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Nastavení informací o typu s použitím [IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md) nebo [IScriptNode::CreateChildHandler](../../winscript/reference/iscriptnode-createchildhandler.md). Informace o typu může být také generován položku založenou na reprezentaci vnitřního funkce.  
  
## <a name="see-also"></a>Viz také  
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)