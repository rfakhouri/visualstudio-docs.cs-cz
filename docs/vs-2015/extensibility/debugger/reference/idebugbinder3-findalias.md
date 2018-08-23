---
title: IDebugBinder3::FindAlias | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugBinder3::FindAlias
helpviewer_keywords:
- IDebugBinder3::FindAlias method
ms.assetid: b8333701-2718-4983-8513-0875fb7cb730
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d638ed77b2ddcab54431862a26cdbab8a356e4ea
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669538"
---
# <a name="idebugbinder3findalias"></a>IDebugBinder3::FindAlias
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugBinder3::FindAlias](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugbinder3-findalias).  
  
Tato metoda vyhledá alias, název. Všechny aliasy to bude hledat v programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT FindAlias(  
   LPCOLESTR     pcstrName,  
   IDebugAlias** ppAlias  
);  
```  
  
```csharp  
int FindAlias(  
   string          pcstrName,  
   out IDebugAlias ppAlias  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcstrName`  
 [in] Název alias se najít.  
  
 `ppAlias`  
 [out] Alias najít (pokud existuje) reprezentována [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` (Pokud není nalezena alias) nebo kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda inicializuje cílového objektu na hodnotu null, před voláním; potom testy pro hodnotu null, následně k určení, zda byl nalezen alias.  
  
## <a name="see-also"></a>Viz také  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)

