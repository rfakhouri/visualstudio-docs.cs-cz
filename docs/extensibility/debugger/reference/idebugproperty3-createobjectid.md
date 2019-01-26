---
title: IDebugProperty3::CreateObjectID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::CreateObjectID
helpviewer_keywords:
- IDebugProperty3::CreateObjectID
ms.assetid: f2fa81e7-822f-456e-8729-a96a18eea771
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0d833f0d01cb6abda3383e1f96d1563de96b7dff
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991707"
---
# <a name="idebugproperty3createobjectid"></a>IDebugProperty3::CreateObjectID
Vytvoří jedinečné ID pro tuto vlastnost k zajištění, že se jedná o jedinečný mimo jiné vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateObjectID(  
   void  
);  
```  
  
```csharp  
int CreateObjectID();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána, když správce ladění relace chce se ujistit, že tato vlastnost je jednoznačně identifikují mimo jiné vlastnosti. Ladicí stroj (DE) podporuje tuto metodu, pokud se už jednoznačně identifikují vlastnosti, které se zabývá. Pokud je DE nepodporuje tuto metodu, vrací `E_NOTIMPL`.  
  
 Všechny jedinečné ID vytvořené pomocí `CreateObjectID` je zničen při [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md) metoda je volána, to také signalizuje konec potřebné pro jedinečnou identifikaci této vlastnosti.  
  
> [!NOTE]
>  Neexistuje žádná metoda se tak DE můžete dělat všechno, co chce jedinečné ID načíst tento jedinečný Identifikátor, když `CreateObjectID` metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)