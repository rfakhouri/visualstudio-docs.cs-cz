---
title: IDebugProperty2::SetValueAsReference | Dokumentace Microsoftu
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
- IDebugProperty2::SetValueAsReference
helpviewer_keywords:
- IDebugProperty2::SetValueAsReference method
ms.assetid: 341b1b89-4ab8-4e1c-abe2-fb955df5c6b0
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b63e3fae4b3b83501a3fbba1057b7b5d06b9d14b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49270579"
---
# <a name="idebugproperty2setvalueasreference"></a>IDebugProperty2::SetValueAsReference
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví hodnotu této vlastnosti na hodnotu daného odkazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Pole argumenty pro tento zdroj vlastnosti spravovaného kódu. Pokud metoda setter vlastnosti nepřebírá argumenty nebo pokud tato [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) objekt neodkazuje na taková vlastnost setter, `rgpArgs` by měl mít hodnotu null. Tento parametr je obvykle hodnotu null.  
  
 `dwArgCount`  
 [in] Počet argumentů `rgpArgs` pole.  
  
 `pValue`  
 [in] Odkazem v podobě [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) objektu na hodnotu, která slouží k nastavení této vlastnosti.  
  
 `dwTimeout`  
 [in] Jak dlouho se má provést při nastavení hodnotu v milisekundách. Obvyklé hodnoty `INFINITE`. To má vliv na dobu, která může mít všechny možné hodnocení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; jinak vrátí chybu kódu, obvykle jednu z následujících akcí:  
  
|Chyba|Popis|  
|-----------|-----------------|  
|`E_SETVALUEASREFERENCE_NOTSUPPORTED`|Nastavením této hodnoty z odkazu není podporován.|  
|`E_SETVALUE_VALUE_CANNOT_BE_SET`|Hodnotu nelze nastavit, protože tato vlastnost odkazuje na metodu.|  
|`E_SETVALUE_VALUE_IS_READONLY`|Hodnota je jen pro čtení a nelze nastavit.|  
|`E_NOTIMPL`|Metoda není implementována.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)

