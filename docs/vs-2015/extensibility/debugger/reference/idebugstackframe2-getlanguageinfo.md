---
title: IDebugStackFrame2::GetLanguageInfo | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d370670ed86ee3484243fe5dc7cfdd8ea64be084
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153131"
---
# <a name="idebugstackframe2getlanguageinfo"></a>IDebugStackFrame2::GetLanguageInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Získá jazyk přidružené k tento rámec zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetLanguageInfo (   
   BSTR* pbstrLanguage,  
   GUID* pguidLanguage  
);  
```  
  
```csharp  
int GetLanguageInfo (   
   ref string pbstrLanguage,  
   ref Guid   pguidLanguage  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrLanguage`  
 [out] Vrátí název jazyka, který implementuje metodu spojenou s rámce zásobníku.  
  
 `pguidLanguage`  
 [out] Vrátí `GUID` jazyka. Pro [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] jazyků, například následující mohou být vráceny:  
  
- `guidVBScriptLang`  
  
- `guidJScriptLang`  
  
- `guidCPPLang`  
  
- `guidVBLang`  
  
- `guidSQLLang`  
  
- `guidScriptLang`  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
