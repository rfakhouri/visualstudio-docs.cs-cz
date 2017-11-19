---
title: IDebugProperty2::SetValueAsReference | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProperty2::SetValueAsReference
helpviewer_keywords: IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d27a087c67401e90e8a3f4629c27d1255d0ade75
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
Nastaví hodnotu této vlastnosti na hodnotu daného odkazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetValueAsReference(  
   IDebugReference2** rgpArgs,  
   DWORD              dwArgCount,  
   IDebugReference2*  pValue,  
   DWORD              dwTimeout  
);  
```  
  
```csharp  
int SetValueAsReference(  
   IDebugReference2[] rgpArgs,  
   uint               dwArgCount,  
   IDebugReference2   pValue,  
   uint               dwTimeout  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rgpArgs`  
 [v] Pole argumentů mají být předány Metoda setter vlastnosti spravovaného kódu. Pokud metoda setter vlastnosti nevyžaduje argumenty, nebo pokud [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt neodkazuje na takové zdroj vlastnosti, `rgpArgs` by měl mít hodnotu null. Tento parametr je obvykle hodnotu null.  
  
 `dwArgCount`  
 [v] Počet argumentů `rgpArgs` pole.  
  
 `pValue`  
 [v] Odkaz, ve formě [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu na hodnotu sloužící k nastavení této vlastnosti.  
  
 `dwTimeout`  
 [v] Jak dlouho chcete-li chtít nastavit hodnotu v milisekundách. Typické hodnota je `INFINITE`. To ovlivňuje dobu, který může trvat všechny možné vyhodnocení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; jinak vrátí chybu. kód, obvykle jednu z následujících:  
  
|Chyba|Popis|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|Hodnota nastavení z odkaz není podporováno.|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Hodnotu nelze nastavit, protože tato vlastnost odkazuje na metodu.|  
|`E_SETVALUE_VALUE_IS_READONLY`|Hodnota je jen pro čtení a nelze ji nastavit.|  
|`E_NOTIMPL`|Metoda není implementována.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)