---
title: IEnumCodePaths2::Reset | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumCodePaths2::Reset
helpviewer_keywords:
- IEnumCodePaths2::Reset
ms.assetid: 490c0e19-ff4b-4673-bd06-cdee996ac226
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a20697c83546fc08c3c08154961a403f18a39c39
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62867614"
---
# <a name="ienumcodepaths2reset"></a>IEnumCodePaths2::Reset
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obnoví výčtu na první prvek.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Reset(  
   void  
);  
```  
  
```csharp  
int Reset();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Až tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumcodepaths2-next.md) metoda vrátí první prvek výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)
