---
title: IDebugMethodField::EnumParameters | Dokumentace Microsoftu
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
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 51e51a3c8dffebb90b36f60df6859d1cfdf4db6f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669782"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugMethodField::EnumParameters](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmethodfield-enumparameters).  
  
Vytvoří čítač pro parametry metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppParams`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam parametrů metody; v opačném případě vrátí hodnotu null, pokud neexistují žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné parametry. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek je [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) objektu, který představuje různé typy parametrů. Volání [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md) metoda na každém objektu k určení přesně jaký druh parametr objekt představuje.  
  
 Parametr zahrnuje jeho název proměnné a jeho typu. První parametr metody třídy je obvykle ukazatel "Tento".  
  
 Pokud pouze typy parametrů je potřeba, zavolejte [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)

