---
title: IDebugExceptionEvent2::GetExceptionDescription | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExceptionEvent2::GetExceptionDescription
helpviewer_keywords:
- IDebugExceptionEvent2::GetExceptionDescription
ms.assetid: d07d458f-5729-47e4-9b77-1bd59c61a75a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2ab2d13c80c5be1121b198ba4ebdb560c73e7c4d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950788"
---
# <a name="idebugexceptionevent2getexceptiondescription"></a>IDebugExceptionEvent2::GetExceptionDescription
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá zobrazitelný popis výjimky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetExceptionDescription(   
   BSTR* pbstrDescription  
);  
```  
  
```csharp  
int GetExceptionDescription(   
   out string pbstrDescription  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrDescription`  
 [out] Vrátí zobrazitelný popis výjimky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Řetězec vrácený z této metody je obvykle název výjimky a je zobrazena ve **výstup** okno, když dojde k výjimce.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)

