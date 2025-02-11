---
title: span::span – konstruktor | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic::span::span
helpviewer_keywords:
- Concurrency::diagnostic::span constructor
ms.assetid: 8b5578aa-5e5c-4ac7-87c7-ce87c4246e2c
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: df6df731de90a9aad9e6cc637b3f218e481b66b7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198300"
---
# <a name="spanspan-constructor"></a>span::span – konstruktor

[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Inicializuje novou instanci třídy `span` třídy.

## <a name="syntax"></a>Syntaxe

```
span(
   const marker_series& _Series,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   marker_importance _Importance,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
span(
   const marker_series& _Series,
   marker_importance _Importance,
   int _Category,
   _In_ LPCTSTR _Format,
   ...
);
```

#### <a name="parameters"></a>Parametry

`_Series` Platné značky řady kontextu.

`_Format` Složený řetězec formátu, který obsahuje textu smíšeného s nula nebo více položek formátu, který odpovídá objektům v seznamu argumentů.

`_Importance` Úroveň důležitosti.

`_Category` Kategorie.

## <a name="requirements"></a>Požadavky

**Záhlaví:** cvmarkersobj.h

**Namespace:** Concurrency::Diagnostic –

## <a name="see-also"></a>Viz také

[span – třída](../profiling/span-class.md)
