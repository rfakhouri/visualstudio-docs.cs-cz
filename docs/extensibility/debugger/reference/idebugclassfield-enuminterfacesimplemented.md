---
title: IDebugClassField::EnumInterfacesImplemented | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords: IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ed2acbae6331829dca351ec7b90ae5bea9981a3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
Vytvoří enumerátor pro rozhraní implementované touto třídou.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumInterfacesImplemented(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumInterfacesImplemented(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objektu, který představuje seznam rozhraní implementovat. Vrátí hodnotu null, pokud nejsou žádné rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud nejsou žádné rozhraní implementované na této třídě. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Každý prvek výčtu je [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md) objekt popisující rozhraní. Všimněte si, že nespravované [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] kód nepoužívá rozhraní jako samostatné entity, takže tato metoda vždy vrátí hodnotu null pro nespravované [!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)] kódu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)