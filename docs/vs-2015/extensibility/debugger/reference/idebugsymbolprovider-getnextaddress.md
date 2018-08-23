---
title: IDebugSymbolProvider::GetNextAddress | Dokumentace Microsoftu
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
- IDebugSymbolProvider::GetNextAddress
helpviewer_keywords:
- IDebugSymbolProvider::GetNextAddress method
ms.assetid: 704eeb94-cb13-49d1-82b6-7d83ed0f19c0
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f109b5115880fab6703428459fcba1ef1867353
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670952"
---
# <a name="idebugsymbolprovidergetnextaddress"></a>IDebugSymbolProvider::GetNextAddress
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugSymbolProvider::GetNextAddress](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugsymbolprovider-getnextaddress).  
  
Získá adresu ladění, který následuje adresa pro danou ladění v metodě.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetNextAddress(   
   IDebugAddress*  pAddress,  
   BOOL            fStatementOnly,  
   IDebugAddress** ppAddress  
);  
```  
  
```csharp  
int GetNextAddress(   
   IDebugAddress     pAddress,  
   bool              fStatementOnly,  
   out IDebugAddress ppAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [in] Adresa pro danou ladění.  
  
 `fStatementOnly`  
 [in] Pokud je hodnota TRUE, omezí ladění adresy, které mají jeden příkaz.  
  
 `ppAddress`  
 [out] Vrátí adresu další ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Bude vracet platnou `HRESULT`, obvykle S_OK.  
  
## <a name="see-also"></a>Viz také  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)

