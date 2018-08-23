---
title: IDebugModuleLoadEvent2::GetModule | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugModuleLoadEvent2::GetModule
helpviewer_keywords:
- IDebugModuleLoadEvent2::GetModule
ms.assetid: c86482bb-9ce5-4e63-bbe0-969b50169424
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dcf01689b6ab133ee52870ff65293ab31e98855e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627381"
---
# <a name="idebugmoduleloadevent2getmodule"></a>IDebugModuleLoadEvent2::GetModule
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugModuleLoadEvent2::GetModule](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmoduleloadevent2-getmodule).  
  
Získá modul, který je načten nebo byla uvolněna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetModule(   
   IDebugModule2** pModule,  
   BSTR*           pbstrDebugMessage,  
   BOOL*           pbLoad  
);  
```  
  
```csharp  
int GetModule(   
   out IDebugModule2 pModule,  
   ref string        pbstrDebugMessage,  
   ref int           pbLoad  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pModule`  
 [out] Vrátí [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) objekt, který představuje modul, který je načítání nebo uvolnění.  
  
 `pbstrDebugMessage`  
 [out v] Vrátí volitelnou zprávu s popisem této události. Pokud je tento parametr hodnotu null, je požadována žádná zpráva.  
  
 `pbLoad`  
 [out v] Nenulová (`TRUE`) Pokud modul je nula a načítání (`FALSE`) Pokud uvolnění modulu. Pokud je tento parametr hodnotu null, je požadována bez stavu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)

