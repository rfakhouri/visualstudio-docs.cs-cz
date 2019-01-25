---
title: IntelliSenseHostFlags | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 12945998b215e9082591fad514bd9c16ab789405
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766535"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje příznaky hostitele technologie IntelliSense.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Členové|Popis|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|Vyrovnávací paměti kontextu je jen pro čtení.|  
|`IHF_NOSEPARATESUBJECT`|Žádný text předmětu. Vyrovnávací paměti kontextu obsahuje cílový IntelliSense (implikuje `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|Text předmětu není více-řádku podporující.|  
|`IHF_FORCECOMMITTOCONTEXT`|Stejné jako `CanCommitIntoReadOnlyBuffer`.|  
|`IHF_OVERTYPE`|Úpravy (v předmětu nebo kontext) by mělo být provedeno režim přepisování.|  
  
## <a name="requirements"></a>Požadavky  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TextManager.Interop>
