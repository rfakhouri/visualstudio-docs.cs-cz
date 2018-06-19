---
title: IDebugProperty3::CreateObjectID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::CreateObjectID
helpviewer_keywords:
- IDebugProperty3::CreateObjectID
ms.assetid: f2fa81e7-822f-456e-8729-a96a18eea771
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: df4e45c442745652b3305fd91146bd31ffe79e4b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120972"
---
# <a name="idebugproperty3createobjectid"></a>IDebugProperty3::CreateObjectID
Vytvoří jedinečné ID pro tuto vlastnost k zajištění, že je jedinečný mezi všechny ostatní vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT CreateObjectID(  
   void  
);  
```  
  
```csharp  
int CreateObjectID();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána, když správce ladicí relace chce zajistit, že tato vlastnost je jedinečně identifikovat mezi všechny ostatní vlastnosti. Modul ladění (DE) podporuje tuto metodu, pokud jsou vlastnosti, které se zabývá již jednoznačně identifikuje. Pokud je DE nepodporuje tuto metodu, vrátí `E_NOTIMPL`.  
  
 Všechny jedinečné ID vytvořené pomocí `CreateObjectID` je zničený, když [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md) metoda je volána; to také označuje konec potřebu jednoznačné identifikaci této vlastnosti.  
  
> [!NOTE]
>  Neexistuje žádná metoda načte tento jedinečný Identifikátor, takže je DE provést, ať chce pro jedinečné ID. při `CreateObjectID` metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DestroyObjectID](../../../extensibility/debugger/reference/idebugproperty3-destroyobjectid.md)