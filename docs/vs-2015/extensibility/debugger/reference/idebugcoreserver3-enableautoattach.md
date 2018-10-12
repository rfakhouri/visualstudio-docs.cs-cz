---
title: IDebugCoreServer3::EnableAutoAttach | Dokumentace Microsoftu
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
- IDebugCoreServer3::EnableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::EnableAutoAttach
ms.assetid: 06aa633b-263b-4e08-8844-9a52d5120b94
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bbfea47c85d9cacefdfd8d897d9af4a037bde406
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49242525"
---
# <a name="idebugcoreserver3enableautoattach"></a>IDebugCoreServer3::EnableAutoAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Umožňuje automatické připojení pro zadanou ladicí stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT EnableAutoAttach(  
   GUID*     rgguidSpecificEngines,  
   DWORD     celtSpecificEngines,  
   LPCOLESTR pszStartPageUrl,  
   BSTR*     pbstrSessionId  
);  
```  
  
```csharp  
int EnableAutoAttach(  
   Guid[]     rgguidSpecificEngines,  
   uint       celtSpecificEngines,  
   string     pszStartPageUrl,  
   out string pbstrSessionId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `rgguidSpecificEngines`  
 [in] Pole identifikátorů GUID pro každý ladicí stroj označit jako automatické připojení.  
  
 `celtSpecificEngines`  
 [in] Počet modulů, zadaný v `rgguidSpecificEngines`.  
  
 `pszStartPageUrl`  
 [in] Počáteční adresa URL má použít při připojení automaticky.  
  
 `pbstrSessionID`  
 [out] ID relace, která byla automaticky připojen.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Jeden kód chyby: `E_AUTO_ATTACH_NOT_REGISTERED`, což znamená, že objekt pro vytváření tříd auto-attach nebyl registrován.  
  
## <a name="remarks"></a>Poznámky  
 Když se spustí program přidružený k zadané adrese URL, zadaný ladicími stroji automaticky zahájení a připojené.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)

