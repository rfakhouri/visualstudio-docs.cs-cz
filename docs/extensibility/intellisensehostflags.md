---
title: IntelliSenseHostFlags | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 882410d68c671a83b13bd14026e5bea4c31cb37e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861631"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
Určuje příznaky hostitele technologie IntelliSense.

## <a name="syntax"></a>Syntaxe

```cpp
enum IntellisenseHostFlags
{
    IHF_READONLYCONTEXT      = 0x00000001
    IHF_NOSEPARATESUBJECT    = 0x00000002
    IHF_SINGLELINESUBJECT    = 0x00000004
    IHF_FORCECOMMITTOCONTEXT = 0x00000008
    IHF_OVERTYPE             = 0x00000010
};
```

### <a name="parameters"></a>Parametry

|Členové|Popis|
|-------------|-----------------|
|`IHF_READONLYCONTEXT`|Vyrovnávací paměti kontextu je jen pro čtení.|
|`IHF_NOSEPARATESUBJECT`|Žádný text předmětu. Vyrovnávací paměti kontextu obsahuje cílový IntelliSense (implikuje `!IHF_READONLYCONTEXT`).|
|`IHF_SINGLELINESUBJECT`|Text předmětu není více-řádku podporující.|
|`IHF_FORCECOMMITTOCONTEXT`|Stejné jako `CanCommitIntoReadOnlyBuffer`.|
|`IHF_OVERTYPE`|Úpravy (v předmětu nebo kontext) by mělo být provedeno režim přepisování.|

## <a name="requirements"></a>Požadavky
 SingleFileeditor.idl

## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualStudio.TextManager.Interop>