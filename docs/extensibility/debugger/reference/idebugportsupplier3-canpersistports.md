---
title: IDebugPortSupplier3::CanPersistPorts | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPortSupplier3::CanPersistPorts
helpviewer_keywords: IDebugPortSupplier3::CanPersistPorts
ms.assetid: 4127760c-e602-4e86-9232-457e382a52c7
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 95e62f283d2ea0411162fb0406c712f0d17a1183
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugportsupplier3canpersistports"></a>IDebugPortSupplier3::CanPersistPorts
Tato metoda určuje, zda může být z portu dodavatele zachovat (podle jejich zápis na disk) porty mezi volání ladicího programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CanPersistPorts();  
```  
  
```csharp  
int CanPersistPorts();  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 `S_OK`Pokud porty můžete nastavit jako trvalý, nebo `S_FALSE` indikující, že porty nelze zachovat.  
  
## <a name="remarks"></a>Poznámky  
 Pokud dodavatel portu můžete zachovat porty, měl by tak učinit, když byla a potom ho znovu načtěte je při vytvoření instance ještě jednou.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)