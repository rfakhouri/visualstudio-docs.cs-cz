---
title: IDebugErrorEvent2::GetErrorMessage | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c4b25e040fe391b0bfbd05159779096e6bad9951
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68183511"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Vrátí informace, které umožňuje tvorbu čitelné chybovou zprávu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetErrorMessage(  
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrErrorFormat,  
   HRESULT*     hrErrorReason,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetErrorMessage(  
   out enum_MESSAGETYPE   pMessageType,  
   out string             pbstrErrorFormat,  
   out int                phrErrorReason,  
   out uint               pdwType,  
   out string             pbstrHelpFileName,  
   out uint               pdwHelpId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pMessageType`  
 [out] Vrátí hodnotu z [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md) výčet popisující typ zprávy.  
  
 `pbstrErrorFormat`  
 [out] Formát závěrečná zpráva uživateli (podrobnosti viz "Poznámky").  
  
 `hrErrorReason`  
 [out] Kód chyby zprávy je o.  
  
 `pdwType`  
 [out] Závažnost chyby (použijte MB_XXX konstanty pro `MessageBox`; například `MB_EXCLAMATION` nebo `MB_WARNING`).  
  
 `pbstrHelpFileName`  
 [out] Cesta k souboru nápovědy (nastavena na hodnotu null, pokud neexistuje žádný soubor nápovědy).  
  
 `pdwHelpId`  
 [out] ID tématu nápovědy k zobrazení (nastavena na 0, pokud není žádná Nápověda).  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Chybová zpráva musí být formátována podle `"What I was doing.  %1"`. `"%1"` By pak vyměnit volajícím s chybovou zprávou, odvozený z kódu chyby (kterou vrací `hrErrorReason`). `pMessageType` Určuje parametr volající zobrazení poslední chybová zpráva.  
  
## <a name="see-also"></a>Viz také  
 [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)   
 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)
