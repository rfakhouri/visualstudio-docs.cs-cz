---
title: IDebugErrorEvent2::GetErrorMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
caps.latest.revision: 9
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 06ffcbaf1266f017b75e6c3662300096b534e209
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
Vrátí informace, které umožňuje vytváření čitelná pro člověka chybová zpráva.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMessageType`  
 [out] Vrátí hodnotu z [typ zprávy](../../../extensibility/debugger/reference/messagetype.md) výčtu, které popisují typ zprávy.  
  
 `pbstrErrorFormat`  
 [out] Formát poslední zprávu pro uživatele (podrobnosti najdete v části "Poznámky").  
  
 `hrErrorReason`  
 [out] Je kód chyby zprávu o.  
  
 `pdwType`  
 [out] Závažnost chyby (použijte MB_XXX konstanty pro `MessageBox`, například `MB_EXCLAMATION` nebo `MB_WARNING`).  
  
 `pbstrHelpFileName`  
 [out] Cesta k souboru nápovědy (nastaven na hodnotu null, pokud není dostupný žádný soubor nápovědy).  
  
 `pdwHelpId`  
 [out] ID tématu nápovědy k zobrazení (nastavena na 0, pokud není žádná Nápověda).  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Chybová zpráva by měl být naformátován podle `"What I was doing.  %1"`. `"%1"` By pak nahrazuje volající s chybovou zprávou odvozené z kódu chyby (což je vrácený v `hrErrorReason`). `pMessageType` Parametr řekne volající, jak by se zobrazit zpráva o poslední chybě.  
  
## <a name="see-also"></a>Viz také  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)