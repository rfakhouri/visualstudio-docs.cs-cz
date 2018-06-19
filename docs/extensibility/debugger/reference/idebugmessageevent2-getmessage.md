---
title: IDebugMessageEvent2::GetMessage | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6a00f7019a96696b0c1bde6876697b71d96c253d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31111869"
---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
Získá zprávu, která se má zobrazit.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMessage(   
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrMessage,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetMessage(   
   out enum_MESSAGETYPE pMessageType,  
   out string           pbstrMessage,  
   out uint             pdwType,  
   out string           pbstrHelpFileName,  
   out uint             dwHelpId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMessageType`  
 [out] Vrátí hodnotu z [typ zprávy](../../../extensibility/debugger/reference/messagetype.md) výčet, který popisuje typ zprávy.  
  
 `pbstrMessage`  
 [out] Vrátí zprávu.  
  
 `pdwType`  
 [out] Vrátí typ zprávy, pomocí konvencí systému Win32 `MessageBox` funkce. Najdete v článku [AfxMessageBox –](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox) funkce podrobnosti.  
  
 `pbstrHelpFileName`  
 [ve out] Vrátí název souboru nápovědy. Může být s hodnotou null (C++) nebo prázdnou hodnotu (C#), pokud není dostupný žádný soubor nápovědy.  
  
 `pdwHelpId`  
 [ve out] Vrátí identifikátor nápovědy. Může být 0, pokud neexistuje žádná nápověda související s touto zprávou.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [TYP ZPRÁVY](../../../extensibility/debugger/reference/messagetype.md)   
 [AfxMessageBox –](/cpp/mfc/reference/cstring-formatting-and-message-box-display#afxmessagebox)