---
title: IDebugDefaultPort2::QueryIsLocal | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::QueryIsLocal
helpviewer_keywords:
- IDebugDefaultPort2::QueryIsLocal
ms.assetid: 1a42e774-c6ed-419a-a0e3-cab5778652ca
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1e9ca74b007c3da5ac3674813ff37c718cdd801e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62921741"
---
# <a name="idebugdefaultport2queryislocal"></a>IDebugDefaultPort2::QueryIsLocal
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda určuje, zda je tento port v místním počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT QueryIsLocal(  
   void  
);  
```  
  
```csharp  
int QueryIsLocal();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` Pokud tento port je místní (ve stejném počítači jako volající) nebo `S_FALSE` Pokud port, který se nachází na jiném počítači.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)
