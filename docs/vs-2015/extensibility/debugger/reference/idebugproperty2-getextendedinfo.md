---
title: IDebugProperty2::GetExtendedInfo | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProperty2::GetExtendedInfo
helpviewer_keywords:
- IDebugProperty2::GetExtendedInfo
ms.assetid: 0c9c0b2b-7540-4424-adb5-fce7aa37a026
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 74810aab2f47a36c716891fd45b7424eb737b142
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164980"
---
# <a name="idebugproperty2getextendedinfo"></a>IDebugProperty2::GetExtendedInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá rozšířené informace o vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Identifikátor GUID, který určuje typ rozšířené informace, které se mají načíst. Podrobnosti najdete v části poznámky.  
  
 `pExtendedInfo`  
 [out] Vrátí `VARIANT` (C++) nebo objekt (C#), který slouží k načtení informací o rozšířené vlastnosti. Například může vrátit tento parametr `IUnknown` rozhraní, které je možné zadávat dotazy pro [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) rozhraní. Podrobnosti najdete v části poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `S_GETEXTENDEDINFO_NO_EXTENDEDINFO` Pokud neexistuje žádné rozšířené informace, které se mají načíst.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda existuje za účelem načtení informací, který se nepropůjčuje k načítají pomocí volání [GetPropertyInfo](../../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) metody.  
  
 Následující identifikátory GUID jsou obvykle rozpoznána touto metodou (identifikátor GUID hodnoty jsou určené pro jazyk C# od název není k dispozici v libovolném sestavení). Další identifikátory GUID je vytvořit pro interní použití.  
  
|Name|GUID|Popis|  
|----------|----------|-----------------|  
|guidDocument|{3f98de84-fee9-11d0-b47f-00a0244a1dd2}|Vrátí `IUnknown` rozhraní v dokumentu. Obvykle [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md) rozhraní můžete získat z tohoto `IUnknown` rozhraní.|  
|guidCodeContext|{e2fc65e-56ce-11d1-b528-00aax004a8797}|Vrátí `IUnknown` rozhraní pro kontext dokumentu. Obvykle [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md) rozhraní můžete získat z tohoto `IUnknown` rozhraní.|  
|guidCustomViewerSupported|{d9c9da31-ffbe-4eeb-9186-23121e3c088c}|Vrátí řetězec obsahující identifikátor CLSID vlastní prohlížeč, většinou implementují moduly vyhodnocovače výrazů.|  
|guidExtendedInfoSlot|{6df235ad-82c6-4292-9c97-7389770bc42f}|Vrátí 32-bit číslo reprezentující počet požadované slotu, je-li tato vlastnost představuje místních adres spravovaného kódu.|  
|guidExtendedInfoSignature|{b5fb6d46-f805-417f-96a3-8ba737073ffd}|Vrátí řetězec obsahující podpis proměnné přidružené k objektu vlastnosti.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugDocumentText2](../../../extensibility/debugger/reference/idebugdocumenttext2.md)   
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)
