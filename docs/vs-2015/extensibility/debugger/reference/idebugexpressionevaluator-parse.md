---
title: IDebugExpressionEvaluator::Parse | Dokumentace Microsoftu
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
- IDebugExpressionEvaluator::Parse
helpviewer_keywords:
- IDebugExpressionEvaluator::Parse method
ms.assetid: e6e31b3a-63a7-4293-bcda-267eb78dffb6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3531218bcde2303aed749714322111a94ce98f54
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266744"
---
# <a name="idebugexpressionevaluatorparse"></a>IDebugExpressionEvaluator::Parse
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda převede řetězec s výrazem na analyzovaný výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Parse(   
   LPCOLESTR                upstrExpression,  
   PARSEFLAGS               dwFlags,  
   UINT                     nRadix,  
   BSTR*                    pbstrError,  
   UINT*                    pichError,  
   IDebugParsedExpression** ppParsedExpression  
);  
```  
  
```csharp  
int Parse(  
   string                     upstrExpression,   
   enum_PARSEFLAGS            dwFlags,   
   uint                       nRadix,   
   out string                 pbstrError,   
   out uint                   pichError,   
   out IDebugParsedExpression ppParsedExpression  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `upstrExpression`  
 [in] Řetězec výrazu, který má být analyzován.  
  
 `dwFlags`  
 [in] Kolekce [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md) konstanty, které určují, jak má být analyzován výraz.  
  
 `nRadix`  
 [in] Základ, který se má použít pro interpretaci jakékoli číselné informace.  
  
 `pbstrError`  
 [out] Vrátí chybu jako čitelný text.  
  
 `pichError`  
 [out] Vrátí pozici znaku start Chyba v řetězci výraz.  
  
 `ppParsedExpression`  
 [out] Vrátí analyzovaný výrazu v [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vytváří analyzovaný výrazu, nikoli skutečnou hodnotu. Analyzovaná výrazu je připraven k vyhodnocení, to znamená, převést na hodnotu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugParsedExpression](../../../extensibility/debugger/reference/idebugparsedexpression.md)   
 [PARSEFLAGS](../../../extensibility/debugger/reference/parseflags.md)

