---
title: IDebugFunctionObject2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugFunctionObject2 interface
ms.assetid: 56b2fdff-146d-4138-a34c-59a9c65a3ddd
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8910a025b569a48be6b8fce0933d03a202400dbf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673432"
---
# <a name="idebugfunctionobject2"></a>IDebugFunctionObject2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugFunctionObject2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject2).  
  
> [!IMPORTANT]
>  V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Představuje funkci a zvyšuje [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugFunctionObject2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Vyhodnocovače výrazů (EE) implementuje toto rozhraní k reprezentaci funkce.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Metody tohoto rozhraní odložit u **IDebugFunctionObject** následujícími způsoby:  
  
-   **IDebugEvaluate** metoda přijímá příznaky.  
  
-   **CreateObject** metoda přijímá příznaky a vypršení časového limitu.  
  
-   **CreateStringObjectWithLength** metoda má délku.  
  
## <a name="methods"></a>Metody  
 Toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject2-createobject.md)|Vytvoří objekt, který používá konstruktor daným nastavením příznaků hodnocení a hodnotu časového limitu.|  
|[CreateStringObjectWithLength](../../../extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength.md)|Vytvoří objekt string, který má zadanou délku.|  
|[Vyhodnocení](../../../extensibility/debugger/reference/idebugfunctionobject2-evaluate.md)|Volá funkci a vrátí výslednou hodnotu jako objekt.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

