---
title: IScriptEntry::GetSignature | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 70cc1939ae4eb1e3c58d31b3d42b7f1b4603ce9e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58145301"
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