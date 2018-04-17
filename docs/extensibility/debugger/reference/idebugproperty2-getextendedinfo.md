---
title: IDebugProperty2::GetExtendedInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetExtendedInfo
helpviewer_keywords:
- IDebugProperty2::GetExtendedInfo
ms.assetid: 0c9c0b2b-7540-4424-adb5-fce7aa37a026
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e6865361ac0b518f4fa78a3521973d756e6ab780
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugproperty2getextendedinfo"></a>IDebugProperty2::GetExtendedInfo
Získá rozšířené informace pro vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetExtendedInfo (   
   REFGUID* guidExtendedInfo,  
   VARIANT* pExtendedInfo  
);  
```  
  
```csharp  
int GetExtendedInfo (   
   ref Guid guidExtendedInfo,  
   out object pExtendedInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidExtendedInfo`  
 [v] Identifikátor GUID, který určuje typ rozšířených informací, které mají být načteny. Podrobnosti najdete v části poznámky.  
  
 `pExtendedInfo`  
 [out] Vrátí `VARIANT` (C++) nebo objektu (C#), který slouží k načtení informací o rozšířené vlastnosti. Například může vrátit tento parametr `IUnknown` rozhraní, které může být dotazován pro [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) rozhraní. Podrobnosti najdete v části poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETEXTENDEDINFO_NO_EXTENDEDINFO` Pokud neexistují žádné rozšířené informace načíst.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda existuje za účelem načtení informací, který není jít o načítány voláním [GetPropertyInfo –](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metoda.  
  
 Následující GUID jsou obvykle rozpoznána touto metodou (identifikátor GUID hodnoty jsou určené pro jazyk C# vzhledem k tomu, že název není k dispozici ve všech sestavení). Můžete vytvořit další identifikátory GUID pro interní použití.  
  
|Název|GUID|Popis|  
|----------|----------|-----------------|  
|guidDocument|{3f98de84-fee9-11d0-b47f-00a0244a1dd2}|Vrátí `IUnknown` rozhraní k dokumentu. Obvykle [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) rozhraní můžete získat z tohoto `IUnknown` rozhraní.|  
|guidCodeContext|{e2fc65e-56ce - 11d 1-b528-00aax004a8797}|Vrátí `IUnknown` rozhraní do kontextu dokumentu. Obvykle [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní můžete získat z tohoto `IUnknown` rozhraní.|  
|guidCustomViewerSupported|{d9c9da31-ffbe-4eeb-9186-23121e3c088c}|Vrací řetězec obsahující CLSID vlastní prohlížeče, obvykle implementované vyhodnocovací filtr výrazů.|  
|guidExtendedInfoSlot|{6df235ad-82c6-4292-9c97-7389770bc42f}|Vrátí 32bitové číslo reprezentující počet požadované pozici, je-li tato vlastnost představuje místní adresu spravovaného kódu.|  
|guidExtendedInfoSignature|{b5fb6d46-f805-417f-96a3-8ba737073ffd}|Vrací řetězec obsahující podpis proměnnou přidružený k vlastnosti objektu.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)