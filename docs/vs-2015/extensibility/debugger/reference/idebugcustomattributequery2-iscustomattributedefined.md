---
title: IDebugCustomAttributeQuery2::IsCustomAttributeDefined | Dokumentace Microsoftu
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
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
helpviewer_keywords:
- IDebugCustomAttributeQuery2::IsCustomAttributeDefined
ms.assetid: 5c07cc52-6d2d-42df-9d76-9f1f769641db
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7abdd6c2b8e974ad624549e2878ded8438fe8792
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49190304"
---
# <a name="idebugcustomattributequery2iscustomattributedefined"></a>IDebugCustomAttributeQuery2::IsCustomAttributeDefined
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje, zda existuje vlastní atribut podle názvu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT IsCustomAttributeDefined(   
   LPCOLESTR pszCustomAttributeName  
);  
```  
  
```csharp  
int IsCustomAttributeDefined(  
   [In] string pszCustomAttributeName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCustomAttributeName`  
 [in] Řetězec obsahující název vlastního atributu k vyhledání.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí hodnotu S_OK, pokud je vlastní atribut je definován v tomto poli, jinak vrátí S_FALSE.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li získat atribut bajtů spojené s vlastní atribut, zavolejte [getcustomattributebyname –](../../../extensibility/debugger/reference/idebugcustomattributequery2-getcustomattributebyname.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCustomAttributeQuery2](../../../extensibility/debugger/reference/idebugcustomattributequery2.md)

