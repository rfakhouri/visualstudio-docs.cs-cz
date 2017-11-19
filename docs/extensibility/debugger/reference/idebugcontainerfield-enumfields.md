---
title: IDebugContainerField::EnumFields | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugContainerField::EnumFields
helpviewer_keywords: IDebugContainerField::EnumFields method
ms.assetid: 9e5e681b-ad49-4c62-bd95-4afa11d61a57
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7e1eb67855ae1e13970ad5eab2eba8dd6308abbb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcontainerfieldenumfields"></a>IDebugContainerField::EnumFields
Vytvoří enumerátor pro pole kontejneru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumFields(   
   FIELD_KIND         dwKindFilter,  
   FIELD_MODIFIERS    dwModifiersFilter,  
   LPCOLESTR          pszNameFilter,  
   NAME_MATCH         nameMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumFields(  
   enum_ FIELD_KIND      dwKindFilter,   
   enum_ FIELD_MODIFIERS dwModifiersFilter,   
   string                pszNameFilter,   
   NAME_MATCH            nameMatch,   
   out IEnumDebugFields  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwKindFilter`  
 [v] Kombinace [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md) konstanty, které vyberte pole, která má být proveden. Typy polí můžete popisují typy úložišť, jako je například třída nebo primitivní nebo konkrétní informace, jako jsou například místní, parametr nebo "Tento" ukazatel.  
  
 `dwModifiersFilter`  
 [v] Kombinace [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) konstanty, které vyberte pole, která má být proveden. Modifikátory polí může být přístupová oprávnění, například veřejné nebo soukromé nebo úložiště informace, například virtuální, statické nebo konečné.  
  
 `pszNameFilter`  
 [v] Název pole, které chcete vytvořit její výčet. Může to být hodnota null, pokud mají být vráceny všechna pole.  
  
 `nameMatch`  
 [v] Hodnota z [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md) výčet, který určuje, jestli vyhledávání je malá a velká písmena, nebo ne.  
  
 `ppEnum`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objektu, který představuje seznam polí. Vrátí hodnotu null, pokud neexistují žádná pole.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo S_FALSE, pokud neexistují žádná pole. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `dwKindFilter`, `dwModifiersFilter`, A `pszNameFilter` parametry mohou být kombinovány, například vyberte všechny veřejné virtuální metody s názvem "MyMethod".  
  
## <a name="see-also"></a>Viz také  
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [FIELD_KIND](../../../extensibility/debugger/reference/field-kind.md)   
 [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)   
 [NAME_MATCH](../../../extensibility/debugger/reference/name-match.md)