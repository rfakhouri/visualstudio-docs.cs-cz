---
title: IDebugProperty3::DestroyObjectID | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9d60cd58015ef3306c3dbfbc3b9fd9333e077d1e
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49274102"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Zničí jedinečné ID přidružené k této vlastnosti označující, že volající už zdroje k identifikaci této vlastnosti jednoznačně z dalších vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud ladicí stroj nemusí podporovat jedinečné ID pro vlastnost (protože je již sleduje je jednoznačně interně), pak můžete jednoduše vrátit `E_NOTIMPL` pro tuto metodu.  
  
 Jedinečné ID se vytváří pomocí volání [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) v případě, že volající vyžaduje, abyste měli jistotu, že tato vlastnost je jednoznačně identifikují mimo jiné vlastnosti.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)

