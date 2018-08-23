---
title: IDebugMethodField::EnumAllLocals | Dokumentace Microsoftu
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
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ce7db92adfed5558eaaa86e2e84af51da9059020
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628217"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugMethodField::EnumAllLocals](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmethodfield-enumalllocals).  
  
Vytvoří čítač pro všechny místní proměnné metody, včetně těch kompilátorem generované interně.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objekt představující adresu ladění v rámci metody, přejdete na konkrétním oboru nebo kontextu.  
  
 `ppLocals`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam všech místních hodnot v zadaném oboru; v opačném případě vrátí hodnotu null označující žádné místní hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné místní hodnoty. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Jsou uvedené pouze proměnné definované v rámci bloku, který obsahuje adresu daného ladění. Tato metoda zahrnuje všechny místní hodnoty generovaný kompilátorem. Pokud jsou všechny, které je potřeba lokální explicitně definovaný ve zdroji, volání [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) metody.  
  
 Metoda může obsahovat více bloků nebo kontextu oboru.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)

