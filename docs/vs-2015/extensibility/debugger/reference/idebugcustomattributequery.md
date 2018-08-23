---
title: IDebugCustomAttributeQuery | Dokumentace Microsoftu
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
- IDebugCustomAttributeQuery interface
ms.assetid: b804b619-70eb-4c38-80d9-c8b32b65ed3e
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d53bbc353093bd2a28732b488ce05879063f798d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633747"
---
# <a name="idebugcustomattributequery"></a>IDebugCustomAttributeQuery
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugCustomAttributeQuery](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcustomattributequery).  
  
Představuje dotaz pro vlastní atributy u metody nebo typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCustomAttributeQuery : IUnknown  
```  
  
## <a name="methods"></a>Metody  
 Toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getcustomattributebyname –](../../../extensibility/debugger/reference/idebugcustomattributequery-getcustomattributebyname.md)|Načte vlastní atribut jeho název.|  
|[IsCustomAttributeDefined](../../../extensibility/debugger/reference/idebugcustomattributequery-iscustomattributedefined.md)|Určuje, do zadaného vlastního atributu je definována.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

