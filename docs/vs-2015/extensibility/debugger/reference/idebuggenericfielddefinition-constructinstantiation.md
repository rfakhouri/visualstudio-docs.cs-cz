---
title: IDebugGenericFieldDefinition::ConstructInstantiation | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ConstructInstantiation
- IDebugGenericFieldDefinition::ConstructInstantiation
ms.assetid: ef8ae261-a98b-4dc2-93b3-7c5191818ba2
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8c5bd1d6164019414bc7cc299e418c38365dbc95
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673650"
---
# <a name="idebuggenericfielddefinitionconstructinstantiation"></a>IDebugGenericFieldDefinition::ConstructInstantiation
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugGenericFieldDefinition::ConstructInstantiation](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebuggenericfielddefinition-constructinstantiation).  
  
Vytvoří instanci pole zadané pole argumentů typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT ConstructInstantiation(  
   ULONG32       cArgs,  
   IDebugField** ppArgs,  
   IDebugField** ppConstructedField  
);  
```  
  
```csharp  
int ConstructInstantiation(  
   uint            cArgs,  
   IDebugField[]   ppArgs,  
   out IDebugField ppConstructedField  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cArgs`  
 [in] Počet argumentů `ppArgs` pole.  
  
 `ppArgs`  
 [in] Pole, které obsahuje argumenty typu. Argumenty typu musí být uzavřený typy (obecné nebo zcela vytvořenou instanci obecné typy).  
  
 `ppConstructedField`  
 [out] Vrátí [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, které představuje nové pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Omezení nekontrolují.  
  
## <a name="see-also"></a>Viz také  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)

